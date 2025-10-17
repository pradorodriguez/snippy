# Code Style Guide

This document outlines the recommended code style practices for writing clean, maintainable code. The examples and guidelines are derived from analyzed coding patterns.

## Naming Conventions

- **Functions and Methods**: Use `snake_case` for functions and methods.
  - Example: `async def generate_code_style(chat_history: str = "", user_query: str = "")`

- **Variables**: Use `snake_case` for variable names.
  - Example: `chat_history`, `user_query`

- **Constants**: Use `UPPER_SNAKE_CASE` for constants.
  - Example: `_CODE_STYLE_SYSTEM_PROMPT`

- **Classes**: Use `CamelCase` for class names.
  - Example: `AIProjectClient`

- **Modules**: Use `lower_snake_case` for module names.

## Code Organization

- **Imports**: Group imports into standard library, third-party, and local module imports. Separate each group with a blank line.

- **Function Length**: Keep functions short; a function should ideally fit within one screen (about 50 lines).

- **Single Responsibility**: Each function should have a single responsibility, making it easier to test and maintain.

## Documentation Standards

- **Function Docstring**: Every function should start with a docstring that describes its purpose, parameters, and return type.
  - Example:
    ```python
    """
    Generates a code style guide using an AI agent.
    
    Args:
        chat_history: The chat history or session for context
        user_query: The user's query for code style analysis
    
    Returns:
        str: The generated code style guide in Markdown format
    """
    ```

- **Class Docstring**: Classes should have a docstring explaining their purpose and any important details.

- **Inline Comments**: Use inline comments to clarify complex logic, but avoid obvious comments.

## Error Handling

- **Try-Except Blocks**: Use try-except blocks for error handling. Log errors at the appropriate level (INFO, ERROR) and provide useful error messages.
  - Example:
    ```python
    try:
        # Code block
    except Exception as e:
        logger.error("Description of error context: %s", str(e))
        raise
    ```

- **Custom Exceptions**: Define custom exceptions for specific error situations where the error can be anticipated and should be differentiated.

## Logging Practices

- **Log Levels**: Use appropriate logging levels: DEBUG, INFO, WARNING, ERROR, CRITICAL.
  
- **Contextual Logging**: Log relevant information to understand the context of operations and catch potential issues.
  - Example:
    ```python
    logger.info("Starting code style generation with:")
    logger.info("Chat history length: %d characters", len(chat_history))
    ```

- **Error Logging**: Always log the full exception and stack trace in error conditions for post-mortem analysis.
  - Example:
    ```python
    logger.error("Code style generation failed with error: %s", str(e), exc_info=True)
    ```

## Best Practices

- **Avoid Deep Nesting**: Refactor to avoid deep nesting in loops and conditionals. This makes the code more readable and maintainable.

- **Async/Await**: Use `async` and `await` for asynchronous programming patterns. Handle all awaited calls with appropriate exception handling.

- **Environment Variables**: Use environment variables for sensitive information like connection strings.
  - Example:
    ```python
    conn_str=os.environ["PROJECT_CONNECTION_STRING"]
    ```

By adhering to these guidelines, you will ensure that your code is clean, efficient, and easily maintainable.
