# 🎸 GuitarLA (TypeScript)

Tienda de guitarras con carrito de compras interactivo construida con React, TypeScript y Vite. Permite explorar un catálogo de 12 guitarras, agregar productos al carrito, ajustar cantidades y ver el total en tiempo real. El carrito persiste entre sesiones gracias a `localStorage`.

Versión en TypeScript del proyecto original [react-guitar-shopping-cart](https://github.com/andresmdevco/react-guitar-shopping-cart), migrado a tipado estático con TypeScript.

## 📁 Archivos principales

| Archivo | Descripción |
|---|---|
| `App.tsx` | Componente raíz. Consume el hook `useCart` y distribuye el estado a los componentes hijos |
| `Header.tsx` | Header con carrito desplegable, tabla de productos y total calculado |
| `Guitar.tsx` | Tarjeta de producto con imagen, nombre, descripción, precio y botón para agregar al carrito |
| `useCart.ts` | Custom hook que encapsula toda la lógica y el estado del carrito |
| `db.ts` | Base de datos local tipada con el catálogo de 12 guitarras |
| `types/index.ts` | Definiciones de tipos (`Guitar`, `CartItem`) compartidas por toda la app |

## 🛠️ Tecnologías utilizadas

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)

## ✨ Características

- **Catálogo de guitarras** — 12 productos con imagen, nombre, descripción y precio
- **Carrito desplegable** — Accesible desde el header, muestra los productos seleccionados con imagen y precio
- **Control de cantidad** — Botones para aumentar o disminuir unidades por ítem (mín. 1 — máx. 5)
- **Eliminación de productos** — Botón para remover un ítem individual del carrito
- **Vaciado del carrito** — Botón para limpiar todos los productos de una sola vez
- **Total en tiempo real** — Calculado con `useMemo` a partir de la cantidad y precio de cada ítem
- **Persistencia con localStorage** — El carrito se mantiene al recargar la página
- **Lazy initializer en `useState`** — El carrito lee `localStorage` solo en el primer renderizado
- **Tipado estático completo** — Props, estado y funciones tipadas con TypeScript, sin uso de `any`
- **Lógica extraída a un custom hook** — `useCart` centraliza el estado y las operaciones del carrito, desacoplándolos de la UI

## 📚 Conceptos practicados

- Tipado de componentes, props y funciones con TypeScript
- Definición de tipos reutilizables (`Guitar`, `CartItem`) mediante intersección de tipos (`&`)
- Extracción de lógica de estado a un custom hook (`useCart`) para separar lógica de presentación
- Gestión de estado con `useState` y lazy initializer
- Estado derivado con `useMemo` para evitar recálculos innecesarios (`isEmpty`, `cartTotal`)
- Persistencia del carrito con `useEffect` — guarda el estado en `localStorage` ante cada cambio
- Comunicación entre componentes mediante props tipadas y funciones callback
- Manipulación de arreglos con métodos funcionales (`map`, `filter`, `findIndex`, `reduce`)
- Uso del operador de aserción no-nula (`!`) al obtener el elemento raíz del DOM

## 🚀 Cómo ejecutar el proyecto

```bash
git clone https://github.com/andresmdevco/react-guitar-shopping-cart-ts.git
cd react-guitar-shopping-cart-ts
npm install
npm run dev
```