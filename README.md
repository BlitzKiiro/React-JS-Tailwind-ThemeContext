# React-JS-Tailwind-ThemeContext
React Context for Handling ( Dark / Light / System ) themes for React.js and TailwindCSS

<h1> How does it work </h1>

(1) Theme Povider integrates with TailwindCSS to add/remove the "dark" class to/from the DOM root HTML tag which automatically switches tailwind css theme mode from  dark to light and vice versa

(2) Theme Povider saves user theme prefrences from previous visits in browser's localstorage whether it's light or dark. 

(3) If there are no saved theme prefrences The Provider uses the system (os) default theme mode.

(4) If theme mode is set to "system" The Porvider detects any change in system's default theme and provides the user with live theme mode update in realtime. 
 


<h1> How to use </h1>

(1) Add darkMode class property to tailwind.config.js  file

```
module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  darkMode: "class",
};

```

(2) Wrap your main component with the ThemeContextProvider component in the App.js file ( react ) or _app.js file ( next.js) 

```
 <ThemeContextProvider>
        <Component {...pageProps} />
 </ThemeContextProvider>
``

(3) use useThemeContext hook to get the Theme mode and dispatch function to change theme Read theme value

<h4> - getting current theme mode </h4>

```
const { theme, dispatch } = useThemeContext();
const {mode} = theme
{/* light , dark or system  */}

```

<h4> - changing theme mode </h4>

```
  dispatch({ type: "LIGHT" }); {/* change to ligh mode  */}

  dispatch({ type: "DARK" });  {/* change to dark mode  */}

  dispatch({ type: "SYSTEM" }); {/* change to os theme mode  */}

```



