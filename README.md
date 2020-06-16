## Geting started project.
1. first create new aplication with typescript.
```create-react-app primeiro-projeto-react --template=typescript```
2. install eslint.
   - run comand for add module in file project.
     - ```yarn add eslint -D```
   - modify ```package.json```
     - exclude lines.
       ```json
        "eslintConfig": {
          "extends": "react-app"
        },
       ```
   - run initialize eslint.
     - ```yarn eslint --init```
   - The options.
     - ? How would you like to use ESLint? To check syntax, find problems, and enforce code style
     - ? What type of modules does your project use? JavaScript modules (import/export)
     - ? Which framework does your project use? React
     - ? Does your project use TypeScript? Yes
     - ? Where does your code run? Browser
     - ? How would you like to define a style for your project? Use a popular style guide
     - ? Which style guide do you want to follow? Airbnb: https://github.com/airbnb/javascript
     - ? What format do you want your config file to be in? JSON
     - Checking peerDependencies of eslint-config-airbnb@latest
     - ? The style guide "airbnb" requires eslint@^5.16.0 || ^6.8.0. You are currently using eslint@7.2.0.
     - Do you want to downgrade? No
     - ? Would you like to install them now with npm? No
   - Copy comands for instalations dependencys in development
     - ```yarn add eslint-plugin-react@^7.19.0 @typescript-eslint/eslint-plugin@latest eslint-config-airbnb@latest eslint@^6.8.0 eslint-plugin-import@^2.20.1 eslint-plugin-jsx-a11y@^6.2.3 eslint-plugin-react-hooks@^2.5.0 @typescript-eslint/parser@latest -D```
   - Eslint ignore files
     - created file in project ```.eslintignore``` with
       - ```**/*.js node_modules build```
   - Eslint configuration
     ```json
     {
      "env": {
        "browser": true,
        "es2020": true
      },
      "extends": [
        "plugin:react/recommended",
        "airbnb",
        "plugin:@typescript-eslint/recommended"
      ],
      "parser": "@typescript-eslint/parser",
      "parserOptions": {
        "ecmaFeatures": {
          "jsx": true
        },
        "ecmaVersion": 11,
        "sourceType": "module"
      },
      "plugins": [
        "react",
        "react-hooks",
        "@typescript-eslint"
      ],
      "rules": {
        "react-hooks/rules-of-hooks":"error",
        "react-hooks/exhaustive-deps":"warn",
        "react/jsx-filename-extension":[1,{"extensions":[".tsx"]}],
        "import/prefer-default-export":"off"
      }
     }
    ```
   - add eslint typescript resolver
     - ```yarn add eslint-import-resolver-typescript -D```
     - ```json
       {
         "settings": {
          "import/resolver":{
            "typescript":{}
          }
        }
       }
   - add prettier with devDependencies
     - ```yarn add prettier eslint-config-prettier eslint-plugin-prettier -D```
   - reorganized eslintrc.json file
     - ```json
       {
        "env": {
          "browser": true,
          "es2020": true
        },
        "extends": [
          "plugin:react/recommended",
          "airbnb",
          "plugin:@typescript-eslint/recommended",
          "prettier/@typescript-eslint",
          "plugin:prettier/recommended"
        ],
        "parser": "@typescript-eslint/parser",
        "parserOptions": {
          "ecmaFeatures": {
            "jsx": true
          },
          "ecmaVersion": 11,
          "sourceType": "module"
        },
        "plugins": [
          "react",
          "react-hooks",
          "@typescript-eslint",
          "prettier"
        ],
        "rules": {
          "prettier/prettier":"error",
          "react-hooks/rules-of-hooks":"error",
          "react-hooks/exhaustive-deps":"warn",
          "react/jsx-filename-extension":[1,{"extensions":[".tsx"]}],
          "import/prefer-default-export":"off",
          "import/extensions":[
            "error",
            "ignorePackages",
            {
              "ts":"never",
              "tsx":"never"
            }
          ]
        },
        "settings": {
          "import/resolver":{
            "typescript":{}
          }
        }
       }
       ```
     - Create file prettier.config.js with content
       ```js
       module.exports = {
        singleQuote:true,
        trailingComma:'all',
        allowParens:'avoid'
       }
       ```






This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).
