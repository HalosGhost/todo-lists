 Programming Languages
=======================

- [ ] ``bgl`` (pronounced "bagel")

  - [ ] C base; probably llvm
  - [ ] Completely reworked type system

    - [ ] integral types          -- ``{u,s}{8,16,32,64,128}``

      - [ ] arbitrary bit-width? (since LLVM IR offers it)
      - [ ] arbitrary-radix literals (e.g., ``2#1111 == 8#17 == 16#f``)

        - [ ] Could implement ``NULL`` as simple sugar for ``0#``

          - [ ] All primitive types (and their fancy pseudo-generics) will be non-nullable by-default
          - [ ] A ``nullable`` qualifier to allow for ``NULL`` (i.e., ``b#`` where ``b`` is some unsigned integer) to be valid

    - [ ] flexible-width integers -- ``bigint``
    - [ ] real types              -- ``r{8,16,32,64,128}``

      - [ ] IEEE 754:2008 in all likelihood since LLVM IR doesn't expose binary reals
      - [ ] LLVM doesn't expose quarter-precision reals either so that'd either be manual or it wouldn't happen

    - [ ] arbitrary-precision real -- ``bigreal``
    - [ ] unicode char             -- ``char``

      - [ ] will need to decide how to handle the representation (I'm thinking UCS-6 actually…)

    - [ ] boolean types            -- ``bool``

      - [ ] might just be implemented as a 1-bit wide integer (``i1`` in LLVM IR)
      - [ ] implication of {,un}signed booleans?

    - [ ] bitmask type or bitwise assignment operator or bitwise literals

      - [ ] essentially, some way of assigning a variable's bits directly rather than using multiple bitwise operators or hoping integer literals correctly translate to the bitmask you want

    - [ ] Haskellian class-like / Rustian trait-like pseudo-generics

      - [ ] probably implemented through some form of fancy unions

        - [ ] LLVM IR doesn't expose a union type, so this might be rough

      - [ ] ``{u,s}int`` -- accepts any fixed-width integral type of the specified signage
      - [ ] ``real``     -- accepts any fixed-width real type
      - [ ] ``numeric``  -- accepts any fixed-width numeric type

    - [ ] Remove all implicit casting and promotion

      - [ ] Exception: functions taking arguments of the fancy pseudo-generics must be callable with any matching primitive type.

    - [ ] Remove implicit array-to-pointer decay

      - [ ] A function specifying its argument as an array must be called with an array argument (or one cast to that type)
      - [ ] Note: Arrays as arguments are still passed by-reference, this just makes a slightly more clear separation between pointers and arrays

  - [ ] Formalize ``{}`` into lexical scoping operators (think of this as Rustian lifetimes)
  - [ ] ``===`` operator (think ``+=`` but with ``==`` instead of ``+``)
  - [ ] Visibility qualifiers / namespaces?
  - [ ] Function Literals

    - [ ] Implements simple anonymous function support
    - [ ] Implements closures
    - [ ] Implements much simpler methods for class/instance-model OOP-esque programming (though that is definitely not a priority)
    - [ ] Syntax something like: ``type (* id) (type) = @(name) { /* function body */ };``

  - [ ] Array declarations should have the brackets next to the type; e.g., ``u64[] identifier``
  - [ ] Multi-dimensional VLAs (matrix math programmers, rejoice!)
  - [ ] Replace ``switch`` with something like a Haskellian ``match`` (offer them both?)

    - [ ] an operator for ``switch`` or ``match`` expressions

  - [ ] Tentative compiler name: ``boil``.
  - [ ] Tentative simple build system: ``bake`` :P
