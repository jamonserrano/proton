![Proton logo](http://jamonserrano.github.io/proton/proton-logo.png)
#Proton
###Simple HTML prototypes

Proton is a tool to create stateful prototypes for mobile and desktop.

##Installation
1. Clone the repository or download & extract the [.zip](https://github.com/jamonserrano/proton/archive/master.zip).
2. Serve the folder with your favorite local server, e.g. SimpleHTTPServer or npm serve. This is needed for the browser history to work.
3. Add your scripts and styling to app.js and app.css respectively.

##Usage

1. Define the states of your application

	```javascript
	init({
		screen: {
			home: true,
			feed: false,
			settings: false
		},
		notification: false
	});
	```
2. Add screens and other layers for each state

	```javascript
	addState({
		id: "Home"
		visible: "screen:home",
		image: "img/home.png"
	});

	addState({
		id: "SettingsButton",
		parent: "Home",
		click: "screen:settings"
	});
	```
3. Add advanced functionality and styling with JavaScript & CSS

	```javascript
	addEventListener("setState", (e) => {
		if (e.detail === "screen:settings") {
			alert("Welcome to the settings screen!");
		}
	});
	```
	```css
	#SettingsButton {
		width: 100px;
		height: 40px;
	}
	```

##Viewing & sharing
1. Open your served folder in your browser.
2. To manually change states, click on the icon in the top right folder (desktop), or tap the screen with three fingers (mobile).
3. To share a specific state, just use the URL.

##Supported browsers
Evergreen browsers with decent ES6 support: Chrome, Firefox, Edge

##Yet to come
* Documentation
* Tests!
* Gestures
* Animations

##License
MIT License