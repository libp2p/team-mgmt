# libp2p Core Sync up July 12, 2018

- **Moderator:** @mgoelzer
- **Notetaker:**  @mgoelzer
- **Attendees:**
- @diasdavid
- @jbenet
- @why
- @tomaka
- @vasco-santos
- @cole
- @lgierth
- @stebalien

## Moderator checklist

- [ ] Ensure that there is a notetaker
- [ ] ~~Start recording~~
- [ ] ~~Call for additional agenda items~~

## Notes

- Have a separate tab for PL-specific goals like FC
- why:  at project level we want more agreement about what features we want to build out
	- cole:  stable and tested QUIC, gossipsub
	- why/cole:  interop testing, common test interface
		- mike:  is this related to common Go interface for all languages?
		- why:  no, the protocol is the common interfaces
	- cole:  stebalien says mock net is sufficiently general for describing topology
		- steb:  but implementation is not mature
	- david:  js has interfaces well documented and tested now
		- cole:  is integration testing just protocol testing?
		- david:  yeah, and we should consider interface testing
		- mike:  who can be interop DRI?
		- david:  right now JS is the furthest along
		- cole:  what about a test DSL and an interpreter written in each language
		- david:  yes, but that is complex, we need something sooner
		- juan:  use IPTB to talk to the RPC interface of each language
	- mike:  let's turn to rust-libp2p
		- pierre:  we're working right now on libp2p in polka and parity
		- juan:  maybe we could give rust team a dedicated sheet of goals?
		- pierre:  right now it's probably faster
		- juan:  testing at scale should be a goal for rust-libp2p also
			- including testing against eclipse attack
		- david:  let's get more people in the rust community on rust-libp2p (examples, docs, videos)
			- need to figure out maintainers for rust b/c pierre and toralf are busy
	- mike:  create a libp2p/notes repo for things that are beyond 2018
	- mike:  let's talk about go
		- why:  here''s what we want to do in 6 months:
			1.  get memory usage down (peerstore)
			2.  transports - Tor and QUIC, implemented and usable
			3.  connectivity issues - you cannot dial to about 60% of nodes
			4.  making nodes not DHT nodes by default
		- Lars:  here are a few more
			5.  DHT interop - general JS and Go objective
			6.  daemon
			7.  gossipsub
			8.  release process
		- Juan:
			9.  Yes release process is important
			10.  We need to massively level up our testing infra
