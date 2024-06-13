// webpack

// 1. npm init -y

// 2. npm install --save-dev webpack webpack-cli

// 3. npm install --save-dev css-loader style-loader

// (image loader)
// 4. npm install --save-dev file-loader
// Note: I am uncertain if i need to manually make folders in /dist
// if I do the folders would be either bundle.js or index.html
// 5. npm install --save-dev html-webpack-plugin

// config file
// const path = require('path');
// const HtmlWebpackPlugin = require('html-webpack-plugin');

// module.exports = {
// entry: './src/index.js',
// output: {
// filename: 'bundle.js',
// path: path.resolve(\_\_dirname, 'dist'),
// },
// module: {
// rules: [
// {
// test: /\.css$/i,
//         use: ['style-loader', 'css-loader'],
//       },
//       {
//         test: /\.(png|jpg|jpeg|gif|svg)$/i,
// type: 'asset/resource',
// loader: 'file-loader',
// options: {
// name: '[name].[hash].[ext]',
// outputPath: 'images',
// },
// },
// ],
// },
// plugins: [
// new HtmlWebpackPlugin({
// template: './src/index.html',
// }),
// ],
// mode: 'development', // or 'production'
// };

// Prettier & Lint (If confused, ask ChatGPT)

// 2. npm install --save-dev prettier

// 3. npm install eslint --save-dev

// 4. npx eslint --init to generate a eslint.config.mjs

// 5. npm install --save-dev eslint-config-prettier eslint-plugin-prettier

// 6. Update ESLint config to extend prettier
// add: extends: ["prettier"], above rules:

// 7. Lots of customization available
// 1. .prettierignore file allows you to ignore folders or file types
// 2. Can add "scripts": {} in package.json to change name for eslint and prettier commands
// 3. .prettierrc allows you to configure settings like {
// {
// "singleQuote": true,
