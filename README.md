# shiny-avenger
## Demo: Basic Windows API integration with a hosted web app

> This demo uses our Demo project full instructions are available at https://github.io/demo/pages.html

This demo shows how to call Windows API from a hosted web app.


### Start
Live code is fun, let's start a local webserver, and install a local hosted web app.

```
gulp appx:dev
```

### Code
Now that the localhost server is started, let's edit some code.

This demo will be editing code in the **src** directory, you can use your favorite editor, even notepad :)

**File: ./src/htdocs/index.html**
> For this demo we'll be adding all of the HTML markup in-between these two HTML comments.

```html
<!-- Demo Code Start-->

<!-- Demo Code End-->
```

1. Add a button

```
<button id="btnDemo">Demo</button>
```

**File: ./src/javascript/main.js**
> For this demo we'll add all of the JavaScript code in this file below this comment

```javascript
// file main.js
```
**Add a window load handler**

```javascript
window.addEventListener('load', demoLoaded, false);

function demoLoaded(e){
	// Insert code from Step 2
}
```
**Add a button click handler**

```javascript
	var btn = document.getElementById('btnDemo');

	btn.addEventListener('click', btnDemoHandleClick, false);
```

**Create click handler function**
```javascript
function btnDemoHandleClick(e){
	
}
```

### Under-the-hood

> This is already setup for you! But it is always good to know what is happening under the hood.

Outside of creating your website the only missing piece to have a hosted web app in the Windows Store is to create a manifest.

The demo project already has a rule to the project that automatically setups for localhost development.

**XML document Path:**

```
Package > Applications > Application > uap:ApplicationContentUriRules > uap:Rule
```
**Example:**
```xml
<uap:Rule Match="http://localhost:3000" 
		  Type="include" 
		  WindowsRuntimeAccess="all">
</uap:Rule>
```

## Using our Demo project

### Setup

#### Option 1: Use Yo
```
npm install -g yo
```

#### Option 2: Use the repo
```
git clone https://github.com/MicrosoftEdge/demo
```
