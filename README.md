
# create-react-cr-project with vscode, perhaps the best environment for developing with react. 

Create-react-cr-project (CRPCR) is an optimal UI-based vscode-react-redux development/auto test/production environment. It supports all the modern webpack features out of the box and significantly simplifies the task of implementing a react-redux solution, as well as reducing the amount of code that must be written.

More specifically, the UI program configuration function of CRPCR automatically builds a valid react-redux program that contains all necessary library imports and other structures and then constructs the vscode/webpack production and HMR development environments for the program. In addition, a mocha and jsdom test environment is also automatically constructed that can be run and debugged from within vscode. 

The UI component configuration function of CRPCR builds valid react MVC components with all imports and component scaffolding in place. You then only need to define the component’s state variables, service functions, possible component initialization and finally the associated react stateless JSX components and that is it.

So in general under CRPCR, to implement a react-redux MVC component, you only need to:
1. Call the UI component configuration feature from vscode to create a MVC react component's model, view and controller files with all the necessary component scaffolding in place. You can also optionally request to have the config program build automated test file scaffolding for the component.
2. Define the component's redux state variables and initial values in the controller file's state variable section.
3. Define the UI service functions in the controller file's UI service function section.
4. If needed, define your component's business code in the model file.
5. Define a react stateless JSX component in the view file. The UI service functions and state variables are automatically injected into the props of the component.

Everything else is done automatically for you such as mapStateToProps, mapDispatchToProps, reducers, action creators, connect, import statements, HMR, builds, etc. In short, implementing a react/redux solution with CRPCR is almost a trivial exercise. See the extensive list below of features provided by CRPCR.

