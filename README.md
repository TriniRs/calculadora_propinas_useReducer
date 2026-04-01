# Calculadora de Propinas y Consumo (React + TS + useReducer)

Este proyecto es una aplicación interactiva para gestionar consumos en un restaurante, permitiendo seleccionar platillos del menú, ajustar propinas y calcular el total a pagar de forma dinámica.

> **Highlight Técnico:** La aplicación utiliza el hook **`useReducer`** para gestionar un estado complejo que incluye la lógica del pedido y el sistema de propinas, garantizando un flujo de datos unidireccional y fácil de depurar.

## 🚀 Funcionalidades

- **Menú Interactivo**: Selección de platillos desde una base de datos local[cite: 7, 11].
- **Gestión de Pedido**:
  - Agregar items al consumo (controlando cantidades de forma automática)[cite: 12].
  - Eliminar items específicos del pedido[cite: 8, 12].
  - Resetear la orden al finalizar el pago[cite: 9, 12].
- **Sistema de Propinas**: Selección de porcentajes personalizados (10%, 20%, 50%) que se aplican al subtotal[cite: 10, 12].
- **Cálculos en Tiempo Real**: Desglose detallado de Subtotal, Propina y Total Final utilizando `useMemo` para optimizar el rendimiento[cite: 9].

## 🧠 Estructura del Reducer (`order-reducer.ts`)

Se implementó un **Reducer** centralizado que maneja todas las mutaciones del estado a través de acciones tipadas[cite: 12].

### Acciones (Dispatch Events):

- `add-item`: Busca si el item ya existe en la orden para incrementar su cantidad o agregarlo como nuevo[cite: 12].
- `remove-item`: Elimina un producto de la lista mediante su ID[cite: 12].
- `add-tip`: Actualiza el porcentaje de propina seleccionado en el estado global[cite: 12].
- `place-order`: Limpia el estado de la orden y la propina para comenzar un nuevo consumo[cite: 12].

## 🛠️ Stack Tecnológico

- **React 18** (Hooks: `useReducer`, `useMemo`)[cite: 9, 14].
- **TypeScript**: Tipado estricto para componentes, interfaces de menú y acciones del reducer[cite: 7, 12, 13].
- **Tailwind CSS**: Diseño moderno y responsivo[cite: 14].

## 📐 Ejemplo de Implementación (Reducer)

El estado se define mediante una interfaz clara para evitar errores de tipo durante el desarrollo:

```typescript
export type OrderState = {
  order: OrderItem[];
  tip: number;
};
```
