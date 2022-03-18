# pwa-ba

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

# PWA - Langeland kommune


<h5 align="center"><img width="300" src="https://langelandkommune.dk/Files/Images/Langeland.svg" alt="logo">
  <p>This is a Progress webapplication build for LangeLand kommune</p>
</h5>



## Table of Contents
* How to run the app
* How to use the PWA - app
* Features
* Future Features
* How to contribute
* What the prototype looks like

## How to run the app
1. Either a git client or downlaod the app and open the folder in the cli
2. Install all dependencies using the `npm install` command
3. Start the web server using the `npm run dev` command. The app will be served at http://localhost:8080/
4. Go to http://localhost:8080/ and get started

## How to use the PWA - PWA - Langeland kommune
The app is pretty simple. You login depending on your which department you work at and then find a specific user by search or through filter.
1. Login.
2. Choose a categori or find a specific user through search.

## Features

### getCommands
```
export interface EditorCommand {
  name: string;
  description: string;
  aliases: string[];
  keyboardShortcut: string[]
  command(): void
  icon: string;
  tags: string[];
}
``` 

**aliases** is a list of alternative names to commands, which makes the searching better. For example can bold have the alias heavy, when doing a search for heavy bold will appear.

**KeyboardShortcut** is an array of buttons that form a shortcut

**Command()** is a function which calls a specific editor command

**tags** is used to filter a list of **commands** based on which menu should display them.

### searchCommands
```
export const searchCommands = (
  search: string,
  tag?: string
): EditorCommand[] => {
  const filtered = getCommands().filter(
    x =>
      (x.name.toLocaleLowerCase().includes(search) ||
        x.aliases.some(y => y.includes(search))) &&
      (tag ? x.tags.some(z => z.includes(tag)) : true)
  );

  return filtered;
};
```

## Future Features
1. Documentation
2. Test
3. Customization - templates
4. Table of Contents
5. Collaborative editing

## How to Contribute
1. Clone repo and create a new branch $ git checkout https://github.com/soonh1/pwa-ba.git -b name for new branch
2. Make changes and test
3. Sumbit Pull Request with comprehensive description of changes

## Why should Langeland kommune use this app?
The basic idea is to digitize physical information cards for a mobile application,
in which the access to this information becomes easily accessible to, for example, nurses and
social and health workers.

* Should ease the workflow for health workers.
* Provides an overview.
* Intuitive to work with. 

## What the prototype looks like
![Prototype image](https://github.com/soonh1/pwa-ba/blob/main/src/assets/prototype-pwa.PNG)

