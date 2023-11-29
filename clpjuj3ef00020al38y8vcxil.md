---
title: "Blazingly fast CLI with Bun 🚀"
seoTitle: "CLI app with Bun"
seoDescription: "Build a blazingly fast CLI app using Bun"
datePublished: Wed Nov 29 2023 14:12:21 GMT+0000 (Coordinated Universal Time)
cuid: clpjuj3ef00020al38y8vcxil
slug: blazingly-fast-cli-with-bun
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701267053539/06c04e6f-e256-48b5-94e6-6ecc3b51cfa6.png
tags: javascript, programmer, bun

---

Bun is freshly out of the oven (Seriously, the parent company’s name is **Oven**!) and it is a new JavaScript runtime and **not a framework!** It is really promising and most importantly **Blazingly fast!** I tried it out and it is fantastic in my opinion. So In this article, we will look into how to create a simple note-taking CLI using bun. The idea here is to give a glimpse of the core utils that Bun comes with, the package management, and the most hyped-up factor which is the speed.

## What’s up with Node.JS?

So Node.JS came in and revolutionized the world of JavaScript. All the frameworks’ existence is because of Node.JS but as days passed, there were a lot of problems as well with it. The major one that I could think of is NPM and Node modules. In a complex codebase, the `npm i` script will take an eternity to install all the packages. Also, NodeJS is built on top of the **V8 engine** developed by Google. Now I don’t know the metrics to calculate the performance bottlenecks but Bun came out and crushed NodeJS concerning performance. Bun is written in the **Zig** programming language and written on top of the **JavaScript core engine** developed by Apple. This engine is known for its performance but it is a little bit hard to work with.

## Advantages of Bun:

1. Bun is a **drop-in replacement** for node. Most of the node’s core utils work in a bun except utils that are close to the V8 engine.
    
2. Bun offers a great developer experience by being a toolkit for JavaScript including a **test runner, debugger, bundler and package manager**, unlike NodeJS which needs 3rd party packages to achieve all of them.
    
3. Last but not the least, **Speed**. Right from executing a script to installing a package, Bun is very fast.
    

### Features that Bun offers

1. Supports **TypeScript** out of the box, no need to configure ts-node or any other things like that anymore.
    
2. Supports **ES Modules and CommonJS** are both in the same file, no need to create `mts` or `cts`.
    
3. Comes with a **Test runner**, and **debugger** to make things simple.
    
4. Support for **JSX.**
    
5. **Environment variables** are loaded without any need for the `dotenv` package.
    
6. It has a built-in HTTP server, Web socket, SQLite database, and so on.
    

## Should you dump Node.JS?

Although bun seems promising, It is too soon to say. Bun 1.0 is already out and people have started adopting it. But Node.JS is not going anywhere. Similar to this situation, earlier another runtime came out called **Deno**, by the same person who created Node and deeply regretted creating it. Like the meme, even though NodeJS revolutionized the world, The programmer who created it would never be satisfied with his code. Till now Deno has never been replaced or not even in a competing stage with node. It co-exists, and it has a good ecosystem. It is healthy to have Bun as well in the race. The JavaScript ecosystem is so advanced that after the framework race, we are now in the runtime race.

## Let’s build a CLI!

Now, Let’s create a cutting-edge CLI app that can take notes for you and we will write this in Bun and explore the features that Bun is offering.

In this CLI app, we will cover the following.

* The SQLite package that Bun ships in with.
    
* Installing NPM packages.
    
* Creating a CLI and processing the arguments and much more.
    

Even if you don’t want to follow along, just read the article and I promise you will learn something new. Before starting, you can find the finished project in this GitHub repository.

%[https://github.com/balamurugan16/bun-cli-app] 

---

### Step 0 - Creating the project:

To kick things start, create a new folder, navigate into it, and run the following command.

```plaintext
mkdir bun-cli && cd bun-cli
bun init -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701264519305/aeb2706b-a6a7-46de-83b4-233b27eee402.png align="center")

This is similar to `npm init` but here, bun scaffolds are a basic application, setting up a great place to start our journey. It will generate a few files which would look familiar.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701263988795/60b47114-2e81-4da3-ae45-e7fd1dc38b2b.png align="center")

Bun, as I said is a drop-in replacement for Node.JS so It supports `node_modules`. The `bun.lockb` file is similar to the `package-lock.json` or similar files for the other package manager. Again, bun is a package manager in itself so no external package managers are required! The `index.ts` file is the entry point of this application though you can change that in the `package.json`. If you execute the `index.ts` file using `bun index.ts` command, you can see the output printed in the terminal without any build step for typescript. As I said, It just works!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701264332493/200cbde9-d8d9-4d48-8976-dc0c77941b58.png align="center")

---

### Step 1 - Registering our CLI

Since we are building a CLI application, We have to assign a name for our CLI and register it so that instead of running `bun index.ts` every time, we can run the CLI instead.

To do this, first, we need to name our CLI, for this demo, I will call it **note.** (Yes I have patented the name!). Now open your `package.json` and add this piece of code.

```json
"bin": {
    "note": "./index.ts"
 },
```

**“bin”** means binary and here we are specifying a CLI name as the key and the subsequent file to be executed whenever this command is called.

Next, you have to add this line as the first line in the `index.ts` file.

```typescript
#! /usr/bin/env bun
```

This line is called a **Shebang!** This line tells the shell to use bun as the runtime when the CLI is invoked in the terminal

Next, you have to execute 2 commands

```json
bun link
bun link <project_name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701264714008/9ff936a1-0276-47a7-b083-9c909f24e41b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701264801376/7deddb2f-4528-4dcc-8bdc-6cff453e5267.png align="center")

