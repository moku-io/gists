# OAuth2

Let's say a user holds an identity with a cartain Identity Provider (Google, Facebook, ecc) and wants to authorize our App to use that identity. The App is split between a Client (a Frontend, a mobile app, or even a bunch of loose pages exposed by the Backend directly) and a Server.

We will use `s` and `ip` as placeholders for the URL of, respectively, the Server and the Identity Provider.

- The Server needs to expose some way (e.g. and endpoint `s/auth`, or a GraphQL query) to get the OAuth2 URL. Most Identity Providers provide libraries to compose this URL automatically.
- The Server needs to expose some callback endpoint (e.g. `s/tokens`) through which to receive the tokens from the Identity Provider.

[![](https://mermaid.ink/img/pako:eNqNU01rGzEQ_SuDzv449CZaB-OGYGiLYXMIZaEo0qwtsqvZ6iNpCPnvHUn22kko9CTpzXuaeaPRi9BkUEgxn89bp8l1di9bBxDwd0KnsRwABus9-bWO5IOETvUBW1c0J-JXq_ZeDZl-T39gPY5VOSofrbajchE2oAJseosufgw2Odigf0Sfg-hMXi4Z212mbA3LbXz-fO-Xq52nR2uqYgPz1QoaCTfXtxCWKsVDhpsCbyTYcUkZvPJorEcdfyVvv7QiLCM9oAutON-y3dVr_k9DY4Q1s3JhWkVLrtr7QRHB2_0hAnXlzm0HDtGgmQHTJy9w8gFPtu-Ls5qusFLgQKSyV2_SFGbX09PiomXcpqPjT3d38I0qVcKp5qv85OxhsVhcWp4a9w9Wc24MOvQqYsle2WX7XqH64zMfK-IMt7VrBZ0epklaYygolsF6q7nOo_dOMmHsWczEgH5Q1vAcv2SwFdykAVsheWuwU4kr4ZJemcoNpObZaSGjTzgTntL-IGQZ6ZlIo2Fjx1meUJ6-n0TnM88Cf4Tv9efUTyNe_wLCkRLM?type=png)](https://mermaid.live/edit#pako:eNqNU01rGzEQ_SuDzv449CZaB-OGYGiLYXMIZaEo0qwtsqvZ6iNpCPnvHUn22kko9CTpzXuaeaPRi9BkUEgxn89bp8l1di9bBxDwd0KnsRwABus9-bWO5IOETvUBW1c0J-JXq_ZeDZl-T39gPY5VOSofrbajchE2oAJseosufgw2Odigf0Sfg-hMXi4Z212mbA3LbXz-fO-Xq52nR2uqYgPz1QoaCTfXtxCWKsVDhpsCbyTYcUkZvPJorEcdfyVvv7QiLCM9oAutON-y3dVr_k9DY4Q1s3JhWkVLrtr7QRHB2_0hAnXlzm0HDtGgmQHTJy9w8gFPtu-Ls5qusFLgQKSyV2_SFGbX09PiomXcpqPjT3d38I0qVcKp5qv85OxhsVhcWp4a9w9Wc24MOvQqYsle2WX7XqH64zMfK-IMt7VrBZ0epklaYygolsF6q7nOo_dOMmHsWczEgH5Q1vAcv2SwFdykAVsheWuwU4kr4ZJemcoNpObZaSGjTzgTntL-IGQZ6ZlIo2Fjx1meUJ6-n0TnM88Cf4Tv9efUTyNe_wLCkRLM)

The Success/Error can be as simple as a static page hosted by the Server. For a better user experience you can *cleverly* use redirects and some state saved locally on the Client to make the flow end up directly on the page the user meant to reach.
