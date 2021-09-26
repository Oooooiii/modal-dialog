## Modal-Dialog

`yarn`
`yarn add`

### Technologies used

- Vite
- Vue
- Tailwind

### Learned about

- Teleport

  - is fantasic for **modals**, **popups**, and **notifications**.
  - keep all the **modal code** in the same component as **the button** is the easiest.
  - render-wise, our modal styles **depends** on its parent DOM elements.
  - **teleport** best place for data, not best place for rendering.

- Slot

  - let us pass template content to a child component
  - it's a great way to build flexible components
  - named slots
    - named our slots with the **name** attribute
    - specify which slot we are targeting with **v-slot**

- Script setup

  - lets us write conscise SFCs with the Composition API
  - it equivalent of common Vue operations
  - all **top level bindinds** are explosed to the template
  - removing **setup** and **manual returns** make our RFCs simpler
  - can wait for API calls in component creation

- Implement unplugin-icons

  - "@iconify/json": "^1.1.406",
  - "unplugin-icons": "^0.11.4",
  - "unplugin-vue-components": "^0.15.4",
