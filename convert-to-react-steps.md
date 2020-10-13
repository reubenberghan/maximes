# Steps to convert this to a React SPA

> **NOTE:** this webpage does not necessarily need to be a React SPA and is fine as a static page. However in the interests of learning React.

Looking at the `sass` directory a React application could follow a similar structure.

```
maximes
  | - src
  |   | - components
  |   |   | - Button.jsx
  |   |   | - Card.jsx
  |   |   | - FeatureBox.jsx
  |   |   | - etc.
  |   | - layout
  |   |   | - Footer.jsx
  |   |   | - Header.jsx
  |   |   | - Layout.jsx
  |   | - etc.
  | - etc.
```

A useful exercise is to look mock out the page / site on some paper and put boxes around the natural groupings of UI elements. This can be at each level of the site. For example at the page / app level down through the layout(s) of the page(s) which include components like header, footer, and nav. Down to the smaller UI elements like buttons, cards, links, headings etc.

By conceptually breaking down the individual components that will make up the application it will hopefully make more sense how to slice out the styling from the static page for the respective components.

> **NOTE:** there isn't really a wrong / right answer with how slice this up so no need to worry about getting it "right" at the start. The main thing is to come up with a list of components that need to be built so you can get started. Remember you can always change things as you go.

## Create the app

It will probably be easier to create the app as a separate project and port across the code needed.

To initialise the react app run the following in a terminal.

```bash
npx create-react-app maximes-react
```

This will create a react project in a directory called `maximes-react`.

`create-react-app` is going to provide all of the build and tooling config which allows you to just worry about adding your components and builiding the app.

## Clean up boilerplate and setup structure

We can now also adjust the starting structure and boilerplate that comes out of the box with `create-react-app`.

Lets add `components` and an `App` directories under `./src`.

```
maximes-react
  | ...
  | - src
  |   | - components
  |   |   | - App
  | ...
```

From the `src` directory we can move the `App.js` and the `App.css` files into the `./src/components/App`.

> **NOTE:** as a starting point this is a pretty standard way to structure a React app. Inside a `components` directory that contains sub-directories for each component and then the component file and styles file.

Also remember to update the `App` import line in the `./src/index.js` entry file. This will need to be from `import App from './App';` to `import App from './components/App/App';`.

We can now delete the `./src/App.test.js` and  `./src/logo.svg` files as these won't be needed.

At this point we can clean out the boilerplate code from the `App.js` and `App.css` files and replace it with a simple "hello world" (or whatever you want basically).

```js
/* ./src/components/App/App.js */
import React from 'react';
import './App.css';

const App = () => <div className="App">Hello world.</div>;

export default App;
```

```css
/* ./src/components/App/App.css */
.App {
  text-align: center;
}
```

> **NOTE:** `create-react-app` can be configured to [handle Sass stylesheets out of the box](https://create-react-app.dev/docs/adding-a-sass-stylesheet) by simply adding `node-sass` to the project and updating the the `.css` files to `.scss`.

At this point you should be good to start implementing the components that you figured were needed in the initial exercise.
