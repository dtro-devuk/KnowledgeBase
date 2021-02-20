# Next JS Knowledgebase from, Feb 2021

| Title                       | Author     | Version | Group | Sub-Levels |
| --------------------------- | ---------- | ------- | ----- | ---------- |
| _Nextjs Knowledgebase Page_ | dtro-devuk | 1.0     |       | **0**      |

## Intro

> The React framework for Production (MIT License)

- Opensource
- Released Oct 2016

Nextjs (by Vercel) is a React based framework, that renders react applications on the server.
Its blazing fast and SEO friendly, due to offering Statitic Site Generation (SSG) as well as Server Side Rendering (SSR).

### Static and Dynamic for JAMstack

Normal React apps, use JavaScript, which requires it to be enabled in your browser. Nextjs fixes this through
SSG and SSR, whereby the app is either 'built' as an SSG (no JS) at build time, or are pre-rendered using SSR.
This makes it very fast on the server, with an overall better user experience.
This combined with great SEO features, make it a perfect choice for SPA's, apps, Blogs etc.

## Nextjs Features

| Features                        | Description                                                                                 |
| ------------------------------- | ------------------------------------------------------------------------------------------- |
| **Hot Code Reloading**          | Nextjs server detects file modification and does auto reload.                               |
| **Automatic Routing**           | Url's are mapped to the file folder system: (`pages`) folder. Optional use React Router.    |
| **SinglFile Components**        | styled-jsx builit-in and provides support for global as well as component specific styles.  |
| **Automatic Code splting**      | efficient rendering of only `used` libs, code, css, etc, split at the component/page level. |
| **Prefetch**                    | the nextjs `Link` component has a `prefetch` property built in to prefetch page resources.  |
| **Server side Renring**         | react components are pre-rendered on server hence faster loading on clients.                |
| **Static Site exports**         | Full static site export to an `out` folder.                                                 |
| **Dynamic components**          | Next.js allows the import of JavaScript modules and React Components dynamically.           |
| **Node Ecosystem**              | Runs on Node and is comptible with most JavaScript frameworks.                              |
| **Built-in TypeScript support** | Excellent built-in TypeScript support.                                                      |

## Usage

### Create

```npm
npx create-next-app {project-name}
```

### Run Dev

```npm
npm run dev
```

### Build and Start

```npm
npm build npm start
```

### Export

```npm
npx export
```

## Links

- [Next.js](https://nextjs.org/)
- [Next.js GitHub](https://github.com/vercel/next.js)
- [Docs](https://nextjs.org/docs)
- [Create Nextjs App](https://nextjs.org/learn/basics/create-nextjs-app)
