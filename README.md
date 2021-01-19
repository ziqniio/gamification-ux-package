<p align="center">
    <img width="600" src="https://www.competitionlabs.com/wp-content/uploads/2020/01/Logo-v4.svg"><br/>
</p>

# Gamification UX package

HTML/CSS and Vanilla JavaScript Competition Labs Leaderboard / Achievements / Inbox-Messaging widget

<p align="center">
    <img width="300" src="https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/mini-scoreboard-animation.gif"><br/>
</p>

Our widget "out of the box" is a product that you can use immediately by placing it on your existing game, on your website or include it into your Node project directly or anything that you need it to be used for. The widget is fully editable, re-adjustable, multilingual (all languages are supported), units of measure are also auto-generated by the system (all the currencies are pre defined in your private space) and it is a complementary product that gives the player a full in-depth gaming experience. All you have to do is:

[Read more here](https://complabs.atlassian.net/wiki/spaces/CLRAV/pages/842301445/The+Widget)

## Installation

The Leaderboard Widget package lives in [npm](https://www.npmjs.com/get-npm). To install the latest stable version, run the following command:

```sh
npm install @competitionlabs/gamification-ux-package
```

Or if you're using [yarn](https://classic.yarnpkg.com/en/docs/install/):

```sh
yarn add @competitionlabs/gamification-ux-package
```

## Build

#### Prerequisites

- NodeJS >= 10.10
- NPM >= 6.x

Install the dependencies.

```sh
npm install
```

Run `npm run build` to generate production files inside `build`.

```sh
npm run build
```

You can include css file into the bundle by running one of the commands (images will also be compiled into base64 format):

```sh
npm run dev -- --inlineCss=true
npm run build -- --inlineCss=true
```

Or run `npm run dev` to build widget in development mode.

```sh
npm run dev
```

#### Coding standards

Code formatting rules are defined in `.eslintrc`. You can check your code against these standards by running:

```sh
npm run lint
```

To automatically fix any style violations in your code, you can run:

```sh
npm run lint -- --fix
```

#### Running tests

You can run the test suite using the following command:

```sh
npm run test
```

Run `npm run test:coverage` to open coverage report

```sh
npm run test:coverage
```

Please ensure that the tests are passing when submitting a pull request.

#### Documentation

You can generate documentation by running:

```sh
npm run jsdoc
```


## Different themes

There are a few themes to choose from (or create your own):

Build default theme:
```shell script
npm run dev
```
Build dark theme:
```shell script
npm run dev:dark-theme
```
Build blue theme:
```shell script
npm run dev:blue-theme
```
Build green theme:
```shell script
npm run dev:green-theme
```
Build grey theme:
```shell script
npm run dev:grey-theme
```
Build red theme:
```shell script
npm run dev:red-theme
```
Build orange theme:
```shell script
npm run dev:orange-theme
```
Build black theme:
```shell script
npm run dev:black-theme
```
Grey refresh theme:
```shell script
npm run dev:grey-theme-refresh
```

## Layouts
Layouts is a new development helper view that has examples of all the different variations of the widget in a static format.
This features is really helpful in creating new theme designs and testing different theme configuration structures.
```shell script
npm run dev:layouts -- --theme=grey-theme-refresh
```

#### Command parameters:
<table>
    <tr>
        <th align="left">Parameters</th>
        <th align="left">Value</th>
        <th align="left">Description</th>
        <th align="left">Example</th>
    </tr>
    <tr>
        <td>inlineCss</td>
        <td>yes/no</td>
        <td>Forces css to be compiled into the bundle</td>
        <td>--inlineCss=true</td>
    </tr>
    <tr>
        <td>theme</td>
        <td>[theme name]</td>
        <td>Tells the rendered what theme to package and render</td>
        <td>--theme=grey-theme-refresh</td>
    </tr>
</table>

#### Themes:
* blue-theme-refresh
* default-theme
* grey-theme-refresh
* dark-theme
* blue-theme
* green-theme
* grey-theme
* red-theme
* orange-theme
* black-theme

## Examples
Running the project in dev mode will initialise with an example page.


* [Live Default Theme laoding examples](https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/examples/default-theme.html)
* [Live Dark Theme laoding examples](https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/examples/dark-theme.html)
* [Live loader script examples](https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/examples/loader.html)


<table style="border:none;">
    <tr>
        <td>
            <img width="250" src="https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/3.png" />
        </td>
        <td>
            <img width="214" src="https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/2.png" />
        </td>
        <td>
            <img width="250" src="https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/1.png" />
        </td>
    </tr>
</table>


## Adding widget to your website
```html
<script type="text/javascript">
	(function(w,d,s,u,o){
    		w[o] = {
    			apiKey: '<api_key>',
    			spaceName: '<space_name>',
    			gameId: "<game_name>",
    			memberId: '<member_reference_id>',
    			language: "en",
    			uri: {
    				gatewayDomain: "https://gateway.competitionlabs.com",
    				translationPath: "https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/build/i18n/translation_:language.json"
    			},
    			resources: [
    				"https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/build/css/theme/default-theme.css"
    			]
    		};
    		var a=d.createElement(s), m=d.getElementsByTagName(s)[0];
    		a.async=1;a.src=u;m.parentNode.insertBefore(a,m);
    	})(window,document,'script','https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/build/javascript/gamification-ux-package.v3.js',"_CLLBV3Opt");
</script>
```

## Using the loader script
You can use this loader script to centralise all your widget loading needs (custom scripts, styles and environmental parameters) into a single place.
The "Loader" script requires the bear minimum of 2 things to be set to the global `window._CLLBV3Opt` parameter before the scripts loads:
1) `gameId`
2) `memberId`
```html
<script type="text/javascript">
    window._CLLBV3Opt = {
        gameId: "my_game_id",
        memberId: "my_member_id"
    };
</script>
```
#### Steps required to configure the loader script:
1) update your default API key, space name (optional: `language` and `currency`), unless you are loading the API key and space name from your game/product
2) define what products will load in the widget:
```javascript
products: {
    "my_product_id": {
        script: "https://my.custom.script.location",
        resources: [
            "https://my.custom.stylesheet.location"
        ],
        onBeforeLoad: function( instance, options, callback ){ // your custom logic before the widget gets initialised/rendered
            if( typeof callback === "function" ) callback();
        }
    },
    "my_product_id_2": {}
}
```
3) add loader script to your website


