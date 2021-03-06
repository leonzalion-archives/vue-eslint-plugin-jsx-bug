# Vue ESLint Plugin JSX Bug

Install dependencies:
```shell
npm install
```

Running the app works as expected:

```shell
npm run dev
```

Output in the browser:

![works](works.png)

But linting the project gives the following error:

```shell
npm run lint
```

![parsing error](parsing-error.png)

Linting the equivalent code in a JSX file works fine:

```shell
npm run lint:jsx
```

![parsing works](parsing-works.png)

However, linting works after applying [a very hacky patch](https://github.com/leonzalion/vue-eslint-plugin-jsx-bug/blob/main/patches/typescript%2B4.6.3.patch) to the TypeScript compiler:

```shell
npx patch-package
num run lint
```

![parsing works patch](parsing-works-patch.png)


