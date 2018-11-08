## Summary

Call recording:  [https://youtu.be/YoTwZ5vFi80](https://youtu.be/YoTwZ5vFi80)

We had a good but very wide-ranging discussion.  Key issues raised:
 - Do we even want "governance" at this time or is it too early?
   - And should it even be called that?
 - Convert biweekly call to an issues call (with updates done async)
 - Centralize issues in `libp2p/{lang}-libp2p`?  Some support but not full consensus.
   - Tooling like Zenhub?
 - What's in the spec and what isn't?
   - Wire protocols definitely
   - Key algorithsm like dialing
   - Key abstractions like a DHT
   - Maybe internals are not mandatory in spec, e.g., switch/swarm abstraction
   - Still open question:  are consumer interfaces part of the spec?  Does every language need to implement the same set of objects and methods?



## Raw discussion notes


@why:  strengthen the spec and let people implement against that
@mgoelzer:  +1


@raul:  python implementation funded by Ethereum 
 - Pegasys looking at Java (native implementation)
 - Harmony (funded by EthFndn) also looking at 
 
Raul notes from DevCon:  https://docs.google.com/document/d/1nTa5xL9-Cs8FaHITCAKG2dmlPuU4ps-plC_54lx4EVc/edit

@Molly:  IPFS has been holding off on governance
@mgoelzer:  Yes, but distinction is that libp2p is a library that other people are investing in whereas IPFS is more like a "finished product"

@Mikeal:  Difference is 99% of dev on IPFS is done by PL, whereas the people who are showing up right now with their own development resources
 - Questons:  are the people adopting it using the entire stack or just some parts?
   - Raul:  most implementors are trying to get a subset of modules to work (ie, interop). List of modules:  https://github.com/ethresearch/p2p/issues/4#issuecomment-436702674
   - Raul:  next question is how to do we handle the maintenance burden?


@raulk:  libp2p is a standards-based library with interop expectations, which is different from IPFS

@mikeal:  Need to define the boundaries of the project.  Needs to be communicated more visibly than just in the spec, most people won't read the spec.
  - What are the boundaries of the platform layer (in libp2p org) vs ecosystem (other GH orgs)
  - Rauk:  need to be clear on what is in spec
 
Wire protocols:
 - multistream / muxers
 - Transport encryptions like SECIO
 - Protocols written on libp2p like ping and Identify
 - PubSub, Relay, how we use websockets
Spec currently also covers APIs:
 - Switch/swarm

Distinction b/t someone implemements libp2p vs someone who conforms to libp2p internal abstractions (like switch/swarm)

What would a "libp2p-compatible" badge mean?  Probably just wire format.

@vyzo:  +1 on Why that as long as the wire protocol is compatible it can be called libp2p.  If some language doens't want to implemented switch/swarm internally, but has the same basic components and speaks the wire protocol, we should call it libp2p.

 - Steb:  yes agree but if they don't implement same pluggable abstractions, then we don't call it libp2p

Molly:
 - various flavors of governance ranging from non-existent to a medium-complexity governance model where people have some resources all the way to massive bureaucracy
   - What is my recourse if people are not merging my PR? <-- molly's recommendation
   
Mutable governance (Mikeal) - needs to be able to evolve

Different contribution models for specs vs code
 - Nodejs limits comments on spec, but not on code.  Bc it's too easy to comment on ideas and you get a lot of unfocused comments.
 - Nodejs has a lightweight consensus governance template.  Could be a good doc to start with (written by Mikeal incidentally)
 - Functioning governance should force decisions to be made, rather than PRs getting stuck.  It unblocks people.  Not about lording over people.

Molly:
- Should we call it "governance" or something softer?  "Governance" may sound too consequential and weighty

Raul:
 - thinking about structure
 - what is the "entry point" to the overall project
 - how can we keep track the state of all the implementations?
 - what is the "public face" of the project?
 - maybe it's not community governance vs just community alignment

Mikeal
 - A lot of foundations want libp2p to go into their foundation.  The stronger our governancce is when we go in, the less problems we have.

mgoelzer:  should we just let people run free as long as they conform to wire protocols?
 - why:  this is too extreme, we should be giving some guidance
 - define so algos like connection mgr logic, how dialing works, streams, etc
 - so the spec becomes wire protocols + key algorithms like conn mgr, dialing
 - raul:  we want a common arch so we can speak about "how libp2p works" instead of "this is how py-libp2p"

Raul:
 - centralize issues to a single repository
 - each implementation (go, js, etc) should centralize
   - go-libp2p-* issues would move to go-libp2p issues with labels
   - vyzo:  seems too extreme to put all issues in a single issue
   - why:  zenhub?
    - raul not quite good enough, users need to see issues in one place

Why/mike:
 - need to improve modularization
 - but going to a monorepo with `go mod` is too extreme

AI:
  - do a call that's just on blocked issues, this is a good way to start to see who the "maintainers" are likely to be under any future governance


