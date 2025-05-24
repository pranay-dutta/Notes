| **Types**              | **Recommended** | **Example**                                     |
| ---------------------- | --------------- | ----------------------------------------------- |
| **Vanilla CSS**        | ❌               | `className="btn"` + `styles.css`                |
| **CSS Modules**        | ❌               | `className={styles.btn}` + `Button.module.css`  |
| **CSS-in-JS**          | ❌               | `styled.button\`...\`` (e.g. styled-components) |
| **CSS Library**        | ✅               | `className="bg-blue-500 ..."` (e.g. Tailwind)   |
| **Inline Styling**<br> | ❌               | `style={{ ... }}`                               |

---
### ✅ **CSS Library (Recommended)**
Using **Tailwind CSS** as an example:
```tsx
export default function Button() {
	return <button className="bg-blue-500 text-white px-4 py-2 rounded">Click</button>; 
}
```

---
#### ❌ Vanilla CSS

```css
/* styles.css */
.btn { background: blue; color: white; padding: 8px 16px; border-radius: 4px; }
import './styles.css';
<button className="btn">Click</button>
```

---
 ❌ **CSS Modules**

```css
/* Button.module.css */ 
.btn { background: green; color: white; padding: 8px 16px; border-radius: 4px; }`
import styles from './Button.module.css'; <button className={styles.btn}>Click</button>
```

---

#### ❌ CSS-in-JS

```tsx
import styled from 'styled-components';
const Button = styled.button`background: purple; color: white; padding: 8px 16px; border-radius: 4px;`;
<Button>Click</Button>
```

---
#### ❌ Inline Styling

```tsx
<button style={{ backgroundColor: 'red', color: 'white', padding: '8px 16px', borderRadius: '4px' }}>   Click </button>
```
