
# Changelog

<!-- ## Master unreleased -->

## 3.2.1

### Bugs fixed

- [#23](https://github.com/expez/superstring/issues/23) Fix `lisp-case` erroneously splitting on parenthesis.

## 3.2.0

### Bugs fixed

- [#22](https://github.com/expez/superstring/issues/22) Fix `lisp-case` removing special characters

## 3.1.1

## Changes

- `declare` every variable we re-export or alias, to make life easier on tooling relying on static analysis.

## 3.1.0

### Bugs fixed

- [#18](https://github.com/expez/superstring/issues/18) `camel-case` vs empty string
- [#17](https://github.com/expez/superstring/issues/17) `slice` with length outside string boundary
- [#16](https://github.com/expez/superstring/issues/16) `slug` vs uppercase diacritical marks

## 3.0.0

## New features

- [#12](https://github.com/expez/superstring/issues/12) Add `replace-last`.
- [#11](https://github.com/expez/superstring/issues/11) Add `some?` which is the complement of `blank?`.

### Bugs fixed

- Add missing cljs alias for `replace-first`.

## Changes

Most of these are motivated by the changes to `clojure.string` in 1.8.

- Bump Clojure and Clojurescript dependencies to latest.
- Rename `contains?` to `includes?` and expand input values to include `java.lang.CharSequence`.
- Rename `contains-all?` to `includes-all?`.
- Rename `contains-any?` to `includes-any?`.
- Alias `clojure.string/index-of?` replacing our own implementation.
- Alias `clojure.string/last-index-of?` replacing our own implementation.
- Extend the input value of `starts-with?` to include anything implementing `java.lang.CharSequence` to match the version in `clojure.string`.
- Extend the input value of `ends-with?` to include anything implementing `java.lang.CharSequence` to match the version in `clojure.string`.

## 2.1.0

### New features

- [#5](https://github.com/expez/superstring/issues/5) ` in `slug` now changes `ł` to `l`, instead of deleting the character.
- Add `translate`, used to translate occurrences of certain characters into something else.

### Bugs fixed

- [#5](https://github.com/expez/superstring/issues/5) `strip-accents` translated the letter `ł` to `l` in the cljs version.

## 2.0.0

### New features

- Add Clojurescript support.
- Remove `title-case`, it was duplicating `clojure.string/capitalize`.
- Various docstring improvements.

### Bugs fixed

- [#4](https://github.com/expez/superstring/issues/4) Inconsistency in the `pascal-case` docstring.  Examples were correct, prose was wrong.

# 1.1.0
### New features

- Add `char-at`, which wraps the native String/charAt
- Add `re-quote` which quotes a string, for use in regular expressions.

### Bugs fixed

- `mixed-case?` is now false on strings like "123" where no character has a case.
- `swap-case` on "ß" now returns "SS"
- Fix `starts-with?` throwing exception when `prefix` is longer than `s`.
