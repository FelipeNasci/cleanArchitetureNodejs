## NodeJs, Typescript, TDD, Clean Architeture and SOLID
### Course teached by Rodrigo Manguinho

## GIT

### List configurations

```
git config --list
```

### Select edit code preferred for configurations

```
git config --local core.editor code
```

### Edit configurations (with your editor preferred)

```
git config --local --edit
```

### Creating a shorcut

```
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
	editor = code --wait

[alias]
	s = !git status -s
	c = !git add --all && git commit -m
	l = !git log --pretty=format:'%C(blue)%h%C(red)%d %C(white)%s - %C(cyan)%cn, %C(green)%cr'

```

**[More Info](https://git-scm.com/docs/pretty-formats)**

### [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)


### Libraries


#### git-commit-msg-linter - commit pattern
```
yarn add git-commit-msg-linter -D
```

#### typescript

```
yarn add typescript @types/node -D
```

#### eslint-config-standard-with-typescript - typescript standard
```
npm install --save-dev eslint@7 eslint-plugin-standard@4 eslint-plugin-promise@4 eslint-plugin-import@2 eslint-plugin-node@11 @typescript-eslint/eslint-plugin@2 eslint-config-standard-with-typescript
```

#### husky - Define git Hooks
```
yarn add husky -D
```

lint-staged - Validations commits in stage area only
```
yarn add lint-staged -D
```

#### Tests
* Jest - lib of tests
* @types/jest - Types for Jest
* ts-jest - compilation de ts to js, jest only.

```
yarn add jest @types/jest ts-jest -D
```

```
yarn global add jest
```

```
jest --init
```



### Typescript Configuration

**tsconfiguration.json**

```
{
    "compilerOptions": {
        "outDir": "./dist",
        "module": "commonjs",
        "target": "ES2019",
        "esModuleInterop": true,
        "allowJs": true,
    }
}
```

### ESlint configuration

**.eslintrc.json**
```
{
    "extends": "standard-with-typescript",
    "parserOptions":{
        "project": "./tsconfig"
    }
}
```

### Husky configuration

**.huskyrc.json**
```
{
    "hooks":{
        "pre-commit": "lint-staged"
    }
}
```

### Lint-staged configuration

**.lintstagedrc.json**
```
{
    "*.ts":[
        "eslint 'src/**' --fix" ,
        "npm run test:staged"
    ]
}
```

### Jest configuration


** jest.config.js **
```
module.exports = {
    roots:['<rootDir>/src'],
    collectCoverageFrom: ['<rootDir>/src/**/*.ts'],
    coverageDirectory: "coverage",
    testEnvironment: "node",
    transform: {'.+\\.ts$': 'ts-jest'},
  };
  ```

** Scripts **

```
"scripts": {
    "test": "jest",
    "test:staged": "jest --passWithNoTests"
},
```