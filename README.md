# Opaque documentation

Documentation for [Opaque Protocol](https://opaque.cash), built with [Mintlify](https://mintlify.com).

**Live site:** Connect this repo (`opaquecash/mintlify-docs`) in the Mintlify dashboard and set custom domain `docs.opaque.cash`.

## Local preview

Requires Node.js 20.17+.

```bash
npm i -g mint
cd docs && mint dev
```

Open [http://localhost:3000](http://localhost:3000).

## Structure

| Path | Content |
| --- | --- |
| `docs.json` | Navigation, branding, navbar |
| `index.mdx` | Welcome |
| `quickstart.mdx` | 5-minute integration (`fromWallet` flow) |
| `concepts/` | CSAP, PSR, UAB |
| `guides/` | End-to-end flows (register, send, scan, schemas, attestations, proofs) |
| `sdk/` | Hand-written `OpaqueClient` + `@opaquecash/react` reference |
| `sdk/api/` | Generated TypeDoc API reference (do not edit by hand) |
| `protocol/` | Spec links and the `@opaquecash/deployments` address registry |

## Generated API reference

`sdk/api/` is emitted by TypeDoc from the SDK source. Regenerate after SDK releases:

```bash
cd sdk && npm run build && npm run docs:api
```

It is not wired into the Mintlify navigation; it serves as a browsable raw reference
on GitHub and a source for the hand-written pages.

## Style

- No em dashes; use commas, colons, parentheses, or separate sentences.
- Code samples must compile against the current `@opaquecash/opaque` API; when a client
  method changes, update the matching page in `sdk/` and any guide that calls it.
- Addresses in `protocol/deployments.mdx` must match `@opaquecash/deployments`
  (regenerated via `npm run generate` in the chain repos).

## Publishing

Push to `main` on `opaquecash/mintlify-docs`. Mintlify auto-deploys when the GitHub app is connected.

## SDK source

API docs reflect `@opaquecash/opaque` in [`opaquecash/sdk`](https://github.com/opaquecash/sdk). Update docs when client methods change.
