# Pulse Cover

**Insurance for machines that pays out automatically when the machine goes silent. No claim form, no adjuster.**

Live demo: https://claude.ai/artifact/L2evPvKfrrb3gt5bBR6zbk
Track: peaq Machine Economy (side track for German builders)

## The problem

Robots and other machines break down, and every hour of downtime costs their owner money. But insuring a machine today is slow and expensive. A human has to file a claim, someone has to check it, and the insurer has no way to trust the machine's own data.

## The idea

A machine already sends out a signed "I'm alive" message (a heartbeat). Pulse Cover turns that message into an insurance trigger:

1. The machine earns money and reports each job. This builds its **credit rating**.
2. A better rating means a **cheaper premium**. A shaky machine pays more.
3. The owner buys cover. The premium is held in **escrow** (a locked pot).
4. If the heartbeats stop, the escrow **pays the owner automatically**.

No human decides anything. The machine's own signed data is the proof.

## Try it (30 seconds)

1. Open the demo link above.
2. Press **Run full demo**.
3. Watch: the robot comes alive, earns money, its rating climbs, the premium gets cheaper, cover is bought, then the signal is cut and the payout fires.

You can also press the buttons one by one: Start machine, Buy cover, Cut the signal.

## Why this is the Machine Economy

Insurance is a missing piece. Machines can already earn and pay, but they cannot be insured, and uninsured machines are hard to finance. This project shows that a machine's own verifiable activity can price and trigger insurance, so machines become insurable and investable without paperwork.

This is the "Parametric insurance" idea from the track brief: a downtime policy triggered by the machine's signed telemetry, with the premium priced from its credit rating.

## How peaq fits

| Piece of the demo | What it does in the demo today | peaq feature it maps to |
|---|---|---|
| Machine identity | Simulated ID | peaq machine ID and peaqID (DID) |
| Heartbeat | Simulated signed message every second | peaq presence heartbeat (signed "I'm here" messages; offline when they stop) |
| Earnings reports | Simulated delivery jobs | peaq revenue and activity events |
| Credit rating | Simulated score, rises with earnings, falls when silent | Machine Credit Rating (MCR) |
| Premium | Calculated from the rating: better rating, lower price | Reads the MCR |
| Escrow and payout | Simulated pot, pays out after silence | Onchain escrow (next step) |

## What is real and what is simulated

Being direct about this:

- **Real:** the logic and the user experience. The premium formula, the heartbeat watchdog, the automatic payout, and the credit-rating behavior all work end to end in the demo.
- **Simulated:** the machine, its ID, its earnings, and the escrow. Nothing in the demo is connected to peaq yet and no real money moves.
- **Time is compressed:** "5 seconds of silence" in the demo stands for a longer real-world window (for example 5 minutes).

## Pricing rule used in the demo

- Coverage: 500 USDT
- Premium rate: 6% minus 0.047% per rating point (score 35 pays about 4.4%, score 90 pays about 1.8%)
- Payout trigger: no heartbeat for 5 seconds (demo time)

## Next steps

1. Replace the simulated ID with a real peaq machine ID.
2. Read the real rating from the peaq MCR API instead of the simulated score.
3. Use peaq's real presence heartbeat as the trigger.
4. Move the escrow into a smart contract on peaq so the payout is truly onchain.

## Built by

[Your name], solo builder.
