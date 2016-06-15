React Stuff : First App

npm init 

npm install --save react@0.14.3
npm install --save react-dom@0.14.3
npm install --save-dev babel-core@6.3.13 babel-loader@6.2.0 babel-preset-es2015@6.3.13 babel-preset-react@6.3.13

mkdir public -> cd public -> touch index.html 

Initial Index.html page: 

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>React Github Notetaker</title>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
</head>
<body>
  <div id="app"></div>
  <script src="bundle.js"></script>
</body>
</html>

touch webpack.config.js 
npm install webpack -g 

webpack.config.js 

module.exports = {
entry: "./app/components/Main.js",
output: {
filename: "public/bundle.js"
},
module: {
loaders: [
{
test: /\.jsx?$/, 
exclude: /(node_modules|bower_components)/,
loader: 'babel',
query: {
presets: ['react', 'es2015']
}
}
]
}
};

mkdir app -> mkdir components -> touch Main.js 

Main.js 

var React = require('react');
var ReactDOM = require('react-dom'); // render on client instead of server 

var Main = React.createClass({
render: function(){
return(

<div>
Hello World
</div>

)
}
});

ReactDOM.render(<Main />, document.getElementById('app')); 

webpack -w 
open index.html 
—————————————————————————————————————







