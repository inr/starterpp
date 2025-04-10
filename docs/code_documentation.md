# Code Documentation

## What To Document

Always document:
 - Functions
 - Global variables
 - Macros
 - Classes & Structs
 - Concepts
 - Using directives

## Guidelines

### Use the following formatting

```cpp
/**
 * @TAG Lorem Ipsum
 * @TAG Lorem Ipsum
 * @TAG Lorem Ipsum
 */
```

### Don't use any tags except the following ones

Use `@brief` to give a general short description.

Use `@param` to give a short description about that specific parameter.

Use `@tparam` to give a short description about a template parameter.

Use `@return` to give a short description about the function return type.

Use `@throws` to describe what the function throws.

Use `@see` to reference an external information that is part of this code.

Use `@warning` to warn about correct usage that otherwise might cause a bug.

### Never put spaces between tags

Bad

```cpp
/**
 * @brief Calculates the area of a rectangle
 * 
 * @param length The longer side measurement
 * 
 * @param width The shorter side measurement
 * 
 * @return Product of length and width
 */
float area(float length, float width);
```

Good

```cpp
/**
 * @brief Calculates the area of a rectangle
 * @param length The longer side measurement
 * @param width The shorter side measurement
 * @return Product of length and width
 */
float area(float length, float width);
```

## Examples

### Functions

```cpp
/**
 * @brief Adds two integers.
 * @param a The first integer to add.
 * @param b The second integer to add.
 * @return The sum of a and b.
 * @throws std::invalid_argument if either parameter is negative.
 * @see subtract() for the inverse operation.
 */
int add(int a, int b)
{
    if (a < 0 || b < 0)
    {
        throw std::invalid_argument("Negative values not allowed");
    }

    return a + b;
}
```

### Global Variables

```cpp
/**
 * @brief Maximum allowed temperature in degrees Celsius.
 * @warning Exceeding this value triggers an emergency shutdown.
 */
float max_temperature = 90.5f; 
```

### Macros

```cpp
/**
 * @brief Computes the absolute value of a number.
 * @param x The input value (integer or floating point).
 * @warning Avoid using with expressions that have side effects (e.g., `ABS(x++)`).
 */
#define ABS(x) ((x) < 0 ? -(x) : (x))
```

### Classes & Structs

```cpp
/**
 * @brief Represents a 3D vector with x, y, z components.
 * @tparam type_t Precision type (e.g., float, double).
 */
template<typename type_t>
struct vec3
{
    type_t x;
    type_t y;
    type_t z;
};
```

### Concepts

```cpp
/**
 * @brief Constraint for types supporting arithmetic operations.
 * @tparam type_t The type to check.
 */
template<typename type_t>
concept arithmetic = std::is_arithmetic_v<type_t>;
```

### Using Directives

```cpp
/**
 * @brief A vector of type float.
 */
using my_vector = std::vector<float>;
```

