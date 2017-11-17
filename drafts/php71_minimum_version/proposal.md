>This is a proposal assembled by the [concrete5 codestyle working group][github-link]. If you'd like to be a part of this
effort, feel free to open an issue or join us in slack!

---
# PHP 7.1 Minimum Version for concrete5 9.0.0

# 1. Summary
PHP 7.1 is the current release of PHP that includes new features like `nullable types` and the `iterable` typehint.
We currently support PHP 7.1 but we have a minimum requirement of PHP 5.5.9.

# 2. Why Bother?
Many of our dependencies are making the jump to a minimum version of PHP 7.1, most notably for us, symfony 4 and laravel 6
will both require at least PHP 7.1 to run.  
PHP 5 is currently only recieving security updates, by this time next year it will be completely unsupported. In the past
the major issue with changing minimum php version was that webhosts didn't support the latest versions until long after
the running versions had been unsupported. That left us supporting PHP 5.2 for years after it was unsupported, potentially
perpetuation the problem by allowing it to continue.  
Even though we have a very large community and user base, we don't have the weight to shift the market on our own, so in
the past we've benefited from major frameworks and other major projects choosing to go to later PHP versions despite which
version hosts supported. The effect this had was to force the hands of the webhosts to support higher PHP versions to stay
relevant in todays market.  
With each minimum version bump, we have gotten closer and closer to being in lockstep with some of these other forefront
projects by setting our minimum version to whatever the earliest supported PHP version was. Now is our chance to join the
pack in ditching PHP 5 and going to a minimum PHP version of 7.1.

For some reading, check out the [Go PHP 7.1][gophp71]'s amazing blog post on the issue. 

# 3. Scope
The scope of this proposal is limited to the target version and the proposed change. Broader policy changes should be left
to a different proposal / discussion.

## 3.1. Release Target
[concrete5 v9.0.0][version-milestone]

## 3.1. Goals

- Require a minimum of PHP 7.1 
- Update dependencies to their latest versions
- Define code style requirements for PHP 5.6-7.1 features

## 3.2 Non-Goals

- Establishing a set standard for minimum version requirements
- Deciding on minimum version bumps for any other version

# 4. How?
This is mostly a documentation change with some serious implications for code style.

## 4.1. Minimum PHP Version docs
All minimum PHP version docs will be updated to represent PHP 7.1 as a minimium version

## 4.2. Code Style
Instead of PSR-1 and PSR-2, we will switch to following PSR-1 and PSR-12 as is currently drafted

# 5. Examples

PHP 5.6 features:
```php
// Variadic functions
class Foo
{

    public function bar($arg1, ...$variadicArg2)
    {
        // ...
    }
}

$foo = new Foo;
$foo->bar('first argument', 'second argument', 'additional arugment', ...);


// Argument unpacking in function calls
some_function(...$arguments);
// Is the same as
some_function($arguments[0], $arguments[1], $arguments[2], ...);


// Exponential math without `pow()`
$twoToThePowerOf3 = 2 ** 3;
```

PHP 7.0 features:
```php
// Scalar type hinting
function foo(string $someString, int $someInt, float $someFloat, bool $someBool)
{
    ...
}

// Return type declaration
function foo(): string
{
    return '';
}

// Null coalesce operator instead if isset checks
$value = $array['item'] ?? 'default';

// Anonymous classes (please don't use these)
$object = new Class extends Foo {
    public function bar() {
        ...
    }
};
```
[github-link]: https://github.com/buttress/concrete5_codestyle_wg
[version-milestone]: https://github.com/concrete5/concrete5/milestones
[gophp71]: https://www.tomasvotruba.cz/blog/2017/06/05/go-php-71/
