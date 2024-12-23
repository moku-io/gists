# OAuth2

Let's say a user holds an identity with a cartain Identity Provider (Google, Facebook, ecc) and wants to authorize our App to use that identity. The App is split between a Client (a Frontend, a mobile app, or even a bunch of loose pages exposed by the Backend directly) and a Server.

We will use `s` and `ip` as placeholders for the URL of, respectively, the Server and the Identity Provider.

- The Server needs to expose some way (e.g. and endpoint `s/auth`, or a GraphQL query) to get the OAuth2 URL. Most Identity Providers provide libraries to compose this URL automatically.
- The Server needs to expose some callback endpoint (e.g. `s/tokens`) through which to receive the tokens from the Identity Provider.

[![](https://mermaid.ink/img/pako:eNqNU11LKzEQ_StDnvvxcN-Ct1J6RQoqhfVBLgsSk9k2uJvZO8nqFfG_m492WxXBpyRnzsnMmUxehSaDQorpdFo7Ta6xW1k7AI__BnQa8wGgs8zESx2IvYRGtR5rlzUH4h-rtqy6RH-g_7Ds-6LsFQerba9cgBUoD6vWogtfg1UKVshPyCmIzqTllLHeJMraRLkNL2cPPF9smJ6sKYoVTBcLqCRcXtyCn6sh7BJcZXglwfZzSuA5o7GMOtwPbH_Xws8DPaLztTjest6Ua36moT7AMrJSYVoFS67Yu6GAwHa7C0BNvnPdgEM0aCYQ6aMXOPiAZ9u22VlJl1mDj4FAea8-pMnMpqXn2UnLYpv2jn_d3cEVFaqEQ83n6cmjh9lsdmp5bNw3rOrYGHTIKmDOXth5-1mh2v0z7yuKGW5L1zI6Pkw1aI0-o5gH66PmIo3eJ8mIRc9iIjrkTlkT5_g1gbWITeqwFjJujeLHVM9b5MXuUfXitJCBB5wIpmG7EzLP80QMvYmu9oM8onH0_hIdz3EQ4i-4Lt-m_Bjx9g53EBGJ?type=png)](https://mermaid.live/edit#pako:eNqNU11LKzEQ_StDnvvxcN-Ct1J6RQoqhfVBLgsSk9k2uJvZO8nqFfG_m492WxXBpyRnzsnMmUxehSaDQorpdFo7Ta6xW1k7AI__BnQa8wGgs8zESx2IvYRGtR5rlzUH4h-rtqy6RH-g_7Ds-6LsFQerba9cgBUoD6vWogtfg1UKVshPyCmIzqTllLHeJMraRLkNL2cPPF9smJ6sKYoVTBcLqCRcXtyCn6sh7BJcZXglwfZzSuA5o7GMOtwPbH_Xws8DPaLztTjest6Ua36moT7AMrJSYVoFS67Yu6GAwHa7C0BNvnPdgEM0aCYQ6aMXOPiAZ9u22VlJl1mDj4FAea8-pMnMpqXn2UnLYpv2jn_d3cEVFaqEQ83n6cmjh9lsdmp5bNw3rOrYGHTIKmDOXth5-1mh2v0z7yuKGW5L1zI6Pkw1aI0-o5gH66PmIo3eJ8mIRc9iIjrkTlkT5_g1gbWITeqwFjJujeLHVM9b5MXuUfXitJCBB5wIpmG7EzLP80QMvYmu9oM8onH0_hIdz3EQ4i-4Lt-m_Bjx9g53EBGJ)

The Success/Error can be as simple as a static page hosted by the Server. For a better user experience you can *cleverly* use redirects and some state saved locally on the Client to make the flow end up directly on the page the user meant to reach.
