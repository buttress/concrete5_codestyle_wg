# Dealing with deprecated features

# 1. Summary
The core makes use of methodsa and other features that have been derecated. The code that make use of deprecated features should be refactored to use the replacement code.

# 2. Why Bother?
Methods are deprecated rather than removed right away, to provide backward compatibility and also time to bring affected code into compliance with new standards. The goal is to remove the deprecated features eventually. This is impossible as long as the core uses the methods itself. The core using deprecated features sets a bad example for 3rd party developers who might end up following the bad example and also depend on the deprecated code.

# 3. Scope
The scope of this proposal applies to any future version that includes deprecated features, in use by the core.

## 3.1. Release Target
[concrete5 v9.0.0][version-milestone]

## 3.1. Goals

- Remove all usage of deprecated features by the core
- Deprecated methods should be gutted and made to go through new code
- Place helpful comments for how to migrate away

## 3.2 Non-Goals

- Removing deprecated features themselves

# 4. How?

## 4.1. Refactor any code using a deprecated feature
A lot of code can be replaced using search (and replace). Other code might have to be partly rewritten. There will be a fair amount of work required.

## 4.2. Refactor deprecated methods
Deprecated code should be gutted and made to go through new code at all times with helpful comments for how to migrate away. Only placing `@deprecated` will not be enough.

# 5. Examples

The file `/concrete/src/Application/Application.php` contains the deprecated method `PackageList::get()`:
```php
public function setupPackageAutoloaders()
{
    $pla = \Concrete\Core\Package\PackageList::get();
    $pl = $pla->getPackages();
    ...
}
```

Refactored
```php
public function setupPackageAutoloaders()
{
    $pl = $this->make(PackageService::class)->getInstalledList();
```

[version-milestone]: https://github.com/concrete5/concrete5/milestones
