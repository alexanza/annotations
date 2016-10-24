## Changelog

### 1.3.0

This release introduces a PHP version bump. `doctrine/annotations` now requires PHP
5.6 or later to be installed.

A series of additional improvements have been introduced:

 * support for PHP 7 "grouped use statements"
 * support for ignoring entire namespace names
   via `Doctrine\Common\Annotations\AnnotationReader::addGlobalIgnoredNamespace()` and
   `Doctrine\Common\Annotations\DocParser::setIgnoredAnnotationNamespaces()`. This will
   allow you to ignore annotations from namespaces that you cannot autoload
 * testing all parent classes and interfaces when checking if the annotation cache
   in the `CachedReader` is fresh
 * simplifying the cache keys used by the `CachedReader`: keys are no longer artificially
   namespaced, since `Doctrine\Common\Cache` already supports that
 * corrected parsing of multibyte strings when `mbstring.func_overload` is enabled
 * corrected parsing of annotations when `"\t"` is put before the first annotation
   in a docblock
 * allow skipping non-imported annotations when a custom `DocParser` is passed to
   the `AnnotationReader` constructor

Total issues resolved: **15**

- [45: DocParser can now ignore whole namespaces](https://github.com/doctrine/annotations/pull/45)
- [57: Switch to the docker-based infrastructure on Travis](https://github.com/doctrine/annotations/pull/57)
- [59: opcache.load&#95;comments has been removed from PHP 7](https://github.com/doctrine/annotations/pull/59)
- [62: &#91;CachedReader&#92; Test traits and parent class to see if cache is fresh](https://github.com/doctrine/annotations/pull/62)
- [65: Remove cache salt making key unnecessarily long](https://github.com/doctrine/annotations/pull/65)
- [66: Fix of incorrect parsing multibyte strings](https://github.com/doctrine/annotations/pull/66)
- [68: Annotations that are indented by tab are not processed.](https://github.com/doctrine/annotations/issues/68)
- [69: Support for Group Use Statements](https://github.com/doctrine/annotations/pull/69)
- [70: Allow tab character before first annotation in DocBlock](https://github.com/doctrine/annotations/pull/70)
- [74: Ignore not registered annotations fix](https://github.com/doctrine/annotations/pull/74)
- [92: Added tests for AnnotationRegistry class.](https://github.com/doctrine/annotations/pull/92)
- [96: Fix/#62 check trait and parent class ttl in annotations](https://github.com/doctrine/annotations/pull/96)
- [97: Feature - #45 - allow ignoring entire namespaces](https://github.com/doctrine/annotations/pull/97)
- [98: Enhancement/#65 remove cache salt from cached reader](https://github.com/doctrine/annotations/pull/98)
- [99: Fix - #70 - allow tab character before first annotation in docblock](https://github.com/doctrine/annotations/pull/99)