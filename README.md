# 🎸 GuitarLA (TypeScript)

Tienda de guitarras con carrito de compras interactivo construida con React, TypeScript y Vite. Permite explorar un catálogo de 12 guitarras, agregar productos al carrito, ajustar cantidades y ver el total en tiempo real. El carrito persiste entre sesiones gracias a `localStorage`.

Versión en TypeScript del proyecto original [react-guitar-shopping-cart](https://github.com/andresmdevco/react-guitar-shopping-cart), migrado a tipado estático con TypeScript y con gestión de estado mediante useReducer.

## 🌐 Demo

🔗 [https://guitarla-ts-andresmdevco.netlify.app/](https://guitarla-ts-andresmdevco.netlify.app/)

## 👀 Vista previa
https://github.com/user-attachments/assets/5c7eae01-7bf4-4add-a820-5385709c36cd

## 🛠️ Tecnologías Utilizadas

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)

## 📁 Archivos principales

| Archivo | Descripción |
|---|---|
| `App.tsx` | Componente raíz. Inicializa el estado global con `useReducer` y distribuye `state` y `dispatch` a los componentes hijos |
| `Header.tsx` | Header con carrito desplegable, tabla de productos y total calculado. Recibe `cart` y `dispatch` para disparar las acciones del carrito |
| `Guitar.tsx` | Tarjeta de producto con imagen, nombre, descripción, precio y botón para agregar al carrito mediante `dispatch` |
| `cart-reducer.ts` | Reducer que centraliza toda la lógica del carrito: acciones tipadas, estado inicial y transiciones de estado |
| `db.ts` | Base de datos local tipada con el catálogo de 12 guitarras |
| `types/index.ts` | Definiciones de tipos (`Guitar`, `CartItem`) compartidas por toda la app |

## ✨ Características

- **Catálogo de guitarras** — 12 productos con imagen, nombre, descripción y precio
- **Carrito desplegable** — Accesible desde el header, muestra los productos seleccionados con imagen y precio
- **Control de cantidad** — Botones para aumentar o disminuir unidades por ítem (mín. 1 — máx. 5)
- **Eliminación de productos** — Botón para remover un ítem individual del carrito
- **Vaciado del carrito** — Botón para limpiar todos los productos de una sola vez
- **Total en tiempo real** — Calculado con `useMemo` a partir de la cantidad y precio de cada ítem
- **Persistencia con localStorage** — El carrito se mantiene al recargar la página
- **Estado global con `useReducer`** — Todo el estado de la app (`data`, `cart`) se gestiona desde un único reducer
- **Acciones tipadas con discriminated unions** — Cada acción del carrito (`add-to-cart`, `remove-from-cart`, `decrease-quantity`, `increase-quantity`, `clear-cart`) tiene su propio `payload` tipado
- **Tipado estático completo** — Props, estado y funciones tipadas con TypeScript, sin uso de `any`
- **Lógica extraída a un reducer** — `cart-reducer.ts` centraliza el estado y las transiciones del carrito, desacoplándolos de la UI

## 📚 Conceptos aplicados

- Tipado de componentes, props y funciones con TypeScript
- Definición de tipos reutilizables (`Guitar`, `CartItem`) mediante intersección de tipos (`&`)
- Migración de `useState` + custom hook a `useReducer` para centralizar el estado global
- Modelado de acciones con discriminated unions (`CartActions`) para tipar `type` y `payload` de forma segura
- Uso de `Dispatch<CartActions>` para tipar la función `dispatch` recibida por los componentes hijos
- Actualizaciones inmutables del estado dentro del reducer (`map`, `filter`, spread operator)
- Persistencia del carrito con `useEffect` — guarda `state.cart` en `localStorage` ante cada cambio
- Estado derivado con `useMemo` para evitar recálculos innecesarios (`isEmpty`, `cartTotal`)
- Comunicación entre componentes mediante props tipadas y `dispatch`

## 🚀 Cómo ejecutar el proyecto

```bash
git clone https://github.com/andresmdevco/react-guitar-shopping-cart-ts.git
cd react-guitar-shopping-cart-ts
npm install
npm run dev
```