[![js-standard-style](https://cdn.rawgit.com/standard/standard/master/badge.svg)](http://standardjs.com) 

(**Please note, create-react-cr-project is only compatible with node 8.1.3 or higher.**)

## Installation

1. Go to a command window and create a directory for your project and change to that directory.
2. ```npm init``` and hit enter through all the questions.
3. ```npm install --s create-react-cr-project```
4. Depending on your system, run ```node_modules\.bin\create-react-cr-project``` or ```node_modules/.bin/create-react-cr-project```.
The installation will take a few minutes. Once npm install has been run for you, the project configuration UI will be displayed. This UI allows you to configure your project and also create react components. Select your project configuration options and save. Then you can also create react components.
5. Open your project directory in Visual Studio Code.
6. Make sure you have [vscode-chrome-debug](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) and [vscode-eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) extension installed
 
## Extensive List Of Features
* **Significantly less coding and debugging than with react alone or with react and redux.**
* Intellisense (code completion) for external libraries via [Automatic Type Acquisition (ATA)](https://code.visualstudio.com/updates/v1_7) 
* Debugging react ES2015 classes inside vscode via [vscode-chrome-debug](https://github.com/Microsoft/vscode-chrome-debug) extension
* Easy access to install, build, test and debugging commands via vscode command palette and keyboard shortcuts
* Basic Babel ES6 (does not include babel-polyfill), dynamic import, Object Rest/Spread Properties, fetch, promises, Object.assign, maps, sets and Array.from. This list can be easily extended.
* Supports the javascript standard code styling with eslint.
* JSX code analysis (linting) with autofixing support via [vscode-eslint](https://github.com/Microsoft/vscode-eslint) extension
* Supports typescript.
* Supports the typescript standard code styling with tslint.
* [React Hot Loading](https://www.youtube.com/watch?v=xsSnOQynTHs) and general [HMR](https://webpack.github.io/docs/hot-module-replacement.html) support for all code.
* Major extensions and simplifications to redux.
* Clean separation between business logic and react components. No entangling program state and business code with the UI. Allows react components to be pure UI components. This way when react becomes obsolute, you simply take it out and install a new UI without having to rewrite any program state code or business code.
* The ability to build independent react web components with the react UI part of the component being free of business logic.
* Support for the react router and redux store synchronization with your routes such that any route component will retain its redux store values given route changes and/or browser forward or back movements.
* React loadable support (code splitting).
* React/enzyme auto test environment with vscode debugging.
* Dll library support for debugging for much faster debug compilation.
* Dll library support for production. Users do not have to reload react code for example, each time they visit your site. Ideally, they need only reload your code when it changes.
* Css inline, modules and legacy support. Also support for less, sass, scss and css. Supports the postcss-loader for vendor css prefixes. 
* urlLoader support for your images, fonts etc. Inlines them in the production bundle for faster loading if they are below a threshhold. Also, they can be imported into your react components.
* Minification build bundles for both css and js for production use.
* Allows you to view your production product after a build.
* Supports progressive web apps for production. You can opt out of this.
* Supports material-ui react components.
* Supports development and production proxies so that you can proxy REST requests to your production server or some stub server such as the json-server.

## Visual Studio Code

* [**Download**](https://code.visualstudio.com/)
* [**Tips and Tricks**](https://github.com/Microsoft/vscode-tips-and-tricks)
* [**Supercharge your JavaScript debugging workflow with Visual Studio Code (Build 2017)**](https://channel9.msdn.com/Events/Build/2017/T6071)

### Required Extensions
To install extensions in vscode, click the extensions button to the very left. Then use the search box at the top to find the extension to install.

* [**Debugger for Chrome**](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
* [**Eslint**](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
* Tslint for Visual Studio Code (For typescript projects only)

### Recommended Extensions

* [ReactSnippets](https://marketplace.visualstudio.com/items?itemName=xabikos.ReactSnippets)
* [vscode-npm](https://marketplace.visualstudio.com/items?itemName=fknop.vscode-npm)
* [npm-intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)


## Visual Studio Code Shortcuts

* <kbd>F5</kbd> to start debugging
* Set up a keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>T</kbd> to display the tasks you can run listed below.
    * Build Production - Builds your production bundles and index.html. 
    * Builddll Development - Builds your development dlls for code like react to speed up debug loading and compilation. 
    * Builddll Development & Production - Builds your development dlls and production dlls.

## Adding React Components
1. In vscode, run the task 'Run Project Configuration'. You may also do it from the command line as npm run config.
2. Click 'CREATE REACT COMPONENT' and the create react component form will be displayed. Type in the component name in the React component name field and select from the various options and then click 'CREATE COMPONENT' at the top right. Once the component is created click 'EXIT' at the top right and then click the 'EXIT' button at the home screen to properly perform exit cleanup.

## Debugging
* Select the debug button to the left in vscode and select "Debug" from the drop down. Then push the green arrow button next to the dropdown.

## Production Build
* (Outside vscode) - npm run build.
* (Inside vscode) - Display the task list and select "Build Production".

## Run Production Code
* Select the debug button to the left in vscode and select "Production" from the drop down. Then push the green arrow button next to the dropdown. This will run your production code in the browser using a simple express server. (Note: running the production code does not perform a production build.)

## Build Dlls
Each time your imported modules change like react, a builddll must be performed.
* Build development dlls - Use this if you do not use dlls in your production build.
    * (Outside vscode) - npm run builddll:dev.
    * See the keyboard shortcuts for building inside vscode.
* Build development & production dlls - Use this if you use dlls in your production build.
    * (Outside vscode) - npm run builddll.
    * (Inside vscode) - See the keybaord shortcuts for building inside vscode.

## React/Enzyme Test Run and Debugging
* (Outside vscode) - npm run test.
* (Inside vscode) - Select the debug button to the left in vscode and select "Run Mocha Tests" from the debug drop down. Then push the green arrow button next to the dropdown.

## Template Configuration
All configuration settings are well documented in the UI configuration program. However, below is a few important notes.
* You must decide whether to use dlls in your production build. If so, a Builddll Development & Production listed above in keyboard shortcuts must be performed.
* If you update your import modules you must also do a builddll for development and/or production.

## License

MIT

# Documentation

### Basics Operations Available to the Controller
The generated MVC react component makes available the basic functions to manipulate the redux store partition associated with the component in the file index.js or index.ts. So, you can use the below in the controller to gain access to all of these functions. 
```javascript
import { getState, setState, partitionState, subscribe } from './'
```
1. getState() - Gets the current partition state object.
2. setState(obj) - Merges obj with the current partition state.
3. partitionState - Proxy used to access and change particular keys in the partition state. See the below for an example.
```javascript
partitionState.key = value

// partitionState.arr returns a shallow copy of the arr in the redux store partition.
const arr partitionState.arr
// Change the local arr
arr.push(1)
// Now set arr in the redux store partition
partitionState.arr = arr

// Note the below will NOT change arr in the redux store.
// This changes a local copy returned by partitionState.arr.
partitionState.arr.push(1)
```
4. subscribe(listener(obj), [key1, key2, ...]) - The listener is called if and only if any of the keys in the second argument array are changed. Only those changed keys/value pairs are passed in as an object to the listener.

Also, causality-redux is an extension to redux so you still have access to all the redux primitives with causalityRedux.store. So for example, the below gets the entire redux state object.
```javascript
const state = causalityRedux.store.getState()
```
### How to perform controller initialization that requires partitionState, getState or setState.
In the component controller file, add a function that performs the initialization code. See below for an example.
```javascript
// Put in some initial comments.
export function initController () {
  if (getState().items.length === 0) {
    const initialComments = [
      { author: 'Cory Brown', text: 'My 2 scents' },
      { author: 'Jared Anderson', text: 'Let me put it this way. You`ve heard of Socrates? Aristotle? Plato? Morons!' },
      { author: 'Matt Poulson', text: 'It`s just a function!' },
      { author: 'Bruce Campbell', text: 'Fish in a tree? How can that be?' }
    ]

    initialComments.forEach(comment => uiServiceFunctions.onAddComment(comment))
  }
}
```
Then in the component index file, simply call initController at the end. See below.
```javascript
export { commentBoxPartition, partitionState, setState, getState }
export default wrappedComponents.CommentBox

// Perform controller initialization here that needs partitionState, setState or getState.
initController()
```

### How to Change State in an MVC Component from an External Module
If you need to change component's state based on some changes that happen elsewhere in the app, define an exported function in the target Component as below. This may be needed for example as data comes in from a webSocket. It is recommended that only the owner of the state partition performs the actual changes on that component's state. 
```javascript
export const externalServiceFunctions = {
  get counter () {
    return partitionState.counter
  },
  set counter (val) {
    partitionState.counter = val
  }
}
```
Then import and export externalServiceFunctions in the component index file. Then simply import the function into the code that needs to change the component's state.
```javascript
import { externalServiceFunctions } from '../Component2'

externalServiceFunctions.counter = 2
```
### How to Access State in an MVC Component from an External Module
Assume you have a login component and you need to access some user features in that component from another module. In this case, the target controller should return a shallow copy of the the required property. Now, keep in mind that the copy may contain properties that contain objects. This would allow the requesting module to alter those embedded objects which would not be picked by the create-react-cr-project monitoring component. So, you may want to consider returning a deep copy of the object. However, if the object to be copied is complex then the deep copy operation can be very slow. In any event, these are the tradeoffs to consider. See the example below.
```javascript
// Component2 controller. The object externalServiceFunctions must be
// imported into index and then exported also.
export const externalServiceFunctions = {
  get userOption1 () {
    return partitionState.user.option1
  }
}

// Component1 controller.
import { externalServiceFunctions } from '../Component2'

if (externalServiceFunctions.userOption1) {
}
```
### How to include only a Subset of defaultState in the Props of the View Component
There will be times that your component state includes information that will not be displayed to the user such as caches. Any changes to these state items however, will cause a component render by default. So, you can list just those state keys that you want passed into the props as below.
```javascript
// Controller file
export const defaultState = {
  counter: 0,
  cache: []
}

// In the index file, add storeKeys as below. Then only counter will be in the props of the view component and not cache.
// However, all keys in defaultState will still be in the redux store partition.
const { partitionStore, partitionState, getState, setState, subscribe, wrappedComponents } = establishControllerConnections({
  module,
  partition: { partitionName: counterPartition, defaultState, uiServiceFunctions },
  storeKeys: ['counter']
  uiComponent: Counter,
  uiComponentName: 'Counter'
})
```
### How to Include Controller Functions and/or State from One MVC Component into Another MVC Component
You can include in any MVC component state and/or functions from the controller of any other MVC component. This is done using the controllerUIConnections key of the input object to establishControllerConnections. See the below for an example.
```javascript
// Index file of the including component.
import { counterFormPartition } from '../CounterForm'
import { commentBoxPartition } from '../CommentForm'
import { defaultState, uiServiceFunctions } from './controller'
import MultiPartitionForm from './view'

const controllerUIConnections = [
  {
    uiComponent: MultiPartitionForm, // React Component to wrap with redux connect
    // Use an array of objects to attach multiple partitions to the component's props
    [
      // The entry below is from this partition.
      { partitionName: multiFormPartition, storeKeys: ['fixedValue'] },
      // Include the increment function and counter state variable from
      // the counterFormPartition component.
      { partitionName: counterFormPartition, changerKeys: ['increment'], storeKeys: ['counter'] },
      // Include items from the commentBoxPartition component.
      { partitionName: commentBoxPartition, storeKeys: ['items'] }
    ],
    uiComponentName: 'MultiPartitionForm' // Name of the react component string form
  }
]

// Then perform the below to replace the default establishControllerConnections in the index file.
const { wrappedComponents } = establishControllerConnections({
  module,
  partition: { partitionName: multiFormPartition, defaultState, uiServiceFunctions },
  controllerUIConnections
})
```
Some points need to be made about the above code.
1. A partition definition is not required for the component. Therefore, a component can be summary only with no state of its own. That means the partition key would not exist for establishControllerConnections.
2. In order to include all store keys from a partition then storeKeys must be undefined. To exclude all store keys, set storeKeys=[].
3. In order to include all controller functions from a partition then changerKeys must be undefined. To exclude all controller functions, set changerKeys=[].

### How to Access Store Values from Other Modules for Calculations in Another
In the module that needs access to the store values of another module, see the below example.

```javascript
import { getState as configureGetState } from '../Configure'

const uiServiceFunctions = {
  myCalc: () => {
    const configureObj = configureGetState()
    // Use the configureObj values here.
    const myNeededValue = configureObj.otherModuleValue
  }
}
```

### How to Access UI Service Functions for Unit Testing
The partitionStore object that is exported in the component index file contains all of the UI service functions. So, in your component test code you can do something like the below.
```javascript
import { partitionStore } from './'
// Then you can call any controller function as below.
partitionStore.increment()
```
Alternatively, you can import the controller object uiServiceFunctions directly from the controller as below.
```javascript
import { uiServiceFunctions } from './controller'
// Then you can call any controller function as below.
uiServiceFunctions.increment()
```
### How to Handle Side Effects of HMR in the MVC Component
There may be times that your component adds an event listener. Then given a HMR, the listener will be attached to the event more than once. So, you can define a function that is called before a HMR to remove the event listener. Use the below to handle this situation.
```javascript
// Controller
export const hotDisposeHandler = () => {
  // Remove event listener
}

// Index file. Add hotDisposeHandler to the input object of establishControllerConnections.

import { defaultState, uiServiceFunctions, hotDisposeHandler } from './controller'

const { partitionStore, partitionState, getState, setState, subscribe, wrappedComponents } = establishControllerConnections({
  module,
  partition: { partitionName: counterPartition, defaultState, uiServiceFunctions },
  hotDisposeHandler,
  uiComponent: Counter,
  uiComponentName: 'Counter'
})
```
### Global Store Partition
Causality-redux provides a global store partition by default in create-react-cr-project. See the below for an example on how to use this global store partition.
```javascript
import {globalPartitionState} from '../causality-redux/init'
globalPartitionState.myValue = 10
```
Note however, you must add your global variables to the globalData object in causality-redux/init. So for example, to use the above the globalData might look like the below. 
```javascript
const globalData = {
  injectTapEventPlugin: false,
  myValue: 0
}
```
### How to Extend the Language with Additional Polyfills
To add a new language polyfill, simply install the library that you need and then import it into src/bootstrap/libs. Also list the additional library using the configuration program in the dll library section so that debug compilation is faster.

### How to Integrate CausalityRedux with Existing Redux Code.
CausalityRedux is capatible with redux in the same project and only requires a few lines of code. This way you can upgrade to CausalityRedux and still leave your existing working redux code base in place.
```javascript
import causalityRedux from 'causality-redux'

// Create the redux store as normal. These two steps below must be done before any causality-redux react components are imported.
const rStore = createStore(combineReducers(yourCoreReducersObject), hydrateState);
// Call causalityRedux.setReduxStore as below.
causalityRedux.setReduxStore(rStore, yourCoreReducersObject);
```
If your hydrateState contains CausalityRedux state then do the below instead.
```javascript
// Create the redux store.
const rStore = createStore(CausalityRedux.combineReducers(yourCoreReducersObject), hydrateState);
// Call CausalityRedux.setReduxStore as below.
causalityRedux.setReduxStore(rStore, yourCoreReducersObject, hydrateState);
```
If you use redux code splitting or some type of lazy load module based logic for reducers then perform the step below with your additional reducers that are to be added. This will add the additional reducers to the existing redux reducers. Note that this is the reducer object itself and not the combineReducers output.
```javascript
causalityRedux.addReducers(additionalReducersObject) 
```

### How to Perform Code Splitting and Dynamic Loading of React-Causality-Redux MVC Components
By default, create-react-cr-project supports code splitting with webpack and also supports dynamic importing. In addition by design, react-causality-redux MVC components are independent units that can be loaded at anytime as long as there is an environment in place such as the libraries react, causality-redux and react-causality-redux. When these MVC components are loaded, they configure themselves in the redux store dynamically and them boot themselves into viable react components. Therefore, you do not have to write any type of code to transition from statically built components to dynamically imported components. So, they just plain work.

See this link for information on code splitting with react by using the react router.

[https://reactjs.org/docs/code-splitting.html](https://reactjs.org/docs/code-splitting.html)

### How to Support HMR with Code Splitting and Dynamic Loading of React-Causality-Redux MVC Components
You can look for some of the solutions available but, an easy one to tomplement is to simply statically load the components when in development mode. Otherwise, in production mode use react Loadable. Below is an example.
```javascript
import Loadable from 'react-loadable'

export const counter1Route = '/counter1'

export const Counter1 = process.env.NODE_ENV === 'production'
  ? Loadable({ loader: () => import('../react-components/Counter1'), loading: Loader })
  : require('../react-components/Counter1').default
```

### State Monitoring and Debugging
create-react-cr-project provides the most advanced state change monitoring available. First, download the StateMonitor react component from [here](https://github.com/AndrewBanks10/StateMonitor) and follow the installation instructions. Also, download this [vscode extension](https://github.com/AndrewBanks10/cr-state-file-open) and follow the installation instructions.

The StateMonitor component records all state changes initiated by causality-redux. To use it, run the vscode debugger. The monitor is automatically displayed to the right hand side of the screen. Then, to see what code causes a particular state change, click on the target state change in the monitor. Go back to to vscode and perform the following steps.
1. Pull up the command palette.
2. Select the react-causality-redux load file entry in the list.
3. If the call stack only contains one entry for the state change then vscode pulls up that particular file with the specific line highlighted that caused the change.
4. If the call stack contains multiple files that caused the state change then vscode pulls up a selection list for you to choose from. Select a particular file and vscode will display that file and highlight the line. As long as you do not change the contents of the clipboard you can continue to pull up the command palette and select 'react-causality-redux load file' and then select the file in the list such that you can display each source file and line number that lead to the state change. This allows you to completely understand the code and/or find the bug in your code that caused an incorrect change in state.

# Redux Counter Sample

To show how awesome this project creator is, a sample redux counter demo will be implemented below which will also contain mocha test files.

Download the create-react-cr-project project files into a directory named counterdemo. Run the command below from the command line in the counterdemo directory.
```
npm run createproject
```
That will perform a npm install and after that will pull up a UI configuration screen. Then follow the below instructions.
1. Click the 'CONFIGURE REACT PROJECT' button. 
2. The defaults will work for this example, so then click 'SAVE CONFIGURATION' at the top right. This will take a few minutes and will display a success message. 
3. Click OK for the message and then click the 'EXIT' button at the top right.
4. Next click 'CREATE REACT COMPONENT'.
5. Type in the component name as Counter and then click 'CREATE COMPONENT' at the top right.
6. Click OK for the success message and then click 'EXIT'.
7. Finally, click the 'EXIT' button on the home screen to properly exit the UI.

The above creates a valid HMR react project with all the standard files in place. Also, under the src/react-components/Counter directory, the scaffolding for the Counter component has been created.  

Open the file src/react-components/Counter/view.jsx in vscode and replace the existing jsx code with the code below. It is simply a stateless counter react component. The ids will be used for mocha testing later.
```javascript
const Counter = ({ counter, increment }) =>
  <div>
    <p id='countertext'>{`The current counter is ${counter}.`}</p>
    <button id='onIncrement' onClick={increment}>Increment</button>
  </div>
```

Now we need to handle counter and increment in the controller. So, open the file src/react-components/Counter/controller.js. 

Put the following import at the top of the controller file for the business logic inc.
```javascript
import inc from './model'
```

Next, under the TODO: for defaultState, replace with the below. This defines the shape of the redux partition 'counterPartition' for this component.
```javascript
export const defaultState = {
  counter: 0
}
```
Now, the UI service function “increment” must be implemented. The role of a controller function is either to update redux partition values based on react UI interactions such as inputing data into a text field or to call into the business code for results and then set values in the redux partition based on those results. So, set the object uiServiceFunctions to the below. This sends in the current redux partition value counter from counterPartition into the business function inc. After the function returns, redux partition counter is changed to the incremented value. Based on this change, causality-redux automatically causes the react component Counter to render with the new value of counter set in the props.
```javascript
export const uiServiceFunctions = {
  increment: () =>
    (partitionState.counter = inc(partitionState.counter))
}
```
The proxy partitionState is supplied automatically by the controller function establishControllerConnections called below in the controller file. It allows changing values by assignment in the redux partition 'counterPartition' and also returns copies of values from that partition.

Now we only need to implement the business code for the inc function. So, open the file src/react-components/Counter/model.js and add the business code below which performs the increment function.
```javascript
export default function inc (val) {
  return val + 1
}
```
Finally, we need to include the Counter component in the react tree. Open the file src/react-components/MainApp/ MainApp.js and make the file as follows.
```javascript
import React from 'react'
import Counter from '../Counter'

const MainApp = () =>
  <Counter />

export default MainApp
```
MainApp is always the root of the react tree with create-react-cr-project and it inherits all the necessary providers based on the project configuration.
Now, click the vscode debug button at the top left and click the green arrow to begin the debug session. Then you will see your counter app in the chrome window and can verify that it works properly.

Next, while still in the debugger open the file src/react-components/Counter/model.js and change the return value of inc to val + 10 and save the file. Notice hot re-loading reloads the updated module and now your react component will increment by 10 without having to recompile and refresh. It also retains the value of counter in the react component. This provides an optimal way of debugging your component without having to lose the current program state.

Make sure that you put the inc function back to val + 1 instead of val + 10 or the tests below will fail.

After you are finished in the debugger, click 'Debug' at the top menu and then 'Stop Debugging'. 

Now, we will generate the mocha test code. So, open the file src/react-components/Counter/view.spec.js and replace the code with the following.
```javascript
import { testCauseAndEffectWithHtmlString } from '../../../../test/projectsetup'

describe('View Counter', function () {
  // Click on the increment button
  it('increment cause and effect 1 - validated.', function (done) {
    testCauseAndEffectWithHtmlString('#onIncrement', '#countertext', 'The current counter is 1.', done)
  })

  // Click on the increment button
  it('increment cause and effect 2 - validated.', function (done) {
    testCauseAndEffectWithHtmlString('#onIncrement', '#countertext', 'The current counter is 2.', done)
  })
})
```
The above code will click the button with id onIncrement and then verify that the content at id countertext is correct. Make sure to uncomment the import statement for testCauseAndEffectWithHtmlString.

Next, open the file src/react-components/Counter/controller.spec.js and replace the code with the following.
```javascript
import assert from 'assert'
import { partitionStore, partitionState } from '../'

describe('Controller Counter', function () {
  const numIterations = 10
  it('increment - validated.', function () {
    // Call the controller function
    const val = partitionState.counter
    for (let i = 0; i < numIterations; ++i) {
      partitionStore.increment()
    }
    assert(partitionState.counter === val + numIterations)
    partitionState.counter = 0
  })
})
```

In MVC, the controller provides functions to the UI and then updates the redux store based on executing those functions. So, the above exercises the controller function increment and then tests the end result of counter in the partition counterPartition in the redux store.

Finally, open the file src/react-components/Counter/model.spec.js and replace the contents with the following code. 
```javascript
import assert from 'assert'
import inc from '../model'

describe('Model Counter', function () {
  const numIterations = 1000
  it('inc - validated.', function () {
    // Call the model function
    let val = 0
    for (let i = 0; i < numIterations; ++i) {
      val = inc(val)
    }
    assert(val === numIterations)
  })
})

```
Note with this MVC implementation, we are able to bench test just the business code on its own. This provides the opportunity to more rigorously test your business functions.

Now, to run the test code, from the debug side window to the left, pull down the drop down at the top and select 'Run Mocha Tests'. Then click the green arrow and the tests will be executed. Simply, check the results in the debug console at the bottom.

Note that create-react-cr-project does all the grunt work for you in terms of setting up the project such that you need only write javascript business code, react jsx stateless components, design the redux partition for the component with defaultState and finally write javascript controller functions to call the business code and set redux partition values so that the react UI properly renders the updated results. Finally, you can optionally add mocha test code without having to perform any setup. Hence, create-react-cr-project provides an optimal way to write MVC stateless react components.

## Simplicity with Programming React Components Using create-react-cr-project
As shown above, to create react components using create-react-cr-project you only need to program these five simple items.
1. Define your component state variables in the controller object defaultState.
2. Define your component UI service functions in the controller object uiServiceFunctions and external event triggered service functions in externalServiceFunctions.
3. Define your business code.
4. Define your react component with jsx as a simple stateless component.
5. Write your test code.

## Demos Featuring this React Project Creator
[react-causality-redux-vscode-template](https://github.com/AndrewBanks10/react-causality-redux-vscode-template)

This demo contains examples for all the documentation above including a react router.
