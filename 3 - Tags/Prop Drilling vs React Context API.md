**Topic**: [[React]]

<img src="prop-drilling-vs-react-context-api.png" width=400 width=250 style="border-radius: 10px" />

| Feature                | **React Context API**                                  | **Prop Drilling**                                           |
| ---------------------- | ------------------------------------------------------ | ----------------------------------------------------------- |
| **Purpose**            | Manage and share global state across components        | Pass data from parent to deeply nested child components     |
| **Ease of Use**        | Cleaner for deep component trees                       | Becomes messy as nesting increases                          |
| **Component Coupling** | Loosely coupled                                        | Tightly couples all intermediate components                 |
| **Performance**        | May cause unnecessary re-renders if not optimized      | Avoids global state, but inefficient for deeply nested data |
| **Scalability**        | More scalable for large apps                           | Hard to maintain in large apps                              |
| **Setup Complexity**   | Requires creating context and provider components      | No extra setup; basic props usage                           |
| **Use Case**           | Theming, authentication, user settings, language, etc. | Simple, one-off data passing through shallow component tree |

🥴 **MEME**

<img src="prop-drilling-vs-react-context-meme.png" width=400 height=250 style="border-radius: 10px" />