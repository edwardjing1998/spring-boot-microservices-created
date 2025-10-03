// src/routes.jsx
import React from 'react'
import { Routes, Route } from 'react-router-dom'

// ---- Direct imports (no React.lazy) ----
import Dashboard from './views/dashboard/Dashboard'
import ArchiveDashboard from './views/dashboard/ArchiveDashboard'

import Colors from './views/theme/colors/Colors'
import Typography from './views/theme/typography/Typography'

// Base
import Accordion from './views/base/accordion/Accordion'
import Breadcrumbs from './views/base/breadcrumbs/Breadcrumbs'
import Cards from './views/base/cards/Cards'
import Carousels from './views/base/carousels/Carousels'
import Collapses from './views/base/collapses/Collapses'
import ListGroups from './views/base/list-groups/ListGroups'
import Navs from './views/base/navs/Navs'
import Paginations from './views/base/paginations/Paginations'
import Placeholders from './views/base/placeholders/Placeholders'
import Popovers from './views/base/popovers/Popovers'
import Progress from './views/base/progress/Progress'
import Spinners from './views/base/spinners/Spinners'
import Tabs from './views/base/tabs/Tabs'
import Tables from './views/base/tables/Tables'
import Tooltips from './views/base/tooltips/Tooltips'

// Buttons
import Buttons from './views/buttons/buttons/Buttons'
import ButtonGroups from './views/buttons/button-groups/ButtonGroups'
import Dropdowns from './views/buttons/dropdowns/Dropdowns'

// Forms
import ChecksRadios from './views/forms/checks-radios/ChecksRadios'
import FloatingLabels from './views/forms/floating-labels/FloatingLabels'
import FormControl from './views/forms/form-control/FormControl'
import InputGroup from './views/forms/input-group/InputGroup'
import Layout from './views/forms/layout/Layout'
import Range from './views/forms/range/Range'
import Select from './views/forms/select/Select'
import Validation from './views/forms/validation/Validation'

import Charts from './views/charts/Charts'

// Icons
import CoreUIIcons from './views/icons/coreui-icons/CoreUIIcons'
import Flags from './views/icons/flags/Flags'
import Brands from './views/icons/brands/Brands'

// Notifications
import Alerts from './views/notifications/alerts/Alerts'
import Badges from './views/notifications/badges/Badges'
import Modals from './views/notifications/modals/Modals'
import Toasts from './views/notifications/toasts/Toasts'

import Widgets from './views/widgets/Widgets'

// Rapid Admin -> Edit
import SysPrinConfig from './views/rapid-admin-edit/sys-pin-config/SysPrinConfig'
import ClientInformationPanel from './views/rapid-admin-edit/client-information/ClientInformationPanel'
import ClientInformationPage from './modules/edit/client-information/ClientInformationPage'
import GlobalSettingForm from './views/rapid-admin-edit/global-setting/GlobalSettingForm'
import DailyMessage from './views/rapid-admin-edit/daily-message/DailyMessage'
import ClientAutoCompleteInput from './views/rapid-admin-edit/client-search-input/ClientAutoCompleteInput'
import ReceivingFiles from './views/rapid-admin-edit/receiving-files/ReceivingFiles'
import EmailSetup from './views/rapid-admin-edit/email-setup/EmailSetup'
import MailType from './views/rapid-admin-edit/mail-type/MailType'
import ReviewDeletedCase from './views/rapid-admin-edit/review-deleted-case/ReviewDeletedCase'
import DeleteCase from './views/rapid-admin-edit/delete-case/DeleteCase'
import SysPrinConfigs from './views/rapid-admin-edit/sys-pin-config/SysPrinConfigs'
import ZipCodeConfig from './views/rapid-admin-edit/zip-code-config/ZipcodeConfig'

// Rapid Admin -> Report
import DailyActivity from './views/rapid-admin-report/daily-activity/DailyActivity'
import DailyReturnDestroy from './views/rapid-admin-report/daily-return-destroy/DailyReturnDestroy'
import Inventory from './views/rapid-admin-report/inventory/Inventory'
import InventoryListing from './views/rapid-admin-report/inventory-listing/InventoryListing'
import InventoryReceived from './views/rapid-admin-report/inventory-received/InventoryReceived'
import ProductivityReport from './views/rapid-admin-report/productivity/ProductivityReport'
import InputRobotTotals from './views/rapid-admin-report/productivity/InputRobotTotals/InputRobotTotals'
import EmailEventId from './views/rapid-admin-report/EmailEventId/EmailEventId'
import AddressChange from './views/rapid-admin-report/address-change/AddressChange'

