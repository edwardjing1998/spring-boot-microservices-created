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










    

