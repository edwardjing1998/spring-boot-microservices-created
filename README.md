react-dom_client.js?v=e8a8cd94:17987 Download the React DevTools for a better development experience: https://react.dev/link/react-devtools
LoadChFromCase.tsx:93 Uncaught TypeError: Cannot read properties of undefined (reading 'details')
    at fetchCHinfoDetailsInfo (LoadChFromCase.tsx:93:84)
    at fetchCHinfoDetailsInfo (react-redux.js?v=e8a8cd94:1021:28)
    at memoizedSelector (react-redux.js?v=e8a8cd94:31:32)
    at react-redux.js?v=e8a8cd94:51:24
    at mountSyncExternalStore (react-dom_client.js?v=e8a8cd94:4550:26)
    at Object.useSyncExternalStore (react-dom_client.js?v=e8a8cd94:16562:18)
    at exports.useSyncExternalStore (chunk-HUL2CLQT.js?v=e8a8cd94:930:36)
    at exports.useSyncExternalStoreWithSelector (react-redux.js?v=e8a8cd94:60:21)
    at useSelector2 (react-redux.js?v=e8a8cd94:1076:85)
    at AccountNumberComponent (AccountNumberComponent.tsx:30:21)
fetchCHinfoDetailsInfo @ LoadChFromCase.tsx:93
fetchCHinfoDetailsInfo @ react-redux.js?v=e8a8cd94:1021
memoizedSelector @ react-redux.js?v=e8a8cd94:31
(anonymous) @ react-redux.js?v=e8a8cd94:51
mountSyncExternalStore @ react-dom_client.js?v=e8a8cd94:4550
useSyncExternalStore @ react-dom_client.js?v=e8a8cd94:16562
exports.useSyncExternalStore @ chunk-HUL2CLQT.js?v=e8a8cd94:930
exports.useSyncExternalStoreWithSelector @ react-redux.js?v=e8a8cd94:60
u
    at P (chrome-extension://gofohnjbcabckdcbamaelhmppjoegikd/data/js/Verint.Validator.Content.js:1:1241)



    


import { Route, BrowserRouter as Router, Routes } from "react-router";

import RapidAdmin from "./RapidAdmin/Hello";

import AccountNumberComponent from "./Rapid/Onload/Components/AccountNumberComponent";
import ImbMainComponent from "./Rapid/RapidImb/Components/ImbMainComponent";

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<AccountNumberComponent />} />
        <Route path="/admin" element={<RapidAdmin />} />
       <Route path="/Imb" element={<ImbMainComponent />} />
      </Routes>
    </Router>
  );
}

export default App;








    const RapidApp = React.lazy(() => import('./rapid/Rapid/Onload/Components/AccountNumberComponent'))

      { path: '/rapid/search-account', name: 'RapidApp', element: RapidApp },






      import Header from "../../../HeaderComponent/Header";
import Navbar from "../CommonComponent/SideNav";
import SearchAccountNumber from "./SearchAccountNumber";
import "../scss/main.scss";
import FetchAccountDetails from "./FetchAccountDetails";
import SimpleSnackbar from "../CommonComponent/snackBar";
import { useSelector } from "react-redux";

import { fetchCHinfoDetailsInfo } from "../../Redux/LoadChFromCase";
import { fetchLabelTypeDetailsInfo } from "../../Redux/GetLabelType";
import { useEffect, useState } from "react";
import { fetchGetAmexInfo } from "../../Redux/GetAmexInfo";
import { accountDetails } from "../../types/AccountDetailstype";
import { LABEL_AMERICAN_EXPRESS } from "../../Constants/Constants";
import { fetchCardTypeDetailsInfo } from "../../Redux/GetCardType";

