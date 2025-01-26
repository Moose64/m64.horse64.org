<!-- For license of this file, see LICENSE.md in the base dir. -->

Features of Moose64
===================

**WARNING, THIS PROJECT IS SUPER UNFINISHED, SOME OF THIS ISN'T
IMPLEMENTED YET.**

Keep in mind many statements in this document are
**subjective.** Nevertheless, Moose64 has the following features:

- Simpler than C++ or Rust, being a focused and streamlined
  lowlevel OOP language, [(see more about **streamlining**...)](
  #a-focused-design)

- Borrows its syntax and approachable look from [Horse64](
  https://horse64.org/),

- Great C inter-operability,

- Expert manual memory management as found in many
  systems programming languages,

- Ownership features for memory safety l/ike `defer`,
  `add_own()`/`del_own()`, and array length checks, [(see
  more about **safety**...)](#measured-safety)

- Avoids exceptions with instead a simpler `failable` handling,
  [(see more about **simple code flow**...)](#a-clear-code-flow)

- Amazing integration with the Horse64 ecosystem.

If you're a beginner, you may want to learn
[Horse64](https://horse64.org) instead.

For how to use Moose64, [check out the
introduction](/docs/Introduction.md).

Read onward for more detailed feature explanations.

A focused design
----------------

Moose64 offers a modern, streamlined, and ocused
design, with the following advantages:

- **Easy-to-read no-nonsense syntax with no historical baggage.**

  This matters for: 1. reducing dangerous
  security errors by misunderstanding complex rarely used
  features (a risk e.g. as perhaps seen in advanced C++), 2.
  reduced difficulty of learning due to clear syntax rather
  than arcane double meanings (as e.g. perhaps seen in C).

- **Core safety features are used mostly consistently by
  demo code and core code, and weren't tacked on later.**

  This matters for: not having features like auto ref counting or
  defer regarded as non-essential addons, misunderstood, and/or
  underused (as e.g. perhaps seen in historical C++ code).

- **Not making safety features time-consuming to master,
  to try to make unsafe shortcuts unappeailng.**

  This seems to be a problem many programmers perceive
  regarding the complexity of Rust's safety mechasnisms.

Measured safety
---------------

Moose64 brings lowlevel safety features that
are easy to use, consistently shown in most demos, and clear:

- **With block-level `defer`, local memory ownership is
  easily handled.** This statement is 1. easy to understand,
  and 2. easy to use correctly compared to e.g. C's `goto error`
  or the comparatively complex code flow of a C++ exception.

- **With available auto ref counting, non-local memory ownership
  is easily handled**, and it's used mostly consistently. (If
  you find it missing somewhere, please suggest improvements.)

- **Unnecessary complexity was avoided,** to make a safe and
  reliable code flow relatively painless to write. For
  example, there is no complex garbage collector, no complex
  ownership semantics, no borrow checker, no complex
  asynchronicity, and so on.

A clear code flow
-----------------

Moose64 tries to make the code flow and side effects obvious,
while remaining approachable and flexible:

- Using the `failable` semantics to easily check if a call
  succeeded via `failed()`, and to propagate errors via
  `return failed`, without the comparatively complex leaps
  of exceptions.

- Using no async nor promises, but straightforward event facilities
  and callbacks that are usually non-threaded.

- The `struct` OOP is very extensible via composition,
  while avoiding the obscured code flow of virtual overrides
  or complex inheritance tree.


