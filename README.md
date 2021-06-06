# btccapital 

An open-source model for building bitcoin native organizations.

## overview

`btcapital` is the topmost level of an organization, representing the individual/group bringing capital into the organization.

`btccapital` flows down into an organization where each level is defined by a type of bitcoin spending policy.

This usually originates from a single signature or many single signatures each representing an single investor. 

There could be cases where a group of investors start at this level out of a multi-signature, for example a capital fund.


```bash

git clone https://github.com/vmenond/btccapital
cd btccapital
tree -d .

btccapital:
├── reserve - long
└── operations - medium
   ├── live - short
   ├── renumeration - short	   
   └── resources - medium
```

Eg periods:

- long = 5 years
- medium = 1 year
- short = 1 month

<hr>

At the topmost branch we find two scripts between board members of the organization:

## reserve

> A script requiring all board members.

When an investor represented by `btccapital` funds a business, it does so by funding the long term `reserve` first.

This is also where company revenue is collected.

From `reserve` funds, the board members decide how much will be required for operating over a medium term and according fund `operations`.

## operations

> A script requiring only a few elected board members.

From operations fund, the board members must then decide how much of their funds will be required for operating within a defined short term period.

They must first set a very short term cycle to get an idea of their spending propensity and accordingly adjust the time period and funds required.

<hr>

This leads us to the final branch of the tree that holds the various different business specific payment logic.

These are all scripts primarily maintained by the team as a whole based on their own internally conducted consensus over a chosen private social media channel. 

We have simplified it into three main types. 

This is where the framework extends. Add your own folders here. Replace the existing ones. This section is meant to be the most customizable.

All the following scripts must be backed up to allow the board to release after a medium term timelock in case the team misplaces keys.

### live

> A script for the company node server as a single sig with the admin as backup.

Funded every short term period.

This is the company hot wallet used to make bitcoin payments to third party service providers.

This could include:
- domain registrars
- cloud server providers
- as part of your application logic (user rewards for example)

### renumeration

> A script between the team members with a timelocked release.

Funded every short term period.

The idea here is that a script is funded up front BUT team members can only unlock funds in this wallet after a certain date.

A new script is created for every renumeration cycle.

The team must get together and arrive at consensus to enforce the renumeration scheme, resulting in a moment of strengthening trust.

The renumeration scheme is initially set with the team member and the board during onboarding. 

A team member is not obliged to agree to changes to the renumeration scheme proposed by other members during a specific cycle. 

However, if mutual consensus leads to a change for a given cycle, this is accepted by the board.

This gives the team a chance to be fair with each other and quickly pick out the weeds.

A team member can chose to sit out on consensus and just receive renumeration without the ceremonies.

If such a member is a cause for concern, the team can addressed it with the board at the successive renumeration cycle.
 
### resources

> A script between delegated core team members without a timelocked release.

Funded every medium term period.

These are funds that the team would need to aquire shared resources or as an emergency fund.

It is managed by a delegated core team selected by the board, in consensus with the rest of the team.

It is funded to exactly support a set `n` early renumerations for all team members for n short periods.

This gives everyone a chance to take an early renumeration `n` times over a medium period.

Those that take an advance are not included in the next renumeration cycle, and their renumeration is divided among other team members. 

The remainder of the funds at the end of the medium term cycle is distributed equally to all team members.


<b>Each sub-folder contains a more detailed explaination of their functions @ README.md.</b>
