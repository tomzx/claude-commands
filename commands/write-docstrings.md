Add or improve docstrings/documentation comments in the code.

## Instructions

1. **Identify Documentation Style**
   - **Python**: Google style, NumPy style, or Sphinx/reStructuredText
   - **JavaScript/TypeScript**: JSDoc
   - **Go**: godoc comments
   - **Rust**: rustdoc comments
   - **Java**: Javadoc

2. **Analyze Code Coverage**
   - Find functions/classes/modules without docstrings
   - Identify incomplete docstrings
   - Check public APIs are documented
   - Review complex code that needs explanation

3. **Write Docstrings**

   **Python (Google Style):**
   ```python
   def calculate_total(items: list[Item], tax_rate: float = 0.0) -> float:
       """Calculate the total price including tax.

       Args:
           items: List of items to calculate total for.
           tax_rate: Tax rate as a decimal (e.g., 0.1 for 10%). Defaults to 0.0.

       Returns:
           The total price including tax.

       Raises:
           ValueError: If tax_rate is negative.

       Examples:
           >>> items = [Item(price=10.0), Item(price=20.0)]
           >>> calculate_total(items, tax_rate=0.1)
           33.0
       """
       if tax_rate < 0:
           raise ValueError("tax_rate must be non-negative")

       subtotal = sum(item.price for item in items)
       return subtotal * (1 + tax_rate)
   ```

   **JavaScript (JSDoc):**
   ```javascript
   /**
    * Calculate the total price including tax.
    *
    * @param {Item[]} items - List of items to calculate total for.
    * @param {number} [taxRate=0] - Tax rate as a decimal (e.g., 0.1 for 10%).
    * @returns {number} The total price including tax.
    * @throws {Error} If taxRate is negative.
    *
    * @example
    * const items = [{price: 10}, {price: 20}];
    * calculateTotal(items, 0.1); // returns 33.0
    */
   function calculateTotal(items, taxRate = 0) {
     if (taxRate < 0) {
       throw new Error("taxRate must be non-negative");
     }

     const subtotal = items.reduce((sum, item) => sum + item.price, 0);
     return subtotal * (1 + taxRate);
   }
   ```

   **Go:**
   ```go
   // CalculateTotal calculates the total price including tax.
   //
   // It sums up all item prices and applies the tax rate.
   // The tax rate should be a decimal (e.g., 0.1 for 10%).
   //
   // Returns an error if taxRate is negative.
   func CalculateTotal(items []Item, taxRate float64) (float64, error) {
       if taxRate < 0 {
           return 0, fmt.Errorf("taxRate must be non-negative")
       }

       var subtotal float64
       for _, item := range items {
           subtotal += item.Price
       }
       return subtotal * (1 + taxRate), nil
   }
   ```

4. **Docstring Components**

   For functions/methods:
   - **Summary**: One-line description
   - **Description**: Longer explanation (if needed)
   - **Parameters/Args**: Each parameter with type and description
   - **Returns**: Return value type and description
   - **Raises/Throws**: Exceptions that can be raised
   - **Examples**: Usage examples
   - **Notes**: Additional context, warnings, or tips

   For classes:
   - **Summary**: What the class represents
   - **Attributes**: Instance/class attributes
   - **Examples**: How to instantiate and use

   For modules:
   - **Summary**: Module purpose
   - **Contents**: Key classes/functions
   - **Usage**: How to import and use

5. **Documentation Best Practices**
   - Document public APIs (public functions, classes, modules)
   - Private functions may need docs too if complex
   - Keep docstrings concise but complete
   - Use consistent style throughout codebase
   - Include type information
   - Add examples for non-obvious usage
   - Document edge cases and gotchas
   - Update docstrings when code changes

6. **Generate Documentation**
   - **Python**: Use `sphinx` to generate HTML docs
   - **JavaScript**: Use `jsdoc` or `typedoc`
   - **Go**: `godoc` or `pkgsite`
   - **Rust**: `cargo doc`

7. **Validate Docstrings**
   - Check for missing docstrings:
     - Python: `pydocstyle`, `interrogate`
     - JavaScript: ESLint rules
   - Verify examples work:
     - Python: `doctest`
   - Ensure completeness (all params documented)

## Output

Provide:
- **Coverage Analysis**: Functions/classes without docstrings
- **Style Guide**: Docstring format used
- **Updated Code**: Code with added/improved docstrings
- **Documentation**: Generated HTML documentation (if applicable)
- **Statistics**:
  - Total functions/classes
  - Documented vs undocumented
  - Documentation coverage percentage
- **Recommendations**: Additional documentation needs