import { RetreieveAmexSysPrin } from "../CommonComponent/IntializeOnload";
import { useDispatch } from "react-redux";
import { AppDispatch } from "../../../store";
import { getIssuedByAmex } from "../../Redux/Case";
import {
  AccountInfo,
  caseAccountInfo,
} from "../CommonComponent/AccountInfoDetails";
import { retrieveAddressDetails } from "../../Redux/FetchAddressDetails";
import { fetchClientInfo } from "../../Redux/RetrieveSysPrin";

const AccountNumberComponent = () => {
  const labelType = useSelector(fetchLabelTypeDetailsInfo);
  const chDetails = useSelector(fetchCHinfoDetailsInfo);
  const cardType = useSelector(fetchCardTypeDetailsInfo);
  const AmexDetails = useSelector(fetchGetAmexInfo);
   
  const dispatch = useDispatch<AppDispatch>();
  const [accountInfo, setAccountInfo] = useState<accountDetails>({
    details: {
      caseNumber: "",
      piId: "",
      customerId: "",
      primaryPiId: "",
      account: "",
      lastName: "",
      firstName: "",
      homePhone: "",
      workPhone: "",
      entityCode: "",
      roleCode: "",
      piStatus: "",
      status: "",
      active: 0,
      reason: "",
      subReason: null,
      disposition: "",
      inHour: "",
      inDate: "",
      nextDate: "",
      outDate: "",
      autoDate: "",
      numCards: null,
      finalActionCardsNr: null,
      deliveryId: null,
      sysPrin: "",
      cycle: "",
      firstUpdateVendId: "",
      contactCode: "",
      contactPhoneNumber: "",
      returnReasonCode: "",
      issuanceCode: "",
      issuanceDate: "",
      operatorCode: "",
      barcodeTypeCode: "",
      fileSent: "",
      postageBilled: "",
      issuedByAmex: 0,
      recordTypeText: "",
      serviceTypeText: "",
      mailerId: "",
      as400ClientId: "",
      as400SystemId: "",
      basicSupplementalId: "",
      originalMailDate: "",
      msgId: "",
      mailMethod: "",
      sourceFile: "",
      custId: "",
      msIssueDate: "",
      custId2: "",
      marketCode: "",
      accountTokenId: "",
      piIdTokenId: "",
      primaryPiIdTokenId: "",
    },
   
  });
  //to check if data exist in db then retrieve logic
  useEffect(() => {
    if (
      labelType?.result == LABEL_AMERICAN_EXPRESS &&
      AmexDetails?.result !== "01"
    ) {
      setAccountInfo(AccountInfo(AmexDetails, cardType));
      RetreieveAmexSysPrin(
        AmexDetails?.bagID,
        AmexDetails?.productCode,
        true,
        AmexDetails?.as400SystemId,
        AmexDetails?.issueDate,
        AmexDetails?.typeIssue,
        dispatch
      );
      dispatch(getIssuedByAmex(1));

    }
  }, [AmexDetails]);

  useEffect(() => {
    if (labelType?.result !== LABEL_AMERICAN_EXPRESS) {
      setAccountInfo(caseAccountInfo(chDetails, cardType));
       dispatch(retrieveAddressDetails(chDetails?.caseNumber));
    }
    
    dispatch(fetchClientInfo(chDetails?.sysPrin))
    
  }, [chDetails]);
  return (
    <div className="container">
      <div>
        <Header />
      </div>
      <div className="subcontainer">
        <Navbar />
        <div className="sub-container-main">
          <div className="main-container">
            <SearchAccountNumber details={accountInfo?.details} />
            {accountInfo?.details?.account != "" && (
              <FetchAccountDetails
                details={accountInfo?.details}
                // piIdAddress={accountInfo?.piIdAddress}
                // primaryAddress={accountInfo?.primaryAddress}
                clientId={accountInfo?.clientId}
                CardType={cardType}
              />
            )}
          </div>
        </div>
      </div>
    </div>
  );
};

export default AccountNumberComponent;




