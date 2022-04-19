# Programming Language

There should be multiple levels of hierarchy so the language is built from the bottom (assembly language) up. Every level should prove it's correctness based on the previous level.

## Permissions

Process isolation happens at the language level instead of the operating system level. So
(read-file file) needs a specific permission so it is allowed. With (request-permission read-file file) the application can interactively request that permission.

## Scheduling

Only cooperative scheduling will be implemented. But applications need to prove that they don't exceed some specific time of exclusive runtime.

## Assembly level

The basic instructions like

(add dest-addr src1-addr src2-addr)
(dereference value-addr addr-addr)
...

You need to prove that you don't to bullshit (e.g. dereference invalid data). (The hard question is how exactly.

## Middle level

If you've proven that (add a b c) and (add a a d) are valid then (set a (b c d)) is also valid.

## High level

### Lifetimes etc.

It should be possible to show that lifetimes (like in Rust) can be lowered to a lower level liveness proof.