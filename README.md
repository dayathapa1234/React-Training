# React-Training

## Creating a React Application
Creating a react application in the current folder:
```
npx create-next-app .
```
To run the application on http://localhost:3000/:
```
npm start
```

## TailWind Setup

In `tailwind.config.js`:
```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
    "node_modules/flowbite-react/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
In `index.css`:
```css
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}

@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Chakra UI Setup
In `index.js`, we need to wrap the `<App />` component with `ChakraProvider` (https://chakra-ui.com/getting-started):
```js
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import { ChakraProvider } from '@chakra-ui/react'

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <ChakraProvider>
    <App />
    </ChakraProvider>
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```

## Calling the Button Component

```js
import logo from './logo.svg';
import './App.css';
import Button from './Components/Button/Button';

function App() {
  return (
    <div className='App h-[100vh] flex justify-center'>
      <div className="flex flex-col justify-center">
          <Button/>
      </div>
    </div>
  );
}

export default App;
```
- `className` is the same as `class` in html
- The `App` class is using the css file './App.css'
- `h-[100vh]` is the same as `height: 100vh;` and `flex` is same as `flex` and so on ...(https://tailwindcss.com/docs/display)
- The `<Button/>` is calling the Button component from Button.jsx

## Button Component

