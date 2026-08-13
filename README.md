# 🐝 WareHive

**Warehouse Storage Booking & Inventory Management System**

> A database project for companies who need somewhere to stash their stuff, and a system smart enough to keep track of it all — no honeycomb required (but we kept the name anyway).

---

## What is this?

WareHive is a relational database project that lets companies **book storage space** in a warehouse the way you'd book a hotel room, then log **stock coming in and going out** of that space — with the database keeping a live count of what's where, automatically.

Think of it like this: the warehouse is the hive, each storage unit is a little cell in the honeycomb, and every company renting space is a colony doing its own thing — moving stock in, moving stock out, keeping busy. The database's job is to make sure nobody's colony ever overflows its cell.

No actual bees were involved in the making of this project. Just a lot of `JOIN`s.

---

## Why "WareHive"?

Because a warehouse full of companies, storage units, and constant stock movement is basically organized chaos — much like a beehive. Everyone's busy, everything has its place, and if one worker bee (`USER`) forgets to log a transaction, the whole hive notices.

We promise this is the last pun for at least a few paragraphs. Maybe.

---

## Core Idea

- A **warehouse** is divided into **storage units** — the honeycomb cells of this operation.
- **Companies** register and can **book** one or more units for a period of time.
- Once booked, a company can log **stock-in** and **stock-out** transactions against their unit.
- The database automatically keeps the **current inventory** and **remaining capacity** up to date — no manual recounting, no guesswork.
- **Users** (admins, warehouse staff, or company employees) log in with role-based access, because not every bee should have queen-level permissions.

---

## Tech Stack

| Layer | Choice |
|---|---|
| Database | SQL Server (SSMS) |
| Backend | Python (Flask) |
| Templates | Jinja2 |
| Styling | Plain CSS — no frameworks, no build step |
| Connector | pyodbc |

Kept deliberately simple, because the point of this project is the database logic, not a shiny frontend. The CSS is there to make it *look* nice — not to steal the spotlight from the SQL.

---

## Entities (the Hive's Residents)

- `COMPANY` — the colony renting space
- `USER` — the worker bees logging in
- `WAREHOUSE` — the hive itself
- `STORAGE_UNIT` — individual honeycomb cells
- `BOOKING` — who's occupying which cell, and for how long
- `PRODUCT` — what's actually being stored
- `STOCK_TRANSACTION` — every bit of stock buzzing in or out
- `PAYMENT` — because bees don't work for free

Full schema, ER diagram, and phase-by-phase build plan are in the project proposal doc.

---

## Features

- 🏗️ Book a storage unit for a date range, like reserving a table — except the table holds pallets
- 📦 Log incoming and outgoing stock, with automatic inventory updates via triggers
- 🚫 Built-in checks so nobody overbooks a unit or overstuffs it past capacity
- 📊 Reports on occupancy, current stock levels, and revenue
- 🔐 Role-based access — admins, warehouse staff, and company users each see only what they need to

---

## Status

🐝 Buzzing along — core schema and ER diagram done, Flask interface in progress.

---

## A Closing Thought

Every good hive needs structure, and every good database needs normalization. WareHive tries to be both — organized, a little bit busy, and hopefully never chaotic enough to sting anyone with a bad `NULL` value.

That's the last one. Unbeelievable restraint, honestly.
