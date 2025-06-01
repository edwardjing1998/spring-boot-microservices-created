react-dom_client.js?v=ae6e808b:17987 Download the React DevTools for a better development experience: https://react.dev/link/react-devtools
chunk-MWBV3TKB.js?v=3ce83e74:30871 Uncaught Error: error #252 cannot get grid to draw rows when it is in the middle of drawing rows. 
Your code probably called a grid API method while the grid was in the render stage. 
To overcome this, put the API call into a timeout, e.g. instead of api.redrawRows(), call setTimeout(function() { api.redrawRows(); }, 0). 
To see what part of your code that caused the refresh check this stacktrace. 
See https://www.ag-grid.com/react-data-grid/errors/252?_version_=33.2.2
    at RowRenderer.getLockOnRefresh (chunk-MWBV3TKB.js?v=3ce83e74:30871:13)
    at RowRenderer.redraw (chunk-MWBV3TKB.js?v=3ce83e74:31124:10)
    at RowRenderer.onCellFocusChanged (chunk-MWBV3TKB.js?v=3ce83e74:30579:14)
    at cellFocused (chunk-MWBV3TKB.js?v=3ce83e74:30595:14)
    at callback (chunk-MWBV3TKB.js?v=3ce83e74:70:124)
    at chunk-MWBV3TKB.js?v=3ce83e74:74:9
    at Set.forEach (<anonymous>)
    at processEventListeners (chunk-MWBV3TKB.js?v=3ce83e74:66:82)
    at LocalEventService.dispatchToListeners (chunk-MWBV3TKB.js?v=3ce83e74:80:7)
    at LocalEventService.dispatchEvent (chunk-MWBV3TKB.js?v=3ce83e74:50:10)
react-dom_client.js?v=ae6e808b:6229 An error occurred in the <AgGridReactUi> component.

Consider adding an error boundary to your tree to customize error handling behavior.
Visit https://react.dev/link/error-boundaries to learn more about error boundaries.

defaultOnUncaughtError @ react-dom_client.js?v=ae6e808b:6229
:3000/#/edit/client-information-new:1 Uncaught (in promise) Error: Could not establish connection. Receiving end does not exist.
:3000/#/edit/client-information-new:1 Uncaught (in promise) Error: Could not establish connection. Receiving end does not exist.
