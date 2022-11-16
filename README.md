# Dotfiles/Setting files are used for mostly JS project.

---

## 1. [Engine Locking](.npmrc)

- `nvmrc` - Will tell other uses of the project which version of Node is used
- `npmrc` - Will tell other users of the project which package manager is used

## 2. Code Formatting and Quality Tools

Those tools will keep the code style consistent across all team members.

- `eslint` - For best practices on coding standards
- `prettier` - For automatic formatting of code files

## 3. Git Hooks

We cannot beleive anyone even include ourself. So everything needs to be verify automatically at first stage. So Husky is best tool for this.

- Husky - a tool for running scripts at different stages of the git process, for example add, commit, push, etc.
- To install Husky

```js
    yarn add -D husky

    npx husky install
```

After that it will create .husky forder that contains all hooks command inside, for example pre-commit, pre-push ...

- After that, we need to add hook command executed to .husky using `lint-staged` or `pretty-quick`. To install `lint-staged`:

```js
    npm i -D lint-staged

    // Inside package.json
    "lint-staged":{
    "**/*.{js,jsx,ts,tsx}":[
      "prettier --write",
      "eslint --fix",
      //"git add"
    ]
  }
```

We could add `lint-staged` command to `package.json` file or custom in `.lintstagedrc.js` file

## 4. VS Code Configuration

We need some VScode setup to make it helps us run Eslint and prettier automatically. Otherwise, we have to to run `yarn lint` and `prettier --write` normally by hand.

Create a directory in the root of project called `.vscode` and inside a file called `settings.json`. This will be a list of values that override the default settings of your installed VS Code.
`.vscode/settings.json`

## 5. Debugging

Inside of your .vscode directory create a `launch.json` file: `.vscode/launch.json`
