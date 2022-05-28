# nuxt-multibyte-url-demo

This is a demonstration of behaviour that fails to loading of payload.js at pages that URL includes multibyte characters.

This branch is a fixed version by a patch `./patches/@nuxt+vue-app+2.15.8.patch`.
`patch-package` applies the patch.

## Reproduction steps

```sh
git clone -b fix-by-patch https://github.com/nahcnuj/nuxt-multibyte-url-demo.git
cd nuxt-multibyte-url-demo
npm i
npm run generate
npm run start
```

- http://localhost:3000/hoge/english/ works well, and
- http://localhost:3000/hoge/日本語/ also works

## Structure

- `nuxt.config.js`: `generate.routes` defines routes, passing payload
- `pages/hoge/_id.vue`: the template uses data from payload in `asyncData`, set dummy data in `data` for type inference

## Initial configuration

```console
$ npm init nuxt-app nuxt-multibyte-url-demo

create-nuxt-app v4.0.0
✨  Generating Nuxt.js project in nuxt-multibyte-url-demo
? Project name: nuxt-multibyte-url-demo
? Programming language: TypeScript
? Package manager: Npm
? UI framework: None
? Nuxt.js modules: (Press <space> to select, <a> to toggle all, <i> to invert selection)
? Linting tools: (Press <space> to select, <a> to toggle all, <i> to invert selection)
? Testing framework: None
? Rendering mode: Universal (SSR / SSG)
? Deployment target: Static (Static/Jamstack hosting)
? Development tools: (Press <space> to select, <a> to toggle all, <i> to invert selection)
? What is your GitHub username? nahcnuj
? Version control system: Git
```
