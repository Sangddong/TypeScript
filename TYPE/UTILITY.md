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

const searchOption1: ProductOptionOmit = { price: 2000, brand: "NIKE" };                              // ⭕️
const searchOption2: ProductOptionOmit = { price: 2000, brand: "NIKE", color: "red", price: 2000 };   // ❌
const searchOption3: ProductOptionOmit = {  color: "red", price: 2000, brand: "NIKE" };               // ❌
const searchOption4: ProductOptionOmit = { color: "red", price: 2000 };                               // ⭕❌

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
---
### Summary
<body>
    <table>
        <thead>
            <tr>
                <th></th>
                <th>Pick</th>
                <th>Omit</th>
                <th>Partial</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><strong>Common</strong></td>
                <td colspan="3" class="merged-cell">Create a new type from an already defined type</td>
            </tr>
            <tr>
                <td><strong>Result</strong></td>
                <td>Selects specific keys</td>
                <td>Removes specific keys</td>
                <td>Makes all keys optional</td>
            </tr>
        </tbody>
    </table>
</body>
