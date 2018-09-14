## Front-End Starter

### Features

#### Webpack 4 and Webpack Dev Server

Comes with a pre-configured Webpack 4 setup with webpack-dev-server. 
Please note, source maps have been turned on so this will need to be
configured further for a production environment

Run `yarn start` to run the dev server

### Usage

#### Creating a new page

1. Add your new page. For example, `about.html` to the `/dist/templates` directory
without any css or js files

2. Add the following to the already configuredd `webpack.config.js`:

```js

.......

plugins: [
	new HtmlWebpackPlugin({ 
		filename: 'about.html',
		template: './dist/templates/about.html'
	}),
	
.......

	new FileManagerPlugin({
		onEnd: {
			move: [
				{
					source: 'dist/about.html',
					destination: './about.html'
        },
			]
		}
	})
]

.......

```

3. Upon running `yarn build` or `npm run build`, you should see your new `about.html` file
in the root directory