## FAQ
### How do I set the currency:
The setting "currency" needs to be set to the appropriate ISO key used in [units of measure section](https://complabs.atlassian.net/wiki/spaces/CLRAV/pages/594935946/Units+of+Measure)
```text
{
  currency: "usd"
}
```

### How do I specify a custom stylesheet:
All styles are loaded as part of the initialisation, so overwriting the resources array variable with your stylesheet asset will allow you to load in the external stylesheets dynamically.
There is no limit to how many stylesheets you can add as the widget will load all of them from the specified array.

### How to show game/product specific competitions only:
```text
The setting "enforceGameLookup" should be set to "true" and game/product ID should be assigned to the setting entry "gameId" part of the widget startup/initialisation
{
  enforceGameLookup: true,
  gameId: "my_id"
}
```

### How to disable Inbox/Messaging section:
```text
To disable the inbox/messaging area on the full widget preview the following setting "messages.enabled" has to be set to "false":
{
  messages: {
      enable: false
  }
}
```

### How to show the widget only if there are any available competitions:
```text
The primary method “this.startup“ inside the "LbWidget" class is the one you should adjust to implement your scenario to achieve a pre-launch check, you can wrap what's inside of that method with the function:
this.checkForAvailableCompetitions()
This method collects all the necessary information about active, ready and finished competitions (example: _this.settings.tournaments.readyCompetitions will contain a list of upcoming competitions) so you can use the callback and the collected information to decide to show or hide the mini-scoreboard on startup based on your requirements.
```

### How do I only show the competition tab if there is an active competition only and/or change the default tab to the achievements tab

The current flow is:
1) once the mini scoreboard is clicked, the main layout gets initialized (unless it’s already not existing in the DOM)
2) the navigation then gets reset to the initial competition tab

To achieve this scenario you would need to do an available competition check prior to the navigation reset and then hide/show tabs accordingly based on your business requirement.
The code of interest would be on line inside the method called: "this.initLayout" in the "MainWidget" widget class, the method that resets the navigation is "_this.resetNavigation( callback )" this handles what navigation item to set as default for the user.
You can either change this code directly or override that method after initialization inside the "this.startup" method for the class "LbWidget" by doing the following "_this.settings.mainWidget.resetNavigation = function(callback){}". 
There you can write some logic that would check what tabs to show/hide. 
Or you can overwrite this on a more global scope level where you initialize the widget "new LbWidget(window._CLLBV3Opt)" as you get full access to the settings and all other methods.


### Localization - How do I translate the widget UI:
To enable translation the following steps need to be made:
1) Translate your UI elements to the appropriate language and save it in a ".json" format using the following naming pattern `translation_en.json` [JSON example](https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/i18n/translation_en.json)
2) The translations you define inside the file will be merged with the core translations on run time

```text
* The default widget language is set to english "en", the widget will try to load look for an external translation 
resource based on the language setting and the "translationPath"

* If the resource path is used as "translation_:language.json" the widget script will try to replace ":language" with the 
current language  setting and load the translation dynamically from an external source, example:
https://s3-eu-west-1.amazonaws.com/demo.competitionlabs.com/_widgets/gamification-ux-package/i18n/translation_:language.json

* If translations are not required it is possible to disable them by changing "loadTranslations" setting to "false"
```

### Why we use SASS:
Here are some of the basic benefits of why we are using SASS:
* provides the ability to use variables, allows you to store a value, or a set of values, and to reuse these variables throughout your SASS files as many times you want and wherever you want. Easy, powerful, and useful.
* the improved syntax allows you to use a nested syntax, which is code contained within another piece of code that performs a wider function
* provides mixin functionality: Mixins are like functions in other programming languages. They return a value or set of values and can take parameters including default values.
* allows you to break apart your big complex CSS files into smaller chunks, this improves the ability to work on the same stylesheets for multiple teams
* still supports the basic CSS syntax as SCSS syntax is CSS compatible

### IE11 support
Internet explorer 11 support is limited, at the moment styling and one of the libraries will need to be adjusted for full IE11 support which will require a review and update on the code where necessary.
To get the code to compile we recommend to:
1) inside the `src/javascript/modules/LbWidget.js` to remove/change the `import jsSHA from 'jssha'` import to the local library `import jsSHA from '../utils/jsSHA'`
2) inside the method `populateIdenticonBase64Image` update the jsSHA implementation from:
```javascript
var shaObj = new jsSHA('SHA-512', 'TEXT');
shaObj.update(str);
var hash = shaObj.getHash('HEX', 1);
``` 
to:
```javascript
var shaObj = new jsSHA(str, 'TEXT');
var hash = shaObj.getHash('SHA-512', 'HEX', 1);
```
