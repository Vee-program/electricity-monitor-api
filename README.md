
# Electricity Monitor API

A backend service that helps households track and forecast prepaid electricity usage, so you know how much each appliance is costing you, how long your current balance will last, and roughly when you'll need to top up next.

## The Problem

Most prepaid electricity users have no visibility into where their units are actually going. Electricity tends to run out before the month ends, especially in winter, when heating and geysers spike usage and by the time the balance hits zero, it's too late to budget around it.

This project aims to give users:
- A clear picture of how much electricity each of their appliances consumes
- An estimate of how long their current balance will last, based on real usage
- A projected date for their next top-up
- A way to track spending against a monthly budget

## Status

In active development-Phase 1 (MVP) in progress.

## Phase 1 Scope (MVP)

- Single-household support
- Appliance catalog with pre-filled wattage (so users don't need to know watts off the bag of their devices)
- Three appliance usage profiles, to keep daily logging effortless:
  - **Always-On** (fridges, freezers) — no daily input needed
  - **Scheduled-Duration** (geysers, heaters), set hours/day once, override only when it changes
  - **Session-Based** (kettles, toasters) ,quick tally instead of manual time entry
- Flat-rate tariff calculations
- Top-up tracking (Rand → kWh)
- Monthly budget tracking and pacing
- Dashboard: daily burn rate, days remaining, projected next top-up date, budget pace

### Planned for later phases

- Multi-user households (shared appliance tallying across members)
- Tiered/inclining block tariffs
- Notifications and budget alerts
- Seasonal usage profiles
- Actual-vs-estimated usage learning over time

## Tech Stack

- **ASP.NET Core (C#)** - Web API
- **Entity Framework Core** - data access
- Clean Architecture layering:
  - `Domain` - entities, no external dependencies
  - `Application` - business logic, calculation services, interfaces
  - `Infrastructure` - EF Core, persistence
  - `Api` - controllers, authentication, DI wiring



## Project Structure

src/
 ├─ ElectricityMonitor.Domain
 ├─ ElectricityMonitor.Application
 ├─ ElectricityMonitor.Infrastructure
 └─ ElectricityMonitor.Api
