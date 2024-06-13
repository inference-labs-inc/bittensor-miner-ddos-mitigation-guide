### Purpose

This is a companion repo to collect community contributions and updates to the recently published [guide](https://inference-labs.medium.com/bittensor-miner-ddos-mitigation-guide-3286c63aa2d2). As mentioned there, there's currently no satisfactory generic solution for the problem where miners get DDoS'ed till they become slow and unavailable in order to shift the incentive. In highly competitive subnets there's unfortunately incentive for such behavior and honestly there's no real prevention.

### Other ideas

There was a recent [proposal](https://github.com/opentensor/subtensor/issues/504) to hide miner's IP so that they are not as easily available for attacks - I'm still reviewing the details and it might help but I think protection that essentially relies on hiding addresses is not enough. There's also a bunch of new tricks mentioned in that ticket that should be tested and saved here for reference (it mentions some whitelist script that might already exist and should be found examined) but mostly the analysis there confirms mine - third-party services can be effective but there's not appropriate service and what's available can get really expensive. Basic protection measures can help and should be deployed in any case and real protection would require protocol change (perhaps some subnet-level measures like additional Axon authentication or complete Dendrite whitelist, but most likely some global changes will be eventually required to tackle this).

### Future possibilities

It would be helpful for miners to create issues in this repo with logs (or share sensitive details privately) so that we can diagnose the specific attacks and suggest solutions and strategies. We really still don't have enough info on specifics of how typical attacks happen, a complete practical guide or a universal tool will not be possible to create without it so please contribute.

I will probably eventually break down the guide into smaller instructions for specific attack vectors: how to spot and diagnose, what prevention and palliative measures are there, more aggressive or safer-simpler treatments, is it at all possible to cure with some global changes, what tools in general can help, etc.

I also have this idea to make a simple setup script based on the guide, to automate the more boring installation/configuration steps and it could be a tool for future - once a new attack vector becomes known to us and we figure out some measures we could add it to the script so that everyone can quickly implement it for their miner allowing for quick mitigation. For now it could just help installing nginx and correctly configuring ufw or something like that. Will be great to hear some feedback on this idea before I actually start coding.

And in general remember that the guide is not a step-by-step instruction that's enough for complete protection in this form (it's not even tested that well) in this form so any feedback on any of the measures there or additions will be greatly appreciated. Always feel free to open issues and pull requests!
