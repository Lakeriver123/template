Webpack

1.  npm init -y

2.  npm install --save-dev webpack webpack-cli

3.  npm install --save-dev css-loader style-loader

4.  npm install --save-dev file-loader

(Note: I am uncertain if i need to manually make folders in /dist
if I do the folders would be either bundle.js or index.html)

5.  npm install --save-dev html-webpack-plugin
6.  manually create webpack.config.js and paste in the below code:

const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
entry: './src/index.js',
output: {
filename: 'bundle.js',
path: path.resolve(\_\_dirname, 'dist'),
},
module: {
rules: [
{
test: /\.css$/i,
         use: ['style-loader', 'css-loader'],
       },
       {
         test: /\.(png|jpg|jpeg|gif|svg)$/i,
type: 'asset/resource',
loader: 'file-loader',
options: {
name: '[name].[hash].[ext]',
outputPath: 'images',
},
},
],
},
plugins: [
new HtmlWebpackPlugin({
template: './src/index.html',
}),
],
mode: 'development', or 'production'
};

// Prettier & Lint (If confused, ask ChatGPT)

// 1. npm install --save-dev prettier

// 2. npm install eslint --save-dev

// 3. npx eslint --init to generate a eslint.config.mjs

// 4. npm install --save-dev eslint-config-prettier eslint-plugin-prettier

// 5. copy code below into eslint.config.mjs

import globals from "globals";
import pluginJs from "@eslint/js";
import prettierConfig from "eslint-config-prettier";
import prettierPlugin from "eslint-plugin-prettier";

export default [
{
files: ["**/*.js"],
languageOptions: {
globals: globals.browser,
ecmaVersion: "latest",
sourceType: "module",
},
plugins: {
prettier: prettierPlugin,
},
extends: ["prettier"],
rules: {
...prettierConfig.rules,
"prettier/prettier": "error",
},
},
pluginJs.configs.recommended,
];

7. hopefully everything works.

// 7. Lots of customization available
// 1. .prettierignore or .eslintignore file allows you to ignore folders or file types
// 2. Can add "scripts": {} in package.json to change name for eslint and prettier commands
// 3. .prettierrc allows you to configure settings like {
// {
// "singleQuote": true,
