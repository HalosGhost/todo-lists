 Programming Languages
=======================

- [ ] ``bgl`` (pronounced "bagel")

  - [ ] C base; probably llvm
  - [ ] Completely reworked type system

    - [ ] integral types           -- ``{u,s}{8,16,32,64,128}``
    - [ ] arbitrary-width integers -- ``bigint``
    - [ ] real types               -- ``r{8,16,32,64,128}``

      - [ ] IEEE 754 or binary real; both?

    - [ ] arbitrary-precision real -- ``bigreal``
    - [ ] unicode char             -- ``char``

      - [ ] will need to decide how to handle the representation

    - [ ] Haskellian class-like / Rustian trait-like pseudo-generics

      - [ ] probably implemented through some form of fancy unions
      - [ ] ``{u,s}int`` -- accepts any fixed-width integral type of the specified signage
      - [ ] ``real``     -- accepts any fixed-width real type
      - [ ] ``numeric``  -- accepts any fixed-width numeric type

    - [ ] Remove all implicit casting and promotion

      - [ ] Exception: functions taking arguments of the fancy pseudo-generics can be called with any matching primitive type.

    - [ ] Remove implicit array-to-pointer decay

      - [ ] A function specifying its argument as an array must be called with an array argument (or one cast to that type)
      - [ ] Note: Arrays as arguments are still passed by-reference, this just makes a slightly more clear separation between pointers and arrays

  - [ ] Formalize ``{}`` into lexical scoping operators (think of this as Rustian lifetimes)
  - [ ] Function Literals

    - [ ] Implements simple anonymous function support
    - [ ] Implements closures
    - [ ] Implements much simpler methods for class/instance-model OOP-esque programming
    - [ ] Syntax something like: ``type (* id) (type) = @(name) { /* function body */ };``

  - [ ] Array declarations should have the brackets next to the type; e.g., ``u64[] identifier``
  - [ ] Multi-dimensional VLAs (matrix math programmers, rejoice!)
  - [ ] Replace ``switch`` with something like a Haskellian ``match``.
