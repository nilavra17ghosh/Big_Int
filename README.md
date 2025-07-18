# BigInt - Arbitrary Precision Integer Library

A C++ implementation of arbitrary precision integers that can handle numbers of any size, limited only by available memory. This library provides a complete set of arithmetic operations and mathematical functions for working with very large integers.

## Features

### Core Operations
- **Arithmetic Operations**: Addition, subtraction, multiplication, division, modulo
- **Comparison Operations**: Equal, not equal, less than, greater than, less than or equal, greater than or equal
- **Assignment Operations**: Direct assignment and compound assignment operators
- **Increment/Decrement**: Pre and post increment/decrement operators
- **Power Operations**: Exponentiation with efficient algorithm
- **Square Root**: Integer square root calculation

### Mathematical Functions
- **Factorial**: Calculate factorial of numbers up to very large values
- **Fibonacci**: Generate Fibonacci numbers of any index
- **Catalan Numbers**: Generate Catalan numbers for combinatorial problems

### Input/Output
- **Stream Operations**: Support for cin/cout operations
- **Multiple Constructors**: Initialize from strings, integers, or other BigInt objects
- **Flexible Input**: Accept numbers as strings, integers, or character arrays

## Class Structure

```cpp
class BigInt {
private:
    string digits;  // Stores digits in reverse order for efficient operations
    
public:
    // Constructors
    BigInt(unsigned long long n = 0);
    BigInt(string &s);
    BigInt(const char *s);
    BigInt(BigInt &other);
    
    // Operator overloads and member functions
    // ... (see implementation for complete list)
};
```

## Usage Examples

### Basic Operations

```cpp
#include "BigInt.cpp"

int main() {
    // Creating BigInt objects
    BigInt a("123456789012345678901234567890");
    BigInt b(987654321);
    
    // Arithmetic operations
    BigInt sum = a + b;
    BigInt difference = a - b;
    BigInt product = a * b;
    BigInt quotient = a / b;
    BigInt remainder = a % b;
    
    // Comparison operations
    if (a > b) {
        cout << "a is greater than b" << endl;
    }
    
    // Power operations
    BigInt power = a ^ BigInt(10);  // a raised to power 10
    
    // Square root
    BigInt sqrt_a = sqrt(a);
    
    return 0;
}
```

### Mathematical Functions

```cpp
// Calculate large factorials
BigInt fact100 = Factorial(100);
cout << "100! = " << fact100 << endl;

// Generate Fibonacci numbers
BigInt fib50 = NthFibonacci(50);
cout << "50th Fibonacci number = " << fib50 << endl;

// Calculate Catalan numbers
BigInt cat20 = NthCatalan(20);
cout << "20th Catalan number = " << cat20 << endl;
```

### Increment/Decrement Operations

```cpp
BigInt num("999999999999999999999");
num++;  // Post-increment
++num;  // Pre-increment
num--;  // Post-decrement
--num;  // Pre-decrement
```

## Supported Operations

### Arithmetic Operators
- `+`, `+=` - Addition
- `-`, `-=` - Subtraction
- `*`, `*=` - Multiplication
- `/`, `/=` - Division
- `%`, `%=` - Modulo
- `^`, `^=` - Exponentiation

### Comparison Operators
- `==` - Equal to
- `!=` - Not equal to
- `<` - Less than
- `<=` - Less than or equal to
- `>` - Greater than
- `>=` - Greater than or equal to

### Unary Operators
- `++` - Increment (pre and post)
- `--` - Decrement (pre and post)

### Stream Operators
- `>>` - Input stream
- `<<` - Output stream

## Helper Functions

- `Length(BigInt)` - Returns number of digits
- `Null(BigInt)` - Checks if BigInt is zero
- `divide_by_2(BigInt)` - Efficiently divides by 2
- `sqrt(BigInt)` - Integer square root

## Error Handling

The library includes error handling for:
- Division by zero
- Invalid number formats
- Underflow conditions
- Array bounds checking

## Example Program Output

The included main function demonstrates:
- Basic arithmetic operations
- Comparison operations
- Fibonacci sequence (0-100)
- Catalan numbers (0-100)
- Factorials (0-100)

## Compilation

```bash
g++ -o bigint BigInt.cpp
./bigint
```

## Performance Features

- **Efficient Storage**: Digits stored in reverse order for optimal arithmetic operations
- **Optimized Algorithms**: Uses efficient algorithms for multiplication, division, and exponentiation
- **Memory Management**: Automatic memory management with dynamic resizing
- **Carry Propagation**: Efficient carry handling in arithmetic operations

## Applications

This BigInt library is suitable for:
- Cryptographic applications requiring large number arithmetic
- Mathematical computations with very large integers
- Competitive programming problems involving big integers
- Scientific computing requiring arbitrary precision
- Educational purposes for understanding big number arithmetic

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.