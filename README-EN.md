# BTC Self-Custody & Inheritance Scheme

> Top of the single-sig category — uncrackable while alive, recoverable after death.

A **vendor-free, trust-minimized** playbook for long-term Bitcoin custody and
posthumous inheritance. Core idea: replace trust with **physical distribution**,
and single points of failure with **incomplete secrets**.

[中文版](./README.md)

## The design in 30 seconds

Three kinds of artifacts, three storage locations each, mutually isolated:

| Artifact | Contents | Stored at (3 places each) |
|---|---|---|
| Seed material | Seed words stamped on steel plate, laminated SeedQR paper (full seed carriers) | Home safe / bank safe-deposit box / hidden at family home |
| Vault password | Machine-generated 14+ char truly random, laser-printed + laminated | Relative A's home / relative B's home (blind) / lawyer's office |
| Vault file | Encrypted bundle: BIP39 passphrase + location map + recovery tutorial (timestamped) | A copy on each family member's phone / bank·lawyer backup / blind copy at relative's |

**Iron rule: seed material and the vault password never co-locate.**
No single compromised location yields a complete wallet.

**While alive**: watch-only wallet for monitoring; spending via an air-gapped,
QR-only DIY signer (SeedSigner on a Raspberry Pi Zero), plus a memorized BIP39
passphrase.
**After death/incapacitation**: heirs retrieve the password → decrypt the vault →
follow the tutorial to the steel plate → recover in any BIP39 wallet.

Key principle: the vault stores only **incomplete secrets** — a BIP39 passphrase
is useless without the seed words, so it may be recorded; seed words and private
keys never enter any digital record.

## Docs (Chinese)

- `docs/01-生前流程.md` — setup, daily spending, vault distribution, annual drill
- `docs/02-身后流程.md` — heir's step-by-step recovery guide
- `docs/03-威胁模型.md` — threat model and trust assumptions
- `docs/04-执行清单.md` — shopping list, setup checklist, verification steps
- `docs/05-登记App配合.md` — how a local encrypted registry fits in (product-agnostic)
- `docs/08-费用清单.md` — cost breakdown
- `docs/06-FAQ.md`
- `docs/07-multisig升级路径.md` — optional 2-of-3 multisig upgrade path

## Security notes

- Security does **not** rely on obscurity (Kerckhoffs's principle): publishing
  this methodology does not weaken it.
- Issues / PRs reporting vulnerabilities are welcome — community review is a
  free security audit.
- This repo contains and will never contain real keys, addresses, or locations.
  All examples are placeholders.

## License

[CC BY-SA 4.0](./LICENSE)
