(note: Anyone that opens an issue or pull request will be added as a collaborator with write access while we're in brainstorming mode. If you disagree with anything added/changed, just add bracketed text next to that area or something like that, such as "Discuss: Not sure I agree, we should do X instead.")


# Workstreams
Brainstorming possible workstreams


# Testing & Measurement
- Would be nice to have a standard recommended dnsperf test configuration, so across different implementers there is an apples-to-apples benchmark tool - https://www.dnsperf.com/
- This can also be used by independent measurement researcher & orgs

# Resolver Discovery & Selection
- Needs to handle one or more FORWARDERS between client and full resolver
- If done right, will provide _DNS Traceroute_ functionality, at last
- Overlapping RFC-1918 scopes may result in forwarders and/or the final resolver not being directly accessible from the client
- Forwarders and resolvers might not have public FQDNs and may not even have private FQDNs
- Need some unique name in an available namespace that is guaranteed to not collide
- Maybe base on IPv6 ULA or some other GUID name-generator

# Canary Domains / Conflict Detection
- Should only be local and should be relative to server's locally scoped name (if that is even possible)
- E.g. canary-domain.forwarder-or-resolver-name.local (not literally, just semantically)

# Scaling / Architecture Discussions
- Support for forwarding may be necessary to maintain parity with current scaling (e.g. ratios)
- New DNS flag or EDNS flag or OPT to signal request to encrypt (including propagation of flag and encryption)
- May require new kind of flag or OPT that is NOT hop-by-hop, but rather is propagated to from the originating client to the full resolver
- See "Recursive-to-Authoritative" below as well

# Security / Attack Resilience
- Downgrade resistance is necessary
- DNSSEC signing is very likely a requirement regardless of specific mechanism(s)
- DANE TLSA records should probably be mandatory unless someone can provide counter-examples

# DoT Positioning
- Propose that DoH exclusive of DoT is not acceptable to the DNS community at large
- Propose that resolver choices need to include DoT-only providers, and that DoH vs DoT needs to be exposed to users if a provider supports both
- Propose DoT blocking be used as a proxy signal for network policy (substitute for canary domains)

# DNS Data Policies
- Best practices concerning logging, use, disclosure, etc.

# Opt-in vs opt-out
- Generally, opt-out is a terrible idea, something that has been demonstrated repeatedly.

# RPZ and Trust Anchor Issues
- Trust anchor(s), provisioning/publishing of such, maybe via resolver-naming authoritative RRs? Self-signed or not?
- Use trust anchors to auto-discover split-DNS environment (resolver type)?
- Use trust anchors to auto-discover RPZ servers (or combined RPZ server-resolvers)?
- Order trust anchors to prevent abuse or to scope functionality (no squatting, maybe private domains and/or RPZ only), including RPZ-first vs RPZ-second (no-cache vs cache)
- Signing RPZ-specific responses?
- Changes to RPZ architecture to allow mixing RPZ and non-RPZ resolvers?
- Add structure to current unordered "nameserver" list in /etc/resolv.conf, similar to SRV semantic mechanisms?

# Recursive-to-Authoritative
- Encryption generally is okay, but simply replacing Do53 with ADoT (for example) causes immediate scaling pain
- "Poster child" of scaling: large recursive operator (google or cloudflare) to large authority operator (godaddy)
- Site-to-site encryption mechanisms may scale better
- Separate transport from DNS messages to facilitate scaling
- Open question: is it desirable/necessary to facilitate anonymity of resolver operators, or would a mechanism that requires enrollment or coordination or identification be acceptable?

# Other Random Stuff
- Develop short presentation that any participant can use to do a 5-minute lightning talk overview of EDDI at workshops/meetings/conferences
