# CSFloat Marketplace Automation

A trading automation project I built with a finance student. We started in August 2025 and use it to evaluate CSFloat listings, automate purchasing, and track inventory and results. A third person now uses the bot as well.

The source code is private. This repository explains the project and my work on it without publishing the trading strategy.

## What I worked on

I'm Oliver Zhang, a Computer Science and Engineering student at Ohio State, graduating in 2029.

We worked together across the project. My work included JavaScript and Node.js components for retrieving market data, turning our trading criteria into code, and connecting the automation to a browser dashboard. I also worked on API request tracking, configurable settings, and Google Sheets integration.

The interesting part was getting the market rules to work consistently in software: handling incomplete data, controlling request frequency, and checking how the application behaved as market conditions changed. We refined the project using live results and the edge cases we encountered.

## Usage and results

As of September 2026, the project has **12+ months of live operation** and now has **three users**, including the two developers. Combined account activity is approximately **$192K in purchases** and **$200K in sales**.

| Users | Purchases | Sales | Profit |
| --- | ---: | ---: | --- |
| Two developers, combined | $119,816.02 | $123,740.77 | $4,693.44 reported trading profit |
| Third user | About $72,000 | About $76,000 | About $3,000 reported profit after taxes and fees |

The developer figures come from our tracking sheets; the third user's figures are self-reported estimates. The profit figures use different fee and tax treatments, so they are shown separately. Purchase and sales totals are account activity, not money deposited or guaranteed returns.

## Built with

- **JavaScript / Node.js:** market-data processing and automation.
- **Axios / REST APIs:** communication with CSFloat.
- **Express / HTML / CSS:** dashboard and application controls.
- **Google Sheets API:** purchase, sale, and performance tracking.

[Architecture overview](ARCHITECTURE.md)

There is no source code or runnable demo in this repository. Credentials, account details, exact decision rules, and individual transactions stay private.
