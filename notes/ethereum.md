## Ethereum - May 17 2018

Participants:
* @mgoelzer (libp2p)
* @bigs (libp2p)
* vyzo (libp2p)
* @JustinDrake (Ethereum)
* Kevin (Ethereum)
* Hsiao-Wei Wang (Ethereum)

```
Use case 1:  Sharing (Justin, Hsiao-wei, Kevin)
	Sharding
		Building extension of Ethereum from scratch - new networking layer from scratch
		Interested in transpoerts and piubsub
		Envisioning a few pubsub channels per shard (eg, 100 shards)
			In sharding protocol, have notaries/validators that listen to the network 
		Vyzo:  PubSub is perfect (gossipsub) b/c people could weaponize Ethereum platform
		Justin:  when you leave and re-join do you have quality peers?
		Justin:  daemon is highest priority  
		Justin:  stable implementation, actors have high incentive to try break it, want to understand if libp2p is coming from this same adversarial mindset
		Justin:  security audits are of interest
		Gossip implementation queation from Felix:  is it based on epidemic broadcast trees paper?  Vyzo:  yes
		
Use case 2:  Transports (Felix)
	Justin working on Ethereum 2, we are more concerned about ethereum 1
	Right now just 1 broken transport
	Wish they had a more standalone transport implementation
	Ethereum 1 has a bunch of libp2p's functuonality already (DHT, routing protocols), but they are interested in zero RT handshaking, better connection crypto.  
		Simplified DTLS, don't need a ton of abstraction, would rather have standalone components, not abstracted.
		IPFS Ethereum interconnection - some conversations with Jeromy, 
		A/I:  open an issue to see how these line up
	Currently still experimenting, but once it gets vendored into their code, they want 3k lines not 50k lines
		
	Devp2p has an overlay (one that falls out of the swarm project, some other overlays)
	"Overlays" = routing approches implemented as a library and they all share a primary routing interface
		
	Question:  no authentication in floodsub today?
		
	Question:  what is the minimum number of peer connections?  Both for validators that want to access every shard, or for a normal client?

```	
		

