# How to share data between web pages?

To share data between web pages (the renderer processes) the simplest way is to use HTML5 APIs which are already available in browsers. Good candidates are Storage API, localStorage, sessionStorage, and IndexedDB.

Or you can use the IPC system, which is specific to Electron, to store objects in the main process as a global variable, and then to access them from the renderers through the remote property of electron module:

// In the main process.
global.sharedObject = {
  someProperty: 'default value'
}
// In page 1.
require('electron').remote.getGlobal('sharedObject').someProperty = 'new value'
// In page 2.
console.log(require('electron').remote.getGlobal('sharedObject').someProperty)