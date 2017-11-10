> This is a proposal assembled by the [concrete5 codestyle working group][github-link]. If you'd like to be a part of this
effort, feel free to open an issue or join us in slack!

----
# Code Standards

# 1. Summary
Our code standards are aging and don't cover new features of PHP. This proposal recommends we follow PSR-12 and codify
certain other aspects of our code style like automated fixing.

# 2. Why Bother?
**Code in the core today doesn't exactly follow a single standard**. We have:

* Modern code following PSR1 and PSR2
* Legacy code following legacy rules
* Legacy code following no rules
* View files where PSR1/2 is largely unhelpful
* Javascript and CSS where it's the wild west

**We don't have standards for some things**

* PSR-2 only covers PHP 5.3 code
* JavaScript and CSS don't have standards
* Many aspects of view files are not standardized

**We don't have concise documentation for this stuff**  
Documentation is an important consideration when it comes to defining standards. We need standards that are easy to
understand and even easier to comply with.

**Tooling we have is inconsistent**  
People have independently contributed to configurations that help keep us honest, but we don't have full coverage and we
are finding it difficult to agree on what to codify.

# 3. Scope
* Defining: 
  * PHP coding style
  * View file coding style
  * JavaScript coding style
  * CSS coding style
* Tooling for testing and fixing errant code
* Minimum PHP version (?)
* Code Style documentation
* Pull Request process


## 3.1. Release Target
[concrete5 v9.0.0][version-milestone]

## 3.2. Goals
This proposal will codify standards for all aspects of current concrete5 development and adjust ALL core code to align
with standards. It will also add clear concise documentation, and enact changes in pull request process as needed to 
ensure  that we maintain a high level of code quality and cleanliness with the least amount of effort.

## 3.3. Non-Goals
This proposal is not meant to cater to what the majority of users are doing today, instead it should focus on the goals
in #3.1.

# 4. How?

## 4.1. Thing that needs to change
TBD

## 4.2. Thing that needs to be removed
TBD

## 4.3. A policy that we need to implement
TBD

# 5. Examples
TBD


[github-link]: https://github.com/buttress/concrete5_codestyle_wg
[version-milestone]: https://github.com/concrete5/concrete5/milestone/21
