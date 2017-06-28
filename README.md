# Whatsapp simulator

## Installation
```
npm install
```

## Running
```
npm run dev
```

Open browser at `http://localhost:1337/`

## Deploying
```
npm run build
```

Files are compiled into `./dist`.

## Adding new chats
Duplicate i.e. `pandas.jade` and rename to `foo.jade` add the following to `webpack.config-helper.js`:

```
new HtmlWebpackPlugin({
	filename: 'foo.html',
	template: "jade!./src/foo.jade"
}),
```

Optionally, add link to `index.jade`.