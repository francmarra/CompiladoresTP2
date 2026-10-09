# Compilers — Lexical Analyzer for Autonomous Robot

A lexical analyzer built with **Lex/Flex** that parses and executes commands
for an autonomous material-handling robot. The robot manages battery, cargo,
maintenance cycles, and deliveries across locations.

## Features

- **Material Collection** (`RECOLHE`) — Parse lists of materials with quantities,
  manage cargo capacity (max 80 units)
- **Delivery System** (`ENTREGA`) — Route-aware deliveries with battery cost
  calculation based on distance and cargo weight
- **Battery Management** (`CARREGA-BATERIA`) — Charging with different priority
  modes (0, 1, 2) and low-battery alerts
- **Maintenance Tracking** (`MANUTENCAO`) — Cycle-based maintenance with
  automatic reset after 3 services
- **State Reporting** (`ESTADO`) — Query battery, materials, and maintenance
  status in any combination

## Tech Stack

- **C** — Core logic and state management
- **Lex/Flex** — Lexical analysis and command pattern matching
- **Regular Expressions** — Token definitions for command validation

## How to Build & Run

```bash
flex trabalho2.l
gcc lex.yy.c -o robot -lfl
./robot < teste.txt
```

## Example Commands

```
RECOLHE([(A4gt6,30), (cbv45,3), (12345,21)])
ENTREGA(LM035,A4gt6,30)
CARREGA-BATERIA(1)
MANUTENCAO(1)
ESTADO(B,M,T)
```

## Context

Academic project for the Compilers course at UTAD (University of Tras-os-Montes
and Alto Douro). Demonstrates lexical analysis, pattern matching with regular
expressions, and state machine implementation in C.
