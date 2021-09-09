# Example Dcl Component Library

An example npm package project for building a decentraland component library!


<br/>

# How It Works

This is a example of a component library to be used in Decentraland projects!

If deploying your own, you can use [npm scoped packages](https://docs.npmjs.com/creating-and-publishing-scoped-public-packages) to deploy an npm package that begins with your organization (optional, but recommended).

<br/>

# Consuming This Library In A Project

To consume the component library, create a new decentraland project on your loal machine. 

Then, install the component library via npm using whatever name you chose. something like this:
```bash
npm install @example-org/dcl-components-library
```

Then project will list `@example-org/dcl-components-library` as a dev dependency, and all the fancy awesome components can be used in your other javascript or typescript files!

For example, here's how easy it is to add the "spinning crate" component onto your stage and control how fast it spins!

```typescript
import { SpinningCrate } from '@example-org/dcl-components-library';

// Create the entity
const spinningCrate = new SpinningCrate()

// Add the entity to the engine
engine.addEntity(spinningCrate)
```

# Peer Dependencies

Virtually all project for building things in Decentraland depend on the _Decentraland Entity Component Sytem._

This is the [decentraland-ecs](https://www.npmjs.com/package/decentraland-ecs) npm package. This project declares `decentraland-ecs` as a "peer dependency" which means it does not get packaged in with the final build. Instead, it uses the `decentraland-ecs` package that the consumer has already installed in his or her project.  

Note that consumers must use _at least_ the version of `decentraland-ecs` that it specifies in the package.json of this project.  

<br/>

# CI / CD Automation Stuff

We can take advantage of the fact that npm versions can have additional text after the "semver" code.

Consider this scenario: you are a developor adding a componet to this library. Suppose the library is currently at version `1.2.3`, and since you added a non-breaking change you want to update it to `1.2.4`. 

_To publish an npm package, all you need to do is run `npm publish`._ And with the right environment variables, we can run `npm publish` on our build servers!

A fancy build script can even take the `1.2.4` in our package.json of the component library, and publish a version of `1.2.4-alpha` when PRs are opened. 

Then once they are merged into dev, another build script can publish it with the version `1.2.4-beta` or `1.2.4-staging` (the namings can be whatever you decide)!

Then finally, when we are happy with the staging version we can cut a final `1.2.4` version, redeploying the working package with the new version. 


<br/>

# Contributing

We're looking for creative people to help us build awesome stuff for Decentraland!

You're always welcome to join our coding fam:

 - Meetup - https://www.meetup.com/ethbuilders/

 - Slack - https://join.slack.com/t/nyc-blockchain-devs/shared_invite/zt-9q57smnm-HHkovOCbhT_i_~U2V3Nuew