The initial command will register your Bun project in the global scope. The second command will install the CLI package into the global bun binaries so that It can be used anywhere in the command line. The project name can be taken from the name property of the `package.json` file.

To test this, we can run our command `note` and see the result.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701265008004/12bba4fc-f7e9-44c0-8b58-2c024efed19a.png align="center")

---

### Step 2 - Installing the packages

Create a `src` folder, this is where all of our source code will reside. After that run the following command to install a few dependencies.

```plaintext
bun add yargs
bun add -D @types/yargs
```

`yargs` is a library that will let you build great CLI apps. It will automatically do **CLI parsing, help documentation,** etc.

---

### Step 3 - Setting up the “yargs” library

Now create a file called `command.ts` and paste the following code.

```typescript
import yargs from "yargs"
import { hideBin } from "yargs/helpers"

yargs(hideBin(process.argv))
  .command(
    "new <note>",
    "Creates a new Note",
    (yargs) => yargs.positional("note", {
      description: "The content of the note",
      type: "string",
    }),
    (argv) => console.log(argv.note)
  )
	.parse()
```

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">I’ll call this the command or <strong>controller layer</strong>.</div>
</div>

Here, we are declaring a command called **“new”** that takes in an argument and prints it out. Later we will be persisting this info in a database.

Now import this file into the main `index.ts` file.

```typescript
#! /usr/bin/env bun
import "./src/command.ts";
```

Now run the command `note new "walk the dog"` in the terminal (you can give any note you want in quotes) and you can see it getting printed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701265343952/b4d60cf0-90a3-4b10-aa01-628d09124b38.png align="center")

---

### Step 4 - Setting up the database:

Let’s persist this value in a database. Bun comes in with a built-in SQLite database which is again “**Blazingly fast”.** To implement this, let’s create a new file called `db.ts` and paste the following code.

```typescript
import { Database } from "bun:sqlite"

const db = new Database("../db.sqlite")
db.exec("PRAGMA journal_mode = WAL;")

export const note_table_query = db.prepare(`CREATE TABLE IF NOT EXISTS note (
  note_id INTEGER PRIMARY KEY AUTOINCREMENT,
  note TEXT NOT NULL
)`)

export function create_new_note(note: string): void {
  const query = db.query(`INSERT INTO note (note) VALUES (?)`);
  query.run(note);
}
```

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">I’ll call this the <strong>Repository layer </strong>as it is interacting with the database.</div>
</div>

Also, create a file called `db.sqlite` file in the root of your project. This file will be your app’s database.

So in this file, you can see a bunch of things going on, Let me explain.

To interact with an SQL database, first, the database table should be created, So the query for that is created which will be executed in the `index.ts` file. Then the `create_new_note` function is responsible for the insertion of a new row into the table. Bun gives a great API to interact with this database. You can create a query and execute it whenever you want. For Example, in the `create_new_note` function, The query is first created and then executed. I like this approach.

Next import the `note_table_query` method in the `index.ts` file and execute the query.

```typescript
#! /usr/bin/env bun
import "./src/command.ts";
import { note_table_query } from './src/db';

note_table_query.run();
```

As you can see here, The bun’s SQLite package first creates the Query and then exposes functions to execute the query. Here we have a run method that runs the query. There are methods like `all` that are used with a `SELECT` query that will return all the rows that are returned. Check out the documentation for more information.

%[https://bun.sh/docs/api/sqlite] 

---

### Step 5 - Connecting the controller with the repository layer:

Now let’s persist the information that is received from the terminal into the database. I will create an intermediate layer that will do the business logic because if the code is written in the `command.ts` file, it will look ugly as yargs primarily takes in a lot of callbacks.

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">I will call this layer the <strong>Service layer</strong></div>
</div>

Create a file called `handler.ts` inside the `src` directory and paste the following code.

```typescript
import { create_new_note } from "./db";

export function create_note_handler(note: string) {
	try {
		create_new_note(note);
		console.log(`${note} added successfully`);
	} catch (err) {
		console.error(err);
		console.error("Oops, Error!");
	}
}
```

So in the above code, we are importing the `create_new_note` function from the repository layer and passing the string that we received as an argument from the user. We are also doing a bit of error handling here.

So now we can call this function in our service layer in the controller layer (i.e. `command.ts`) as shown below.

```typescript
import yargs from "yargs";
import { hideBin } from "yargs/helpers";

const { create_note_handler } = require("./handler");

yargs(hideBin(process.argv))
	.command(
		"new <note>",
		"Creates a new Note",
		(yargs) =>
			yargs.positional("note", {
				description: "The content of the note",
				type: "string",
			}),
		(argv) => create_note_handler(argv.note as string),
	)
	.parse();
```

As you can see, in the callback, I am calling the function we created in the service layer. Also, note that I am importing the `create_note_handler` method using the CommonJS syntax and it will work out of the box.

So now when we execute this app, we can store the data in the database.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701266031141/dd8a425f-aa7f-4c4f-9d7e-f2eef4eb891a.png align="center")

With all these steps you have created your Command Line Interface in Bun. You can check the repository where I have implemented other CRUD functionalities. You can extend and make this application extensive. With all of these covered, we are at the end of this article.

%[https://github.com/balamurugan16/bun-cli-app] 

### Conclusion

The JavaScript ecosystem is fast evolving and we are seeing new libraries, frameworks and now even runtimes getting released. It could be overwhelming but at the same time quite interesting. Bun is a promising tool and It is worth checking out. I have used bun in some of my React and Svelte projects and I haven't had any complaints yet, So I'd recommend you also to use it. Try to convince your boss why your project should also migrate to Bun for no reason and get a 10x raise in your next appraisal! (Sarcasm!)