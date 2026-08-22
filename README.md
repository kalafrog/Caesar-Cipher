# Caesar Cipher — ROT13 (C++)

A clean C++ implementation of the Caesar Cipher algorithm using a fixed shift of 13 (ROT13) for text encryption and decryption.

## Features
* **Dual Operation**: Supports both text encryption and decryption using symmetric cipher logic[cite: 1].
* **Case Sensitivity**: Correctly handles uppercase (`A-Z`) and lowercase (`a-z`) letters independently[cite: 1].
* **Character Preservation**: Keeps spaces, digits, and special characters completely unchanged[cite: 1].
* **Zero External Dependencies**: Built strictly using fundamental C++ standard library features (`<iostream>`, `<string>`) without external cryptographic libraries[cite: 1].

## How It Works
1. **ASCII Normalization**: Subtracts the base character (`'A'` or `'a'`) from letter ASCII codes to map them to a 0–25 index.
2. **Modulo Wrapping**: Applies the shift transformation using modulo arithmetic to ensure clean wrap-around at alphabet boundaries:
   $$\text{New Index} = (\text{Current Index} + \text{Shift}) \pmod{26}$$
3. **Negative Shift Handling**: Uses `(shift % 26 + 26) % 26` to normalize backward shifts during decryption into positive equivalent bounds.

## Sample Execution
| Input Text | Operation | Shift | Resulting Output |
| :--- | :--- | :--- | :--- |
| `Hello Techies!` | Encrypt | +13 | `Uryyb Grpuvrf!` |
| `Uryyb Grpuvrf!` | Decrypt | -13 | `Hello Techies!` |
| `C++ Code 2026` | Encrypt | +13 | `P++ Pbqr 2026` |

## How to Run

1. **Compile the code**:
   ```bash
   g++ -o main main.cpp
