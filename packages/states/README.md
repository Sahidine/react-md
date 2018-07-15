# @react-md/states
A package for managing the different interaction states on elements like hover, focus, and pressed

This source code of this package can be found at: https://github.com/mlaursen/react-md/tree/next/packages/states

<!-- TOC_START -->
<!-- TOC_END -->

## Installation
```sh
$ npm install --save @react-md/states
```

#### Updating Sass to include `node_modules`
If you want to include the SCSS styles for `@react-md/states`, you will need to update your Sass compiler to include the `node_modules` in the paths as well as add [autoprefixer](https://github.com/postcss/autoprefixer) to handle multiple browser compatibility.

> If you are using [create-react-app](https://github.com/facebook/create-react-app), the autoprefixer is already included.

#### webpack
```diff
 {
   test: /.scss$/,
   use: [{
     loader: 'style-loader',
     options: { sourceMap: true },
   }, {
     loader: 'css-loader',
     options: { sourceMap: true, importLoaders: 2 },
   }, {
     loader: 'postcss',
     options: { sourceMap: true },
   }, {
     loader: 'sass-loader',
     options: {
       sourceMap: true,
+      includePaths: [
+        './node_modules', // or whatever relative path it is to node_modules
+      ],
     },
   }],
 }
```

#### create-react-app and node-sass-chokidar
```diff
   "scripts": {
+    "build-css": "node-sass-chokidar --include-path ./node_modules src/ -o src/",
+    "watch-css": "npm run build-csss && npm run build-css -- --watch --recursive"
   }
```

### Styles
Including all the base styles can be done by either importing the styles file from the `dist` folder or importing the helpers file and using the mixin `react-md-states`:

```scss
// This import will generate styles by default.
@import "@react-md/states/dist/styles";
```

or

```scss
// This import only includes all the utility variables, mixins, and functions.
@import "@react-md/states/dist/states";

// Once everything has been imported, you can generate the styles with the following mixin
@include react-md-states;
```

If you would like to just import all the utility variables, mixins, and functions:
```scss
@import "@react-md/states/dist/states";

// Any custom styles that use the utilities
```


## Usage
<!-- PROPS_START -->
<!-- PROPS_END -->


<!-- SASSDOC_START -->
<!-- SASSDOC_END -->
