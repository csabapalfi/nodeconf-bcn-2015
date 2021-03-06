## NodeConf Barcelona 2015

21st November 2015 marked the [Barcelona edition](http://barcelona.nodeconf.com) of the longest running community-driven Node.js conference. As part of the conference - the day after - Tom Gallacher, Hassy Veldstra and Igor Soarez from YLD delivered a hand-on Node.js Performance workshop. Many thanks to the organizers, had a great weekend! Let's dive in with a short summary of the talks and the workshop:

## V8 under the hood - Franziska Hinkelman

We got a peek into how V8 works and what kind of optimizations we can apply to application code if we really need them. A great example was how hidden classes allow machine code re-use. Check out `d8` to get more V8 insights about your JS code.

## Lessons learned from building a high traffic web-app  - Patrick Hund

[Mobile.de](http://mobile.de) (part of eBay) has moved their homepage serving 300 requests a second to node from Java making coding fun again in the process. Lessons learnt included the importance of getting to production early, pair programming and keeping it simple. Also a great war story on last minute replacing a misbehaving node module based on load testing. **People, load test!** Have you tried [minigun](http://minigun.io/)?

## IPFS and the distributed web - David Dias

The web relies on our network backbones and centralized services way too much. Loosing backbone connection or a DDoS attack can seriously affect us all. It doesn't have to be that way. [Protocol Labs](http://ipn.io/) is working on [IPFS](https://ipfs.io/) to upgrade the web using peer to peer technology built on Merkle DAGs (like git), DHTs (like BitTorrent) and much more.

## Hunting performance problems - Daniel Khan

When node gets bad press it's usually around performance (Netflix vs. express or the Walmart memory leak). To tackle problems like this we first need to understand what node is, the memory model, how garbage collection works and so on. Then we can troubleshoot memory leaks with heap snapshots and CPU-related problems with flamegraphs. [v8-profiler](https://www.npmjs.com/package/v8-profiler) and Chrome Dev Tools makes this fairly easy.

## The magic dump - Luca Maraschi

Luca told us a story of a production outage and tracking down the root cause. Lots of good examples on how to debug issues by taking a core dump and using dtrace and mdb on SmartOS.

## Middleware evolution - Eugene Pshenichniy

Eugenes' slides had really cool realtime polls built-in giving input from the audience. Based on the polls people agree that generators are not really intuitive but prefer promises and [async-await](https://jakearchibald.com/2014/es7-async-functions/) seems well received, too.

## Robots - Julian Cheal

Julien demoed all sorts of hardware from RGB LED strips to a dancing Parrot AR drone. Clearly the most jokes/laughs per talk here. Libraries to check out include [cylon.js](https://www.npmjs.com/package/cylon) and [johnny-five](https://www.npmjs.com/package/johnny-five).

## Becoming a better node dev - Igor Soarez

You might started learning node for just fun or out of necessity but to keep up your motivation it's great to bet on the long run and enjoy to keep up learning.

Igor mentioning the right mentality to keep things simple (YAGNI, no IDEs, no boilerplate, no code generation) reminded me of a great talk from Rich Hickey: [Simple made easy](http://www.infoq.com/presentations/Simple-Made-Easy). Also node has the perfect tools for 'turbo mode' learning by keeping your feedback keep really short.

We can map certain node skills to levels of capable, efficient and pro developer. An interesting idea here was README-driven development at a quite high level of maturity. Essentially breaking a problem down to small node modules in advance then writing READMEs, then tests, then code.

Another piece of great advice is to don't be afraid to open source your code early. The node.js community is a welcoming one.

## Greenkeeper demo - Stephan Bönnemann

Then we saw a short demo of [greenkeeper](http://greenkeeper.io/). This tool sends you PRs when your  dependencies release a new version. The PR could then trigger a CI run thus also allowing to automatically detect non-semver-respecting dependencies breaking our own code.

## Rapid idea devalidation - David Gruebl

We all know the feeling when a friend approaches with that amazing idea. Good to remember that a startup is basically just a bet on an idea, validate and fail early if need be.

## Coding education should be free - Michelle and Claire

Even in a such a skill shortage coding education remains expensive and inaccessible to a lot of people. [Founders and coders](http://www.foundersandcoders.com/) is set out to solve this problem by a completely free 8 week face-to-face coding course. Online resources are cool but pretty hard to stay motivated. Community helps remaining on track.
Free doesn't mean low quality though. Passionate volunteers are helping out. 8 weeks is not enough to learn everything but enough to start someone's coding career. Please, help mentoring or contribute!

## Async microservices with node - Bruno Pedro

The de-facto standard way of 'connecting' microservices is using HTTP. A message broker based approach might make this more decoupled and simpler in some cases.

AMQP (and RabbitMQ) is a great option offering lots of flexibility in the patterns used. To simplify things message consumption can actually happen via web-hooks as well using a RabbitMQ plugin. Bruno recommends [amqplib](https://www.npmjs.com/package/amqplib) as a great node module. Can't agree more. Also check out [rascal](https://www.npmjs.com/package/rascal).

## Networking for node programmers - Aria Stewart

As node developers we have to be aware of the properties and architecture of the networking protocol stack our apps communicate through. After some history Aria covered the basics of the most important network protocols from all layers: Ethernet, ARP, IP, DNS, TCP. These are nothing new but stood the test of time and important to understand them.

On some more recent new IPv6 is finally really starting to happen and we could hear a bit about p2p once again. Be sure to check out some of the [various](https://github.com/mafintosh/peerwiki) [torrent experiments](https://github.com/mafintosh/peerflix) from mafintosh and [scuttlebutt](https://github.com/dominictarr/scuttlebutt) from dominictarr.

## Advanced performance workshop - Tom, Hassy and Igor

A great hands-on workshop with a series of challenges. Warmed up with a few small exercises including one about how to [async](https://www.npmjs.com/package/async) correctly to prevent starving the event loop. We then generated flamegraphs ourselves using [linux perf tools](https://perf.wiki.kernel.org/index.php/Main_Page) and [stackvis](https://www.npmjs.com/package/stackvis) to learn to diagnose CPU-usage related problems. Next up a deep dive into the node.js memory model and we were presented with a memory leak challenge to resolve ourselves using [heapdump](https://www.npmjs.com/package/heapdump) and comparing heap snapshots in Chrome Dev Tools. Last we had a chance to try our new skills on a deliberately performance faulty application. [minigun](http://minigun.io/) proved to be a great to help generating load to aid our efforts during the whole day. All of this with lots of help and clear explanations from the guys.
