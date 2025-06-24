**Topic**: [[React]]

| Step                 | Tool / Role                       | Emoji |
| -------------------- | --------------------------------- | ----- |
| Write React JSX code | Developer writes components       | ✍️    |
| Transform JSX + ES6+ | Babel compiles to JS              | 🔧    |
| Bundle and optimize  | Webpack or bundler bundles assets | 📦    |
| Run in browser       | Bundled JS runs in browsers       | 🌐    |
### What Happens When You Write React Code?

- React code is often written using **JSX** (JavaScript XML) — looks like HTML inside JavaScript.
- Uses modern JavaScript features (ES6+) which **not all browsers support directly**.

---
###  Why Do We Need Compilation?

- ❌ Browsers **can’t run JSX or modern JS directly**.
- 🔄 React code needs to be **compiled** into plain JavaScript that browsers understand.

---
###  Tools That Compile React Code

#### 🛠️ Babel

- 🔧 A **JavaScript compiler**.
- 🔄 Converts **JSX + ES6+** → **Browser-compatible JS**.
- Example: JSX like `<div>Hello</div>` becomes `React.createElement('div', null, 'Hello')`.

#### 📦 Webpack (or Other Bundlers)

- 📚 Bundles all JavaScript and assets (CSS, images) into a few optimized files.
- 🚀 Prepares code for fast loading in browsers.

#### ⚙️ Frameworks & Starter Kits

- Examples: **Create React App (CRA), Next.js, Vite, Parcel**
- 🎯 Provide **pre-configured environments** combining Babel + bundlers.
- 💻 Run commands like `npm start` or `npm run build` to compile and bundle automatically.