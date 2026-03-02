# Writing Good Commit Messages

A good commit message should be clear, concise, and consistent. It should explain what the commit does and why.

Here's a widely accepted format for commit messages:

`<type>(<scope>): <subject>`

`<空行>`
`<body>`

`<空行>`
`<footer>`

**Type:**
*   **feat:** A new feature
*   **fix:** A bug fix
*   **docs:** Documentation only changes
*   **style:** Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
*   **refactor:** A code change that neither fixes a bug nor adds a feature
*   **test:** Adding missing tests
*   **chore:** Changes to the build process or auxiliary tools and libraries such as documentation generation

**Example:**

`feat(auth): Add password reset functionality`

`This commit introduces a new feature that allows users to reset their password.`
`The user will receive an email with a link to a page where they can create a new password.`

`Closes #42`
