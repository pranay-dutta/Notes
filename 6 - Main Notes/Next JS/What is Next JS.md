**Topic**: [[React]] [[Next JS]]

📌**Next.js** is a React-based **framework** developed by **Vercel**. 
🟢 Offers building **full-stack** web applications with optimized **performance** and **scalability**.

🔹 **Key Features & Benefits**

| #   | Feature                           | What it Does / Why it Helps                                                                      |
| --- | --------------------------------- | ------------------------------------------------------------------------------------------------ |
| 1   | **Server-Side Rendering (SSR)**   | Pre-renders pages on every request via `getServerSideProps`, boosting performance & SEO.         |
| 2   | **Static Site Generation (SSG)**  | Builds pages at compile time with `getStaticProps` / `getStaticPaths`, giving CDN-fast delivery. |
| 3   | **Client-Side Rendering (CSR)**   | Lets you hydrate pages and fetch data in the browser with hooks like `useEffect`.                |
| 4   | **File-based Routing**            | Any file in `pages/` (or `app/`) instantly becomes a route—no extra config.                      |
| 5   | **App Router (New)**              | `app/` directory adds nested & parallel routes, layouts, and React Server Components.            |
| 6   | **API Routes**                    | Ship backend endpoints right inside your project (`pages/api/` or `app/api/`).                   |
| 7   | **Image Optimization**            | `next/image` handles responsive sizing, lazy loading, and modern formats automatically.          |
| 8   | **TypeScript Support**            | Zero-config TypeScript setup out of the box for safer code.                                      |
| 9   | **CSS & Sass Support**            | Built-in CSS Modules, global styles, and Sass—no tooling hassle.                                 |
| 10  | **Middleware & Edge Functions**   | Run logic (auth, redirects, A/B tests) closer to the user before each request completes.         |
| 11  | **Fast Refresh & Hot Reload**     | Instant feedback loop while coding—state preserved on edits.                                     |
| 12  | **Optimized Deployment (Vercel)** | One-click deploy with built-in CI/CD, automatic scaling, and global CDN.                         |

✅ **Use Next.js when you need:**

| Scenario                      | Why Next.js Fits                                       |
| ----------------------------- | ------------------------------------------------------ |
| SEO-friendly projects         | SSR/SSG ensure search engines get fully rendered HTML. |
| Blogs & portfolios            | Generate static pages once; serve worldwide via CDN.   |
| Full-stack apps               | Co-locate frontend & backend (API Routes) in one repo. |
| Hybrid static + dynamic sites | Mix SSG for content and CSR/SSR for dynamic parts.     |

🔗 Official Site: https://nextjs.org