import { configureStore } from "@reduxjs/toolkit";
import FetchNACMessageReducer from './Rapid/Redux/NACMessages'
import RetreiveCaseDetails from './Rapid/Redux/SaveCaseRedux'
import SubmitTransactiondataDetails from './Rapid/Redux/SaveNacTransaction'
import PrintLabelreducer from './Rapid/Redux/PrintLabel'
import CaseInfoReducer from './Rapid/Redux/Case'
import transactReducer from './Rapid/Redux/SaveTransactionData'
import TransactionNumberreducer from './Rapid/Redux/GetTransactionNumber'
import GetAmexInfoDetails from './Rapid/Redux/GetAmexInfo'
import FetchOpenCaseDetails from './Rapid/Redux/CheckForOpenCase'
import GetFetchCardType from './Rapid/Redux/GetCardType'
import GetFetchLabelType from './Rapid/Redux/GetLabelType'
import RetrieveCaseInfo from './Rapid/Redux/LoadChFromCase'
import ChSliceReducer from './Rapid/Redux/CardHolder'
import FetchExisitingCardHolderInfo from './Rapid/Redux/FetchExisitingCase'
import MailerReducer from './Rapid/Redux/RetrieveAs400MailerId'
import GetControlInfoDetails from './Rapid/Redux/CardHolderInfo'
import BulkCardReducer from './Rapid/Redux/insertBulkCard'
import GetAdressDetailsReducer from './Rapid/Redux/FetchDetailsFromZip'
import addressDetailsReducer from './Rapid/Redux/FetchAddressDetails'
import sysPrinreducer from './Rapid/Redux/RetrieveSysPrin'
import dispatchaddressDetailsReducer from './Rapid/Redux/dispatchAddressValues'
import submitAddressDetailsReducer from './Rapid/Redux/SubmitAddressDetails'
import fetchImbDetailsReducer from './Rapid/Redux/AccountDetailsRedux'
import AccountTransactionTypeReducer from './Rapid/Redux/AccountTransaction'
import fetchSpecialCaseMessagesReducer from './Rapid/Redux/SpecialCasesRedux'
import ImbAccountDetailsReducer from './Rapid/Redux/IMBAccountDetailsRedux'
import AudtiLogDetailesReducer from './Rapid/Redux/AuditLogApi'

export const store= configureStore({
    reducer:{
        fetchNacMessageSlice:FetchNACMessageReducer,
        retrieveCaseDetails:RetreiveCaseDetails,
        retrieveTransactionDetails:SubmitTransactiondataDetails,
        RetrieveLabelPrint:PrintLabelreducer,
        CaseInfo:CaseInfoReducer,
        transactionDetails:transactReducer,
        getTransactionNumber:TransactionNumberreducer,
        FetchForOpenCase:FetchOpenCaseDetails,
        FetchCardHolderInfo:RetrieveCaseInfo,
         fetchLabelTypeInfo:GetFetchLabelType,
         fetchGetAmexInfo:GetAmexInfoDetails,
         fetchCardTypeInfo:GetFetchCardType,
         chSlice:ChSliceReducer,
         fetchMailerInfoDetails:MailerReducer,
         exisitingCaseDetails:FetchExisitingCardHolderInfo,
         fetchControlInfodet:GetControlInfoDetails,
         insertBulkCard:BulkCardReducer,
         fetchAdressDetailsFromZip:GetAdressDetailsReducer,
         addressDetails:addressDetailsReducer,
         fetchSysPrin:sysPrinreducer,
         saveAddressDetails:dispatchaddressDetailsReducer,
         submitAddressDetailsData:submitAddressDetailsReducer,
         fetchImbDetails:fetchImbDetailsReducer,
         fetchAccountTransactionTypeDetails: AccountTransactionTypeReducer,
         specialCaseMessages:fetchSpecialCaseMessagesReducer,
         fetchAccountDetails:ImbAccountDetailsReducer,
    fetchAuditLoginfo:AudtiLogDetailesReducer,
    }
})
export type ReducerType = ReturnType<typeof store.getState>
export type AppDispatch = typeof store.dispatch;



