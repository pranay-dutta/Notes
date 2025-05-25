**Topic**: [[React]]

🔴 A component **can't** **return more** than one **HTML element** 
🔴 **Inside** of **JSX**  we don't have `!for loops` instead we use `@map`

🟢Each item should have an **unique key**
🟢React uses **Synthetic Base Event** for cross browser **compatibility**. Because some **browsers** have different **implementation** of **event object**

### State
- 📌 **React** updates **state asynchronously**, means not **immediately.**
- 🤔 Reason is if we render on each state change we'll have multiple re-renders. So, for performance reasons all updates by react done after event handler.


