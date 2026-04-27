# Interface Design for Testability

Three core principles for creating testable interfaces:

1. **Dependency Injection**: Rather than instantiating dependencies internally, functions should accept them as parameters. The example contrasts "Testable: `function processOrder(order, paymentGateway) {}`" with a harder-to-test approach that creates a StripeGateway instance internally.

2. **Pure Functions Over Side Effects**: Functions should compute and return values instead of modifying state. As demonstrated, "`function calculateDiscount(cart): Discount {}`" is preferable to one that directly modifies the cart object and returns void.

3. **Minimal Surface Area**: Reducing the number of methods and parameters simplifies test creation and setup requirements.

These principles emphasize that testable design emerges naturally when interfaces prioritize explicit inputs, predictable outputs, and reduced complexity.