// Rapid/Redux/LoadChFromCase.ts  (or wherever your selector lives)
import type { ReducerType } from '../../../store'; // or RootState

export const fetchCHinfoDetailsInfo = (state: ReducerType) =>
  state.FetchCardHolderInfo?.details ?? null;  // ⬅️ null-safe












// inside LoadChFromCase slice file
type Details = { caseNumber: string; /* ...other fields you read... */ };

type LoadChFromCaseState = {
  details: Details | null;
};

const initialState: LoadChFromCaseState = {
  details: null,   // ⬅️ start as null instead of undefined
};














import { createAsyncThunk, createSlice } from "@reduxjs/toolkit";
import {ReducerType} from '../../store'
import axios from "axios";
import { CardHolderInfoType } from "../types/CardHolderTypes";

export const GetChInfo:CardHolderInfoType={
    details:{
    caseNumber: "",
    piId: "",
    customerId: "",
    primaryPiId: "",
    account: "",
   firstName:"",
   lastName:"",
    homePhone: "",
    workPhone: "",
    entityCode: "",
    roleCode: "",
    piStatus: "",
    status: "",
    active: 1073741824,
    reason: "",
    subReason: 1073741824,
    disposition: "",
    inHour: "",
    inDate: "",
    nextDate: "",
    outDate: "",
    autoDate: "",
    numCards: 1073741824,
    finalActionCardsNr: 1073741824,
    deliveryId: 1073741824,
    sysPrin: "",
    cycle: "",
    firstUpdateVendId: "",
    contactCode: "",
    contactPhoneNumber: "",
    returnReasonCode: "",
    issuanceCode: "",
    issuanceDate: "",
    operatorCode: "",
    barcodeTypeCode: "",
    fileSent: "",
    postageBilled: "",
    issuedByAmex: 1073741824,
    recordTypeText: "",
    serviceTypeText: "",
    mailerId: "",
    as400ClientId: "",
    as400SystemId: "",
    basicSupplementalId: "",
    originalMailDate: "",
    msgId: "",
    mailMethod: "",
    sourceFile: "",
    custId: "",
    msIssueDate: "",
    custId2: "",
    marketCode: "",
    accountTokenId: "",
    piIdTokenId: "",
    primaryPiIdTokenId: "",
    billing_sp: ""
    }
}
export const fetchCHinfoDetails=createAsyncThunk('fetch/getCardholderInfo',async(acctNum:string)=>{
   
    const response= await axios.get(`http://localhost:8010/v1/Case/retrieveLatestCases?accNum=${acctNum}`)
    return response?.data[0]
})

const FetchCardHolderInfo=createSlice({
    name:'FetchCardHolderInfo',
    initialState:GetChInfo,
    reducers:{
        fetchCHinfoDetailsinformation(state,action){
            state=action?.payload
        }
    },
    extraReducers(builder){
        builder
        .addCase(fetchCHinfoDetails.pending,(state,action)=>{
            //state.status='loading'
        })
        .addCase(fetchCHinfoDetails.fulfilled,(state,action)=>{
          state.details=action?.payload;
        })
        .addCase(fetchCHinfoDetails.rejected,(state,action)=>{
            //state.error="Failed fetching account details"
        })
    }
})

export const fetchCHinfoDetailsInfo = (state: ReducerType) =>
  state.FetchCardHolderInfo?.details ?? null;  // ⬅️ null-safe

export const {fetchCHinfoDetailsinformation}= FetchCardHolderInfo.actions;
export default FetchCardHolderInfo.reducer;












import React from 'react'
import DeleteCase from './views/rapid-admin-edit/delete-case/DeleteCase'

const Dashboard = React.lazy(() => import('./views/dashboard/Dashboard'))
const ArchiveDashboard = React.lazy(() => import('./views/dashboard/ArchiveDashboard'))

const Colors = React.lazy(() => import('./views/theme/colors/Colors'))
const Typography = React.lazy(() => import('./views/theme/typography/Typography'))

