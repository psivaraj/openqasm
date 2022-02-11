# OpenQASM Working Groups

As outlined in the OpenQASM [governance document](governance.md), the Technical Steering Committee (TSC)
will, from time to time, elect to create **Working Groups** (WG) to study issues. The TSC will appoint a **Contributor**
as **Chair** for each WG. A WG shall submit a language RFC or pull request to the OpenQASM specification
for review by the TSC at an agreed upon date. A WG will be automatically disbanded upon acceptance or
(final) rejection of the RFC/pull request.

## Current Working Groups

### Generics and circuit families

**Objective**: Recommend what range of generics / parameterised circuit family functionality (beyond angle parameters) would be suitable for inclusion in OpenQASM, and what syntax should be used for it.

Chair: Niel de Beaudrap  
Members: Colm Ryan, Andrew Cross, Ali Javadi, Blake Johnson, Matthew Amy

### Types and casting

**Objective**: Define type hierarchy and implicit casting rules.  
**Questions**:

 * Any implicit casts?
 * What explicit casts are allowed?
 * Registers vs arrays?
 * Can you index into integers and get bit value?
 * Is an int equivalent to an array of bits?

Chair: Michael Healy (IBM Quantum)  
Members: Niel de Beaudrap, Hiroshi Horii, Blake Johnson, Colm Ryan, Luciano Bello, Prasahnt Sivarajah, Yunong Shi, Jake Lishman

### Pragmas


**Objectives**: Define a pragma syntax, standard directives, the standard behavioral expectations for interacting within a toolchain.  
**Questions**:

 * What should be the pragma syntax? Should there be more directives (e.g., `#if`, `#define`), or should the functionality avoid anything like a pre-processor?
 * What should be supported in the language instead of as a pragma?
 * What is not supported by pragmas
 * Conventions:
    * How should multiple OpenQASM tools interact with pragmas?
    * How do pragmas that may operate at different levels of the MLIR different stages of processing determine when and where to be processed?
    * Syntactical conventions for independent developers

Chair: Jeff Heckey (AWS)  
Members: Ali Javadi (IBM Quantum)
BẢO Bach Gia (Ho Chi Minh University of Technology), Jake Lishman (IBM Quantum), Jack Woehr (IBM Quantum), Lev S. Bishop (IBM Quantum), Michael Healy (IBM Quantum), Thomas Alexander (IBM Quantum), Yunong Shi (AWS)

### Dynamic Deference & Allocation

**Objectives**: Formulate response to issues raised by [Physical mapping of dynamically dereferenced qubits #307](https://github.com/Qiskit/openqasm/issues/307)
 * Provide concrete examples proving this cannot be dealt with in OpenQASM 3 as the spec stands
 * If in scope, provide rough solutions.
 * Keep in mind the difference between dynamic dereference and dynamic allocation.
 * Capture implicit assumptions that would make it hard to introduce this in future.

**Questions**:
 * Do dynamically deferenced qubits break hidden assumptions in the current spec?
    * Gates may have different implementations for each dynamic qubit
    * Multiple qubit gates require connectivity or swaps
    * Index out of bounds in runtime?

Chair: Dor Israeli (Quantum Machines)
Members: Thomas Alexander (IBM Quantum), Niel de Beaudrap (Sussex), Phillip Schindler (Innsbruck), Bettina Heim (Microsoft)

## Past Working Groups

### OpenPulse

**Objective**: Define a pulse grammar "openpulse" to be used for microcoding of gate instructions with
OpenQASM `defcal`'s.

Chair: Thomas Alexander (IBM Quantum)  
Members: Blake Johnson, Colm Ryan, Derek Bolt, Peter Karalekas, Lauren Capelluto, Michael Healy, Prasahnt Sivarajah, Yunong Shi, Steven Heidel