PHPSignatures
=============

Overview
--------

This contain signatures **with extra details** for PHP functions, methods, and properties.
These were initially part of [Phan](https://github.com/phan/phan), but have been forked in various static analysis tools (Psalm, PHPStan, etc).
These differ from other signatures in different ways

- These signatures also include types where the function/method call would be likely to fail (e.g. runtime errors)

  This differs from repos such as PHPStorm's stubs, which only contain enough information for autocompletion.
- These contain the nullable type syntax `?T`
- These also contain non-standard generic arrays (such as `array<int,T>`) and array shapes (such as `array{keyName:T}`)

  Details about the signatures are documented in more detail in [FunctionSignatureMap.php](./FunctionSignatureMap.php).

These signatures were obtained from a wide variety of sources (such as the C source code of PHP, the SVN sources of the php.net documentation, external documentation of third party PHP modules, PHPStorm stubs, bug reports, etc.)

There are minor differences in how these projects use these signatures (such as error handling and type strictness).
This repo was created as to make synchronizing fixes to these signatures easier.

- Changes may be cherry-picked (or merged) for forks of this, possibly with edits.

Layout
------

FunctionSignatureMap tracks the function and method signatures of the most recent stable PHP release.

- Delta files can be applied to obtain the function and method signatures of older releases.

DynamicPropertyMap.php contains a set of classes of PHP modules known to have dynamic properties.

PropertyMap.php tracks the union types of properties of known classes of PHP modules.
