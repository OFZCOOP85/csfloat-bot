# Architecture notes

[Back to the project overview](README.md)

This is a high-level description of the private application. It omits source code, endpoint details, strategy thresholds, configuration values, and account identifiers.

## Component responsibilities

### Listing scanner

A Node.js process periodically retrieves marketplace data and maintains runtime activity information. Listing evaluation and trade-history synchronization connect the external marketplace to the local application.

### Selection and pricing

A rule-based evaluation stage considers market activity and historical prices, then determines whether a listing qualifies for an offer. Pricing logic relates the proposed offer to market demand and configured limits. This component is central to Oliver's personal contribution. Detailed rules and formulas are private.

### Offer handling

The application submits qualifying offers, processes seller counteroffers, and can cancel offers. Outbound actions depend on marketplace responses, so local records and external state need reconciliation.

### Trade synchronization and storage

Offer and trade synchronization updates a local JSON ledger. Matching logic associates purchases and sales with recorded items and transactions. The ledger supports downstream summaries; it is not a transactional database.

### Dashboard

An Express server exposes application data and controls to a browser interface. The dashboard presents runtime activity, inventory, and calculated trade summaries. It is intended for the owner's local workflow, not as a publicly hosted service.

### Google Sheets integration

Spreadsheet integration supports purchase and sale tracking. The public showcase contains neither the connected spreadsheet identifier nor its authentication material.

## Engineering considerations

**External API state:** An offer response, a purchase record, and a settled resale are different events. Their states should remain distinct when reporting results.

**Persistence:** Local JSON storage is straightforward for a personal project. More robust recovery and atomic persistence would reduce the risk of losing records after a failed write or malformed file.

**Side effects:** All external write operations need consistent controls. Existing simulation behavior should not be interpreted as a guarantee that every operation is isolated from live accounts.

**Testing:** Automated tests should cover pricing boundaries, state transitions, malformed saved data, and external failures using synthetic fixtures and mocked API clients. A comprehensive automated test suite is not claimed for the current implementation.

**Scope:** These are current design observations and improvement areas. They are not claims that the proposed improvements have already been implemented or measured.

## Why the source is private

The implementation includes a private trading strategy and account integrations. This repository shares the engineering context and contribution narrative for portfolio review while leaving the executable application and operational details undistributed.
