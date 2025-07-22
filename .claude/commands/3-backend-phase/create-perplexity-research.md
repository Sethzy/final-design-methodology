#### 2.2. External Documentation & Examples

_(Provide a list of all external documentation. For each resource, provide a link, a brief description, and a detailed explanation of how it should be used. This is the most critical section.)_

_(Reference specific files and code blocks codebase thjat should be used as a template. Explain what aspects should be mimicked.)_

**(List at least 5-7 resources here)**

**Example Format:**

**Resource 1: [Name of Resource, e.g., React Docs - Handling Events]**

- **URL**: [Link to the documentation]
- **Description**: Official React documentation on handling user events.
- **How to Use**:
  - **Event Persistence**: The section on `event.persist()` is critical. We must call this if we need to access an event asynchronously to prevent it from being nullified.
  - **Passing Handlers**: Follow the patterns here for passing event handlers as props to child components.
