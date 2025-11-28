# Inventry ERP Documentation

Documentation hub for Inventry ERP covering business modules, processes, and configuration guidance.

## Overview
- Scope: Sales, Purchase, Inventory, Manufacturing, Quality, Packaging, Dispatch/Logistics, Finance, Masters, and Administration.
- Purpose: Centralize functional specs and serve as a quick reference for users, implementers, and developers.
- Status: Living document—see `Modules.md` for the latest module breakdown.

## Quick Links
- Module reference: [Modules.md](Modules.md)
- Updates/changelog: add a `CHANGELOG.md` entry per change.
- Issues/clarifications: track questions and decisions in your issue tracker.

## Module Snapshot
- Sales: inquiry-to-order flow, approvals, returns, and reporting.
- Inventory: real-time stock checks, GRN, adjustments, alerts, and valuation.
- Purchase: requisitions to PO/GRN/invoice, returns, and vendor analytics.
- Production: WO, BOM, routing, material issue, WIP, scrap/rework, completion.
- Quality: IQC/IPQC/FQC, rejection handling, and QC reporting.
- Packaging & Dispatch: packing, batch/lot, packing lists, dispatch/DC, transport.
- Finance: invoicing, unified party ledger, netting, payments, notes, GST.
- Master Data: unified Party Master, items, warehouses, UOM, tax, BOM, price lists.
- Administration: users, roles/permissions, workflows, activity logs, notifications.

## How to Use This Repo
- Browse: Start with `Modules.md` for a functional overview.
- Extend: Add new docs per module as `docs/<module>/<topic>.md`.
- Contribute: Propose changes via PRs; keep tables consistent and concise.
- Versioning: Note any process/policy changes with an effective date.

## Conventions
- Format: Markdown tables for workflows and responsibilities.
- Terminology: Use ERP-standard terms (SO, PO, GRN, WO, BOM, QC).
- Data sensitivity: Do not include live credentials or real customer data.

## Roadmap Ideas
- Add workflow diagrams per module.
- Include sample forms/templates (SO, PO, QC, DC, invoices).
- Add KPI/report definitions for each function.
