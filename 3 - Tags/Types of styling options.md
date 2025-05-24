**Topic**: [[React]]

| **Types**              | **Recommended** |
| ---------------------- | --------------- |
| **Vanilla CSS**        | ❌               |
| **CSS Modules**        | ❌               |
| **CSS-in-JS**          | ❌               |
| **CSS Library**        | ✅               |
| **Inline Styling**<br> | ❌               |

---
 ✅ **CSS Library (Recommended)**:  **Tailwind CSS** as an example:
 
```tsx
export default function Button() {
	return <button className="bg-blue-500 text-white">Click</button>; 
}
```
---
 ❌ **Vanilla CSS**

```css
/* styles.css */
.btn { background: blue; color: white;  }
import './styles.css';
<button className="btn">Click</button>
```
---
 ❌ **CSS Modules**
 
```css
/* Button.module.css */ 
.btn { background: green; color: white; }
import styles from './Button.module.css'; 
<button className={styles.btn}>Click</button>
```
---
 ❌ **CSS-in-JS**
 
```tsx
import styled from 'styled-components';
const Button = styled.button`background: purple; color: white`;
<Button>Click</Button>
```
---
 ❌**Inline Styling**

```tsx
<button style={{ backgroundColor: 'red', color: 'white'}}> Click </button>
```
