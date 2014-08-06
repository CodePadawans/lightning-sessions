# How to start new projects (Workflow)
This describes what steps you need to take to start a new project.

## 1. Requirements

Before you start any coding, it starts with requirements. What you do here is writing down all things your new program should do. You write it down in normal text without any code related things. To achieve the best results, you describe the features/requirements from the user's perspective.
You can write this directly into your project's `README.md` file.

### Requirements explanation
A requirement describes, what you expect the new program to do.

> "I expect ataru to test my documenation"

This is an requirement, but it is very abstract. 

> "I expect ataru to read code examples from markdown files"

This here is already more concrete. With this requirement you're able to infer concrete tasks:

- Read a file
- The file must be Markdown
- Get all code examples from Markdown


### Examples

Requirement 1:

> "As a user, I want to run ataru from the command line and pass a markdown file as parameter"

Example: 
```
$ ataru readme.md
```

Requirement 2:

> "As a user, I want to see how many examples where run and how many failed"

Example:
```
$ ataru readme.md
Ran examples: 5 Failed: 1
```

