# Feather 🪶

Feather is a prototype smart matatu fare and prepaid payments platform for Kenya.

## Product principle

> **The vehicle manages the trip. The passenger manages their journey.**

A conductor starts one live vehicle trip. Passengers join that trip, select a destination, receive a calculated fare, and pay before boarding. The conductor only needs to verify that payment is confirmed.

## Current MVP

- Passenger-first responsive web prototype
- SACCO and vehicle selection
- Route and destination selection
- Fare engine with route fare, operating-cost/fuel factor, and peak-time adjustment
- Prepaid payment flow
- Feather Wallet balance and demo top-up
- Payment receipt / boarding confirmation
- Conductor mode
- Live passenger payment dashboard
- Trip-level paid/pending/occupancy/collection metrics
- Destination-change architecture ready for future fare-difference payments

## Architecture direction

```text
Passenger
  -> Vehicle QR / active trip
  -> GPS-assisted boarding point
  -> Destination
  -> Fare Engine
  -> Prepaid Payment
  -> Boarding Confirmation

Vehicle Trip
  -> Route
  -> SACCO
  -> Vehicle
  -> Live passenger journeys
  -> Settlement / analytics
```

## Planned integrations

- M-Pesa / Safaricom Daraja
- Bank payment rails
- SACCO management and settlement
- GPS / mapping provider
- SMS / USSD for feature-phone passengers
- Authentication and identity
- Production wallet ledger

## Important product rules

1. Payment is collected before or at boarding.
2. A vehicle has one active trip session; passengers do not require conductor-created trips.
3. Destination changes require payment of any fare difference before continuing.
4. Overpayment/refund value can return to the Feather Wallet rather than requiring cash handling.
5. Cash passengers remain supported; digital payments should not be mandatory for the MVP rollout.
6. Production fare rules must be configurable by authorized SACCO/operator administrators and comply with applicable Kenyan transport requirements.

## Run locally

This first version is a static prototype. Open `index.html` in a browser, or serve the folder with any static HTTP server.