// Rapid Admin -> Maintenance
import ClientReportMapping from './views/rapid-admin-maintenance/client-report-mapping/ClientReportMapping'
import WebClientDirectory from './views/rapid-admin-maintenance/web-client-directory/WebClientDirectory'

// Rapid module
import RapidApp from './rapid/Rapid/Onload/Components/AccountNumberComponent'

// ---- Routes component ----
export default function AppRoutes() {
  return (
    <Routes>
      {/* Home / Dashboards */}
      <Route path="/" element={<Dashboard />} />
      <Route path="/dashboard" element={<Dashboard />} />
      <Route path="/archive-dashboard" element={<ArchiveDashboard />} />

      {/* Rapid search */}
      <Route path="/rapid/search-account" element={<RapidApp />} />

      {/* Theme */}
      <Route path="/theme/colors" element={<Carousels />} />
      <Route path="/theme/typography" element={<Typography />} />

      {/* Maintenance */}
      <Route path="/maintenance/client-report-mapping" element={<ClientReportMapping />} />
      <Route path="/maintenance/resend-web-reports" element={<Spinners />} />
      <Route path="/maintenance/web-client-directory" element={<WebClientDirectory />} />

      {/* Reports */}
      <Route path="/report/unmatch-sys-prins" element={<ChecksRadios />} />
      <Route path="/report/billing" element={<Alerts />} />
      <Route path="/report/report-queries" element={<Badges />} />
      <Route path="/report/email-event-id" element={<EmailEventId />} />
      <Route path="/report/input-rebot-totals" element={<InputRobotTotals />} />
      <Route path="/report/address-change" element={<AddressChange />} />
      <Route path="/report/mails-with-a-stat" element={<ChecksRadios />} />
      <Route path="/report/status" element={<ChecksRadios />} />
      <Route path="/report/pending-cis" element={<ChecksRadios />} />
      <Route path="/report/failed-non-mons" element={<ChecksRadios />} />
      <Route path="/report/robot-labels" element={<ChecksRadios />} />
      <Route path="/report/daily-return-destroy" element={<DailyReturnDestroy />} />
      <Route path="/report/inventory" element={<Inventory />} />
      <Route path="/report/inventory-listing" element={<InventoryListing />} />
      <Route path="/report/inventory-received" element={<InventoryReceived />} />
      <Route path="/report/daily-activity" element={<DailyActivity />} />
      <Route path="/report/productivity-report" element={<ProductivityReport />} />
      <Route path="/report/input-robot-totals" element={<InputRobotTotals />} />

      {/* Query maintenance (live + archive duplicates preserved as in your list) */}
      <Route path="/query-maintenance/define-query" element={<ChecksRadios />} />
      <Route path="/archive-query-maintenance/c3-file-transfer" element={<ChecksRadios />} />
      <Route path="/archive-query-maintenance/table-load" element={<ChecksRadios />} />
      <Route path="/query-maintenance/c3-file-transfer" element={<Alerts />} />
      <Route path="/query-maintenance/data-definitions" element={<Badges />} />
      <Route path="/query-maintenance/schedule-batch-report" element={<Range />} />
      <Route path="/query-maintenance/table-load" element={<Toasts />} />
      <Route path="/query-maintenance/table-load-column-mapping" element={<Range />} />
      <Route path="/query-maintenance/tool-tips" element={<Toasts />} />
      <Route path="/archive-maintenance/client-report-mapping" element={<Toasts />} />
      <Route path="/archive-maintenance/resend-web-reports" element={<Spinners />} />
      <Route path="/archive-maintenance/web-client-directory" element={<Tooltips />} />
      <Route path="/archive-report/billing" element={<Alerts />} />
      <Route path="/archive-maintenance/input-robot-totals" element={<Alerts />} />
      <Route path="/archive-report/unmatch-sys-prins" element={<Alerts />} />
      <Route path="/archive-report/report-queries" element={<Alerts />} />
      <Route path="/archive-report/email-event-id" element={<Range />} />
      <Route path="/archive-query-maintenance/tool-tips" element={<Range />} />
      <Route path="/archive-query-maintenance/schedule-batch-report" element={<Range />} />
      <Route path="/archive-query-maintenance/data-definitions" element={<Spinners />} />
      <Route path="/archive-query-maintenance/define-query" element={<Spinners />} />
      <Route path="/archive-query-maintenance/table-load-column-mapping" element={<Spinners />} />

      {/* Base */}
      <Route path="/base" element={<Cards />} />
      <Route path="/base/accordion" element={<Accordion />} />
      <Route path="/base/breadcrumbs" element={<Breadcrumbs />} />
      <Route path="/base/cards" element={<Cards />} />
      <Route path="/base/carousels" element={<Carousels />} />
      <Route path="/base/collapses" element={<Collapses />} />
      <Route path="/base/list-groups" element={<ListGroups />} />
      <Route path="/base/navs" element={<Navs />} />
      <Route path="/base/paginations" element={<Paginations />} />
      <Route path="/base/placeholders" element={<Placeholders />} />
      <Route path="/base/popovers" element={<Popovers />} />
      <Route path="/base/progress" element={<Progress />} />
      <Route path="/base/spinners" element={<Spinners />} />
      <Route path="/base/tabs" element={<Tabs />} />
      <Route path="/base/tables" element={<Tables />} />
      <Route path="/base/tooltips" element={<Tooltips />} />

      {/* Buttons */}
      <Route path="/buttons" element={<Buttons />} />
      <Route path="/buttons/buttons" element={<Buttons />} />
      <Route path="/buttons/dropdowns" element={<Dropdowns />} />
      <Route path="/buttons/button-groups" element={<ButtonGroups />} />

      {/* Charts */}
      <Route path="/charts" element={<Charts />} />

      {/* Forms */}
      <Route path="/forms" element={<FormControl />} />
      <Route path="/forms/form-control" element={<FormControl />} />
      <Route path="/forms/select" element={<Select />} />
      <Route path="/forms/checks-radios" element={<ChecksRadios />} />
      <Route path="/forms/range" element={<Range />} />
      <Route path="/forms/input-group" element={<InputGroup />} />
      <Route path="/forms/floating-labels" element={<FloatingLabels />} />
      <Route path="/forms/layout" element={<Layout />} />
      <Route path="/forms/validation" element={<Validation />} />

      {/* Icons */}
      <Route path="/icons" element={<CoreUIIcons />} />
      <Route path="/icons/coreui-icons" element={<CoreUIIcons />} />
      <Route path="/icons/flags" element={<Flags />} />
      <Route path="/icons/brands" element={<Brands />} />

      {/* Notifications */}
      <Route path="/notifications" element={<Alerts />} />
      <Route path="/notifications/alerts" element={<Alerts />} />
      <Route path="/notifications/badges" element={<Badges />} />
      <Route path="/notifications/modals" element={<Modals />} />
      <Route path="/notifications/toasts" element={<Toasts />} />

      {/* Widgets */}
      <Route path="/widgets" element={<Widgets />} />

      {/* Edit */}
      <Route path="/edit/global-settings" element={<GlobalSettingForm />} />
      <Route path="/edit/daily-message" element={<DailyMessage />} />
      <Route path="/edit/client-search-input" element={<ClientAutoCompleteInput />} />
      <Route path="/edit/sys-prin-config" element={<SysPrinConfig />} />
      <Route path="/edit/sys-prin-config-new" element={<SysPrinConfigs />} />
      <Route path="/edit/client-information" element={<ClientInformationPanel />} />
      <Route path="/edit/client-information-new" element={<ClientInformationPage />} />
      <Route path="/eidt/receive-files" element={<ReceivingFiles />} />
      <Route path="/edit/email-setup" element={<EmailSetup />} />
      <Route path="/edit/message-table" element={<SysPrinConfig />} />
      <Route path="/edit/zip-code-config" element={<ZipCodeConfig />} />
      <Route path="/edit/mail-type" element={<MailType />} />
      <Route path="/edit/delete-case" element={<DeleteCase />} />
      <Route path="/edit/review-deleted-case" element={<ReviewDeletedCase />} />
      <Route path="/eidt/account-number" element={<SysPrinConfig />} />
    </Routes>
  )
}
