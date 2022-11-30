
### Modules needed
    
Run
```sh
./install-npm-modules.sh
```

### Scripts needed for package.json
```json
{  
  "scripts": {
    "build:aws-exports-es5": "tsc --skipLibCheck --allowJs --lib 'es5' --module 'commonjs' --target 'es5' --moduleResolution 'node' --outDir . src/aws-exports.js",
    "precypress:open": "yarn build:aws-exports-es5",
    "precypress:run": "yarn build:aws-exports-es5",
    "cypress:open": "cypress open",
    "cypress:run": "cypress run ",
    "tsnode": "ts-node -P tsconfig.tsnode.json",
    "test:provisionCognitoUsers": "yarn tsnode scripts/provisionCognitoUsers.ts",
  },
  "eslintConfig": {
    "env": {
      "cypress/globals": true
    },
    "extends": [
      "react-app",
      "plugin:prettier/recommended",
      "plugin:cypress/recommended"
    ],
    "plugins": [
      "cypress",
      "prettier"
    ],
    "rules": {
      "no-unused-expressions": 0
    }
  },
  "prettier": {
    "trailingComma": "es5",
    "printWidth": 100,
    "endOfLine": "auto"
  },
}
```
