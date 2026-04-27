# Refactor Candidates

Key indicators to address after completing a TDD cycle:

**Duplication** - "Extract function/class" when repeated code patterns emerge.

**Long methods** - Break them into private helpers while maintaining tests on the public interface.

**Shallow modules** - Consider combining or deepening modules that lack sufficient responsibility.

**Feature envy** - "Move logic to where data lives" when code inappropriately depends on another object's internal state.

**Primitive obsession** - Replace basic data types with purpose-built value objects to improve type safety.

**Existing code** - Pay attention to problems the new code reveals in the current codebase.
