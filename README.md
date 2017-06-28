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

## Editing chats
One simple message consists of the following:

```
article
  section.message.person1
    h1 Infoji-Bot 🤖
    p Congratulations!
    span 12:27
```

The message can have the following classes to modify the **color of the author**:

```
.person1
…
.person20
```

The default color and `.person1` have the same color.

To change the **side of the message** the class `.right` can be used.

If **two or more messages** of one person follow each other directly every message except the first one requires the class `.continuous` and the last one additionally `.arrow`. Only the first message has a `h1` to hold the author’s name.

If a message holds a **longer text** it should have the class `.wider`.

if a message contains **only one emoji** it requires the class `.size1`, for two emojis `.size2` and three emojis have `
.size3`.

### Author
The author is placed within the `h1`-tag. It should only appear in the first message if the author posts multiple continuous messages. The author can also hold emojis.

### Message
The whole message is placed inside a single `p`-tag. Emojis require an additional `em`-tag. Between text and emojis there should be a space. An example would be:

```
p In 2004, Queen Beatrix 
  em 👑 
  | of the 
  em 🇳🇱 
  | signed the first equal marriage bill.   
  em 😊
```

### Time
The time can have an additional `.up`-class to place it on the same height as the message`s bottom. This might be required if the last line of the text is shorter.