// Base
const Accordion = React.lazy(() => import('./views/base/accordion/Accordion'))
const Breadcrumbs = React.lazy(() => import('./views/base/breadcrumbs/Breadcrumbs'))
const Cards = React.lazy(() => import('./views/base/cards/Cards'))
const Carousels = React.lazy(() => import('./views/base/carousels/Carousels'))
const Collapses = React.lazy(() => import('./views/base/collapses/Collapses'))
const ListGroups = React.lazy(() => import('./views/base/list-groups/ListGroups'))
const Navs = React.lazy(() => import('./views/base/navs/Navs'))
const Paginations = React.lazy(() => import('./views/base/paginations/Paginations'))
const Placeholders = React.lazy(() => import('./views/base/placeholders/Placeholders'))
const Popovers = React.lazy(() => import('./views/base/popovers/Popovers'))
const Progress = React.lazy(() => import('./views/base/progress/Progress'))
const Spinners = React.lazy(() => import('./views/base/spinners/Spinners'))
const Tabs = React.lazy(() => import('./views/base/tabs/Tabs'))
const Tables = React.lazy(() => import('./views/base/tables/Tables'))
const Tooltips = React.lazy(() => import('./views/base/tooltips/Tooltips'))

// Buttons
const Buttons = React.lazy(() => import('./views/buttons/buttons/Buttons'))
const ButtonGroups = React.lazy(() => import('./views/buttons/button-groups/ButtonGroups'))
const Dropdowns = React.lazy(() => import('./views/buttons/dropdowns/Dropdowns'))

//Forms
const ChecksRadios = React.lazy(() => import('./views/forms/checks-radios/ChecksRadios'))
const FloatingLabels = React.lazy(() => import('./views/forms/floating-labels/FloatingLabels'))
const FormControl = React.lazy(() => import('./views/forms/form-control/FormControl'))
const InputGroup = React.lazy(() => import('./views/forms/input-group/InputGroup'))
const Layout = React.lazy(() => import('./views/forms/layout/Layout'))
const Range = React.lazy(() => import('./views/forms/range/Range'))
const Select = React.lazy(() => import('./views/forms/select/Select'))
const Validation = React.lazy(() => import('./views/forms/validation/Validation'))

const Charts = React.lazy(() => import('./views/charts/Charts'))

// Icons
const CoreUIIcons = React.lazy(() => import('./views/icons/coreui-icons/CoreUIIcons'))
const Flags = React.lazy(() => import('./views/icons/flags/Flags'))
const Brands = React.lazy(() => import('./views/icons/brands/Brands'))

// Notifications
const Alerts = React.lazy(() => import('./views/notifications/alerts/Alerts'))
const Badges = React.lazy(() => import('./views/notifications/badges/Badges'))
const Modals = React.lazy(() => import('./views/notifications/modals/Modals'))
const Toasts = React.lazy(() => import('./views/notifications/toasts/Toasts'))

const Widgets = React.lazy(() => import('./views/widgets/Widgets'))

// Rapid Admin -> Edit
const SysPrinConfig = React.lazy(() => import('./views/rapid-admin-edit/sys-pin-config/SysPrinConfig'))
const ClientInformationPanel = React.lazy(() => import('./views/rapid-admin-edit/client-information/ClientInformationPanel'))
const ClientInformationPage = React.lazy(() => import('./modules/edit/client-information/ClientInformationPage'))


const GlobalSettingForm = React.lazy(() => import('./views/rapid-admin-edit/global-setting/GlobalSettingForm'))
const DailyMessage = React.lazy(() => import('./views/rapid-admin-edit/daily-message/DailyMessage'))
const ClientAutoCompleteInput = React.lazy(() => import('./views/rapid-admin-edit/client-search-input/ClientAutoCompleteInput'))
const ReceivingFiles = React.lazy(() => import('./views/rapid-admin-edit/receiving-files/ReceivingFiles'))
const EmailSetup = React.lazy(() => import('./views/rapid-admin-edit/email-setup/EmailSetup'))

