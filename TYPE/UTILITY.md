# UTILITY
### 0. What is Utility type?
- Utility types are predefined type helpers that transform existing types.
- They allow you to write code more concisely than using generics or interfaces.
- `Pick`, `Omit`, 'Partial'
---
### 1. Pick
- `Pick` extracts specific keys from an already defiend type.
<br>

``` typescript
interface ProductOption {
  color: string;
  brand: string;
  price: number;
  sex: string;
};

const ProductOptionPick = Pick<ProductOption, 'color' | 'price'>;

const searchOption1: ProductOptionPick = { color: "red", price: 2000 }; // ⭕️
const searchOption2: ProductOptionPick = { color: "red" };              // ⭕️
const searchOption3: ProductOptionPick = { price: 2000 };               // ⭕️
const searchOption3: ProductOptionPick = { brand: "NIKE" };             // ❌

```
---
### 2. Omit
- `Omit` removes specific keys from an already defined type.
<br>

``` typescript
interface ProductOption {
  color: string;
  brand: string;
  price: number;
  sex: string;
};

const ProductOptionOmit = Omit<ProductOption, 'color' | 'price'>;

const searchOption1: ProductOptionOmit = { price: 2000 };               // ⭕️
const searchOption2: ProductOptionOmit = { brand: "NIKE" };             // ⭕️
const searchOption3: ProductOptionOmit = { color: "red", price: 2000 }; // ❌
const searchOption4: ProductOptionOmit = { color: "red" };              // ❌

```
---
### 3. Partial
- `Partial` creates a new type where all properties of another type are optional.
<br>

``` typescript
interface ProductOption {
  color: string;
  brand: string;
  price: number;
  sex: string;
};

const ProductOptionPartial = Partial<ProductOption>;

const searchOption1: ProductOptionPartial = { price: 2000 };               // ⭕️
const searchOption2: ProductOptionPartial = { brand: "NIKE" };             // ⭕️
const searchOption3: ProductOptionPartial = { color: "red", price: 2000 }; // ⭕️
const searchOption4: ProductOptionPartial = { color: "red" };              // ⭕️
const searchOption5: ProductOptionPartial = {};                            // ⭕️
```

