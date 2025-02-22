# Change Log

All notable changes to this project will be documented in this file.
This change log follows the conventions of
[keepachangelog.com](http://keepachangelog.com/).

## [Unreleased][unreleased]

Nothing so far.

## [1.6.0] - 2021-09-08

### Added

- A new predefined value, `svg-attrs`, which starts out as an empty
  map, but can be redefined to add arbitrary SVG attributes to the
  top-level SVG node of your diagram (for example, to set a background
  color for the entire diagram).

## [1.5.0] - 2020-07-12

### Added

- Two new functions, `wrap-link` and `wrap-svg` which allow you to
  create hyperlinks and arbitrary SVG elements around sections of your
  drawings.

## [1.4.3] - 2020-05-15

### Fixed

- Short-lived version 1.4.2 was not properly built for release before
  publishing to npm.

### Changed

- `defattrs` now takes an attribute expression rather than only a
  resolved attribute map as its second expression, so you can use the
  concise attribute mini-language to build new attributes based on
  existing ones.

### Added

- You can now pass `:next-row-height` as an attribute to `draw-box`
  when you need to change row heights as you draw the first box of a
  new row. This makes it more practical to have variable-height rows,
  while still having the automatically-drawn row headers appear in the
  correct posititons.
- The user guide now shows examples of how to draw vertical text and
  boxes which span more than two rows but which are not
  variable-length gaps.


## [1.4.1] - 2020-04-04

### Fixed

- Invoking the `generate` function with a single argument was not
  working properly any longer because of a problem handling default
  JavaScript arguments from ClojureScript code. (Sorry, I am really
  new at the JavaScript/ClojureScript worlds!)
- Generation of the user guide using the local extension now uses
  the new embedded SVG tag mode, to avoid HTML structural issues.

## [1.4.0] - 2020-04-05

### Added

- The `svg` element is now rendered with a proper `viewPort` attribute
  which allows the host page to make it responsive by styling it with
  `max-width="100%"`.
- You can generate a bare `svg` element for inclusion in an HTML
  document by supplying the command-line flag `--embedded` or `-e`, or
  invoking the `generate` function with a new second `options` object
  in which the property `embedded` is `true`.
- New helper functions to support drawing bit-fields from integers.
- New helper functions to support drawing padding until a particular
  address is reached.
- A `draw-inline-gap` function to support drawing discontinuities in
  single-row diagrams.
- The ClojureScript namespaces `clojure.set` and `clojure.string` and
  the JavaScript `Math` object are now available for use by your
  diagram code.

### Fixed

- A new version of the Small Clojure Interpreter is used, which
  enables `dotimes` for index-based iteration within diagrams.
  Previously it would fail because it delegated to the forbidden,
  potentially non-terminating `loop` form.

## [1.3.0] - 2020-03-29

### Added

- A command-line interface to make it easy to use from the shell, and
  support integration with asciidoctor-diagram.
- Finished the language guide documentation site.

### Fixed

- The `draw-column-headers` function was missing its zero-arity
  version, which is the most commonly useful one. It was only a quirk
  of the compiled Clojurescript that was allowing diagrams to work.

## [1.2.0] - 2020-03-26

### Added

- Continued fleshing out the language guide documentation site.

## [1.1.0] - 2020-03-24

### Fixed

- Subscripts were not working properly in Firefox

### Added

- Ability to draw superscript elements as well, even in conjunction
  with subscripts.
- Started creating a documentation site for the domain-specific
  language with which diagrams are created.

## [1.0.1] - 2020-03-22

This was the first release that actually worked when installed via
`npm`.

### Fixed

- The previous release was accidentally published as a development
  build, not a release build, which will not work with out
  shadow-cljs.

## 1.0.0 - 2016-03-22

Intial early release.

[unreleased]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.4.3...HEAD
[1.4.3]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.4.1...v1.4.3
[1.4.1]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.4.0...v1.4.1
[1.4.0]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.3.0...v1.4.0
[1.3.0]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.0.1...v1.1.0
[1.0.1]: https://github.com/Deep-Symmetry/bytefield-svg/compare/v1.0.0...v1.0.1