const MailType = React.lazy(() => import('./views/rapid-admin-edit/mail-type/MailType'))


const ReviewDeletedCase = React.lazy(() => import('./views/rapid-admin-edit/review-deleted-case/ReviewDeletedCase'))
const DeletedCase = React.lazy(() => import('./views/rapid-admin-edit/delete-case/DeleteCase'))

const DailyActivity = React.lazy(() => import('./views/rapid-admin-report/daily-activity/DailyActivity'))
const DailyReturnDestroy = React.lazy(() => import('./views/rapid-admin-report/daily-return-destroy/DailyReturnDestroy'))
const Inventory = React.lazy(() => import('./views/rapid-admin-report/inventory/Inventory'))
const InventoryListing = React.lazy(() => import('./views/rapid-admin-report/inventory-listing/InventoryListing'))
const InventoryReceived = React.lazy(() => import('./views/rapid-admin-report/inventory-received/InventoryReceived'))

const ProductivityReport = React.lazy(() => import('./views/rapid-admin-report/productivity/ProductivityReport'))

const SysPrinConfigs = React.lazy(() => import('./views/rapid-admin-edit/sys-pin-config/SysPrinConfigs'))
const ZipCodeConfig = React.lazy(() => import('./views/rapid-admin-edit/zip-code-config/ZipcodeConfig'))

const AddressChange = React.lazy(() => import('./views/rapid-admin-report/address-change/AddressChange'))

const ClientReportMapping = React.lazy(() => import('./views/rapid-admin-maintenance/client-report-mapping/ClientReportMapping'))
const WebClientDirectory = React.lazy(() => import('./views/rapid-admin-maintenance/web-client-directory/WebClientDirectory'))

const InputRobotTotals = React.lazy(() => import('./views/rapid-admin-report/productivity/InputRobotTotals/InputRobotTotals'))

const EmailEventId = React.lazy(() => import('./views/rapid-admin-report/EmailEventId/EmailEventId'))

const RapidApp = React.lazy(() => import('./rapid/Rapid/Onload/Components/AccountNumberComponent'))


