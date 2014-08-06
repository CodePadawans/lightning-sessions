# How to start new projects (Workflow)
This describes what steps you need to take to start a new project. This is meant as a guideline.

## 1. Requirements

Before you start any coding, it starts with *requirements*. What you do here is writing down all things your new program should do. You write it down in normal text without any code related things. To achieve the best results, you describe the features/requirements from the user's perspective. For each requirement, you create an Issue in your project's repository.

### What is a requirement?
A requirement describes what you expect the new program to do.

> "I expect ataru to test my documentation"

This is an requirement, but it is very abstract and not very specific. 

> "I expect ataru to read code examples from markdown files"

This here is already more concrete. With this requirement you're able to infer concrete tasks:

- Read a file
- The file must be Markdown
- Get all code examples from Markdown


### Examples
Each requirement here is a separate issue.

*Requirement 1:*

> "As a user, I want to run ataru from the command line and pass a markdown file as parameter"

Example: 
```
$ ataru readme.md
```

*Requirement 2:*

> "As a user, I want to see how many examples where run and how many failed"

Example:
```
$ ataru readme.md
Ran examples: 5 Failed: 1
```

## 2. Select features for the first version of your program

When you collected all requirements you need to prioritize which features should be part of the first version. What requirements should be picked?
Pick all requirements which are necessary to build a very basic but working version.

## 3. Start development

General Notes

### Pull Request (PR)
In the description of the PR you describe shortly what you did. Also add a reference to the GitHub Issue. When the PR was created, ask you pair for review. When your pair approved it, it can be merged. The branch you worked on can be deleted afterwards.

### Commit
Before you create a new commit, make sure that all tests pass and none of them fail.

### Workflow

The development workflow looks like this:

1. Pick an issue from the list and assign it to you
2. Create a new branch <issue number> - <branch name>
3. Start development on the branch
4. When you're finished, create a pull request.
