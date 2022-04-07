# Processor core

The processor should be as simple as possible and as complex as necessary. As much as possible should be moved from the hardware level to the software level. This means it won't be backwards compatible at all though it may be possible to create (slow) emulation layers.

Take the following ideas with a grain of salt. They may change radically if they turn out to be stupid (which they probably will).

I think I will write this in Bluespec.

## Branch prediction

This will not be implemented in the classical way. Instead there will be the following instructions

(branch-in-n-cycles 5 0xaddress)
(branch-in-n-cycles-if 5 r5)
(branch-in-n-cycles-less-than 5 r5 r8)

where n needs to be at least the processor specific instruction fetch delay.

## Caches

There will be no implicit caches as they often cache stuff that you don't need and also increase complexity. Instead there will be be general memory instructions and processor specific address ranges that address different caches / main memory.

## Speculative execution + Out-of-order execution

Yeah not gonna happen you know what this led to. I think many things can be done by the compiler (reordering instructions).

## SIMD

Not going to happen at the start. Maybe later a RISC V like design so independent of the size of the data the same instruction to not require complex code that needs to split the data into blocks and handle the remaining data etc.

## Registers

At the beginning not existing. Caches could be used as register-like things.

## Bits

64 bits probably not all working for addressing.

## IO

No idea about that. DMA etc. would probably be important.

## Endianness

Don't know yet.

## Floating point



## Fixed point


## Pipelining

Probably yes. Has it's own problems of course.


## ALUs


## Graphics


## Virtual memory

Not existing. Most programs should know how much memory they need where and for the rest allocate globally.



## DRAM vs SRAM




## Multicore



## Interrupts

## Interesting articles

https://en.wikipedia.org/wiki/Processor_design

https://en.wikipedia.org/wiki/Superscalar_processor#Alternatives