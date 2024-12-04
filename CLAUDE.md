# Critical Operational Requirements for Claude

This document outlines critical operational requirements when using Claude to interact with this repository through the GitHub API.

## File Operations

### Use `push_files` Instead of `create_or_update_files`

- ALWAYS use the `push_files` function for file operations
- The `create_or_update_files` function is currently non-functional and should not be used
- Example:
  ```json
  {
    "command": "push_files",
    "owner": "wrale",
    "repo": "wrale-charts",
    "branch": "main",
    "message": "Update documentation",
    "files": [{"path": "docs/example.md", "content": "Full content here..."}]
  }
  ```

### Never Use Content Placeholders

- ALWAYS include the complete file content when pushing changes
- NEVER use placeholders that point to old content (e.g., "..." or "rest of file remains the same")
- If you use placeholders, the pointed-to content will be overwritten and lost
- Data loss would require manual recovery from older commits

### Single File Operations

- Push only ONE file per MCP call
- This helps prevent hitting maximum message length limits
- Breaking up multi-file changes into individual pushes prevents having to restart entire operations
- If multiple files need updating, make separate push_files calls for each

## Best Practices

1. Before modifying a file:
   - Always fetch the current content first
   - Review the entire file content
   - Keep track of the full context

2. When pushing changes:
   - Include complete file content
   - Use clear, descriptive commit messages
   - Verify content before pushing

3. For multi-file changes:
   - Plan the sequence of updates
   - Push files one at a time
   - Verify each push completes successfully

These requirements help maintain data integrity and prevent accidental data loss when Claude interacts with the repository.