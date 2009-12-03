Abstract
========

CPULang is a domain-specific language for defining processors, intended for compilation to FPGA bitstreams or for synthesis to hardware.  By separating IO definitions (which are low-level) from instruction definitions (which are high-level), you can gain a large amount of flexibility.

On the compiler side, pipelining logic can be generated procedurally from the instruction set, allowing for high performance out of the box.  The same definitions could be used to run simulations and testing.  Depending on the design of the instruction set, flexible microcoding may be possible, and can be heavily optimized.

Computational units (ALUs, FPUs, decoders, etc) and caches can either be determined and placed by the compiler or customized at build time, so the same processor design can be used in multiple different configurations with no modifications.  This could allow for the design and development of a multitude of processors in parallel without a lot of the traditional problems.  This could even allow you to scale a processor automatically to max out the capabilities of an FPGA.

Questions
=========

 - What should it look like?
 - What algorithm should be used for procedural pipelining?  Is there an existing algorithm that fits?
 - How do you fit the IO to the logic without strict timing on the logic side?
 - Would it be possible for this to generate async designs?

Base languages
==============

 - Python
  - Pros: Clean, simple
  - Cons: Would likely require a custom parser
 - Ruby
  - Pros: Flexible syntax, same language as the compiler
  - Cons: Instruction definitions could be complicated
 - Scheme
  - Pros: Complete customization of syntax
  - Cons: It's Scheme.