const routes = [
  { path: '/', exact: true, name: 'Home' },
  { path: '/dashboard', name: 'Dashboard', element: Dashboard },
  { path: '/archive-dashboard', name: 'ArchiveDashboard', element: ArchiveDashboard },

  { path: '/rapid/search-account', name: 'RapidApp', element: RapidApp },

  { path: '/theme/colors', name: 'Colors', element: Carousels },
  { path: '/maintenance/client-report-mapping', name: 'ClientReportMapping', element: ClientReportMapping },
  { path: '/maintenance/resend-web-reports', name: 'Colors', element: Spinners },
  { path: '/maintenance/web-client-directory', name: 'WebClientDirectory', element: WebClientDirectory },

  { path: '/report/unmatch-sys-prins', name: 'Colors', element: ChecksRadios },
  { path: '/report/billing', name: 'Colors', element: Alerts },
  { path: '/report/report-queries', name: 'Colors', element: Badges },
  { path: '/report/email-event-id', name: 'EmailEventId', element: EmailEventId },
  { path: '/report/input-rebot-totals', name: 'InputRobotTotals', element: InputRobotTotals },

  { path: '/report/billing', name: 'Colors', element: Toasts },
  { path: '/report/resend-email-reports', name: 'Colors', element: Toasts },
  { path: '/report/report-queries', name: 'Colors', element: Toasts },
  { path: '/report/email-event-id', name: 'Colors', element: Toasts },

  { path: '/query-maintenance/define-query', name: 'Colors', element: ChecksRadios },

  { path: '/archive-query-maintenance/c3-file-transfer', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/define-query', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/define-query', name: 'Colors', element: ChecksRadios },
  { path: '/archive-query-maintenance/table-load', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/define-query', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/define-query', name: 'Colors', element: ChecksRadios },


  { path: '/query-maintenance/c3-file-transfer', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/data-definitions', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/define-query', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/table-load', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/table-load-column-mapping', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/tool-tips', name: 'Colors', element: ChecksRadios },

  { path: '/report/address-change', name: 'AddressChange', element: AddressChange },

  { path: '/report/mails-with-a-stat', name: 'Colors', element: ChecksRadios },
  { path: '/report/status', name: 'Colors', element: ChecksRadios },
  { path: '/report/pending-cis', name: 'Colors', element: ChecksRadios },
  { path: '/report/failed-non-mons', name: 'Colors', element: ChecksRadios },
  { path: '/report/robot-labels', name: 'Colors', element: ChecksRadios },


  { path: '/query-maintenance/define-query', name: 'Colors', element: ChecksRadios },
  { path: '/query-maintenance/c3-file-transfer', name: 'Colors', element: Alerts },
  { path: '/query-maintenance/data-definitions', name: 'Colors', element: Badges },
  { path: '/query-maintenance/schedule-batch-report', name: 'Colors', element: Range },
  { path: '/query-maintenance/table-load', name: 'Colors', element: Toasts },
  { path: '/query-maintenance/table-load-column-mapping', name: 'Colors', element: Range },
  { path: '/query-maintenance/tool-tips', name: 'Colors', element: Toasts },


  { path: '/archive-maintenance/client-report-mapping', name: 'Colors', element: Toasts },
  { path: '/archive-maintenance/resend-web-reports', name: 'Colors', element: Spinners },
  { path: '/archive-maintenance/web-client-directory', name: 'Colors', element: Tooltips },
  { path: '/archive-report/billing', name: 'Colors', element: Alerts },
  { path: '/archive-maintenance/input-robot-totals', name: 'Colors', element: Alerts },
  { path: '/archive-report/unmatch-sys-prins', name: 'Colors', element: Alerts },
  { path: '/archive-report/report-queries', name: 'Colors', element: Alerts },
  { path: '/archive-report/email-event-id', name: 'Colors', element: Range },
  { path: '/archive-query-maintenance/tool-tips', name: 'Colors', element: Range },
  { path: '/archive-query-maintenance/schedule-batch-report', name: 'Colors', element: Range },
  { path: '/archive-query-maintenance/data-definitions', name: 'Spinners', element: Spinners },
  { path: '/archive-query-maintenance/define-query', name: 'Spinners', element: Spinners },
  { path: 'archive-query-maintenance/table-load-column-mapping', name: 'Spinners', element: Spinners },

  { path: '/theme/typography', name: 'Typography', element: Typography },
  { path: '/base', name: 'Base', element: Cards, exact: true },
  { path: '/base/accordion', name: 'Accordion', element: Accordion },
  { path: '/base/breadcrumbs', name: 'Breadcrumbs', element: Breadcrumbs },
  { path: '/base/cards', name: 'Cards', element: Cards },
  { path: '/base/carousels', name: 'Carousel', element: Carousels },
  { path: '/base/collapses', name: 'Collapse', element: Collapses },
  { path: '/base/list-groups', name: 'List Groups', element: ListGroups },
  { path: '/base/navs', name: 'Navs', element: Navs },
  { path: '/base/paginations', name: 'Paginations', element: Paginations },
  { path: '/base/placeholders', name: 'Placeholders', element: Placeholders },
  { path: '/base/popovers', name: 'Popovers', element: Popovers },
  { path: '/base/progress', name: 'Progress', element: Progress },
  { path: '/base/spinners', name: 'Spinners', element: Spinners },
  { path: '/base/tabs', name: 'Tabs', element: Tabs },
  { path: '/base/tables', name: 'Tables', element: Tables },
  { path: '/base/tooltips', name: 'Tooltips', element: Tooltips },
  { path: '/buttons', name: 'Buttons', element: Buttons, exact: true },
  { path: '/buttons/buttons', name: 'Buttons', element: Buttons },
  { path: '/buttons/dropdowns', name: 'Dropdowns', element: Dropdowns },
  { path: '/buttons/button-groups', name: 'Button Groups', element: ButtonGroups },
  { path: '/charts', name: 'Charts', element: Charts },
  { path: '/forms', name: 'Forms', element: FormControl, exact: true },
  { path: '/forms/form-control', name: 'Form Control', element: FormControl },
  { path: '/forms/select', name: 'Select', element: Select },
  { path: '/forms/checks-radios', name: 'Checks & Radios', element: ChecksRadios },
  { path: '/forms/range', name: 'Range', element: Range },
  { path: '/forms/input-group', name: 'Input Group', element: InputGroup },
  { path: '/forms/floating-labels', name: 'Floating Labels', element: FloatingLabels },
  { path: '/forms/layout', name: 'Layout', element: Layout },
  { path: '/forms/validation', name: 'Validation', element: Validation },
  { path: '/icons', exact: true, name: 'Icons', element: CoreUIIcons },
  { path: '/icons/coreui-icons', name: 'CoreUI Icons', element: CoreUIIcons },
  { path: '/icons/flags', name: 'Flags', element: Flags },
  { path: '/icons/brands', name: 'Brands', element: Brands },
  { path: '/notifications', name: 'Notifications', element: Alerts, exact: true },
  { path: '/notifications/alerts', name: 'Alerts', element: Alerts },
  { path: '/notifications/badges', name: 'Badges', element: Badges },
  { path: '/notifications/modals', name: 'Modals', element: Modals },
  { path: '/notifications/toasts', name: 'Toasts', element: Toasts },
  { path: '/widgets', name: 'Widgets', element: Widgets },

  // Edit
  { path: '/edit/global-settings', name: 'GlobalSettingForm', element: GlobalSettingForm },
  { path: '/edit/daily-message', name: 'DailyMessage', element: DailyMessage },
  { path: '/edit/client-search-input', name: 'ClientAutoCompleteInput', element: ClientAutoCompleteInput },
  { path: '/edit/sys-prin-config', name: 'SysPrinConfig', element: SysPrinConfig },
  { path: '/edit/sys-prin-config-new', name: 'SysPrinConfigs', element: SysPrinConfigs },
  { path: '/edit/client-information', name: 'ClientInformationPanel', element: ClientInformationPanel },
  { path: '/edit/client-information-new', name: 'Edit / Client Information', element: ClientInformationPage },
  { path: '/eidt/receive-files', name: 'ReceivingFiles', element: ReceivingFiles },
  { path: '/edit/email-setup', name: 'EmailSetup', element: EmailSetup },
  { path: '/edit/message-table', name: 'SysPrinConfig', element: SysPrinConfig },
  { path: '/edit/zip-code-config', name: 'ZipCodeConfig', element: ZipCodeConfig },
  { path: '/edit/mail-type', name: 'MailType', element: MailType },
  { path: '/edit/delete-case', name: 'DeleteCase', element: DeleteCase },
  { path: '/edit/review-deleted-case', name: 'ReviewDeletedCase', element: ReviewDeletedCase },
  { path: '/eidt/account-number', name: 'SysPrinConfig', element: SysPrinConfig },

  { path: '/report/daily-return-destroy', name: 'DailyReturnDestroy', element: DailyReturnDestroy },
  { path: '/report/inventory', name: 'Inventory', element: Inventory },
  { path: '/report/inventory-listing', name: 'InventoryListing', element: InventoryListing },
  { path: '/report/inventory-received', name: 'InventoryReceived', element: InventoryReceived },
  { path: '/report/daily-activity', name: 'DailyActivity', element: DailyActivity },
  { path: '/report/productivity-report', name: 'ProductivityReport', element: ProductivityReport },
  { path: '/report/input-robot-totals', name: 'InputRobotTotals', element: InputRobotTotals },
]

export default routes










    

