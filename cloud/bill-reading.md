# Bill Reading — fisher (2026-11-22)

## What is running?
- EC2 instance `i-04cfedd988b5e8916` (`fisher-first-instance`, `t3.micro`, `eu-north-1`, state: `running`, launched `2026-11-22`), verified on EC2 Console Instances page (read 2026-11-22).
- Attached 8 GiB `gp3` EBS volume (`Owner=fisher`, `eu-north-1`) and public IPv4 address `13.61.35.219`, verified on EC2 Volumes and Network Interfaces console pages (read 2026-11-22).
- Security group `sg-0c6d36f70c937767d` and key pair `fisher-key` (`$0.00` idle configuration items), verified on EC2 Console (read 2026-11-22).

## What is it costing?
- AWS Billing & Cost Management Bills console page (https://console.aws.amazon.com/billing/home#/bills, read 2026-11-22): Month-to-date unblended usage in `eu-north-1` for EC2 compute (`t3.micro`), EBS `gp3` storage, and VPC Public IPv4 hours (~$0.06 accrued today).
- AWS Cost Explorer console page (https://console.aws.amazon.com/cost-management/home#/cost-explorer, figures for 2026-11-21): Daily unblended cost for `2026-11-21` shows $0.00 prior to today's instance launch (Cost Explorer data lags live usage by up to 24 hours).
- AWS Free Tier usage & limits page (https://aws.amazon.com/free/, read 2026-11-22): Sandbox account does not apply personal Free Tier credits; `t3.micro` (`$0.0108/hr`) + Public IPv4 (`$0.005/hr`) + 8 GiB `gp3` EBS (`~$0.001/hr`) = `~$0.0168/hr` (`~2.17 KES/hr` at `1 USD = 129.00 KES`, read 2026-11-22) × ~3.6 running hours = `~$0.06` (`~7.8 KES`).

## What did I forget?
- Before signing out, stop/terminate `i-04cfedd988b5e8916` via `teardown-scs2b.5 --do` so compute (`$0.0108/hr`), EBS storage, and public IPv4 (`$0.005/hr`) stop billing, then verify `0` items costing with `cloud-sweep` (verified on EC2 Console, read 2026-11-22).
- Re-check AWS Cost Explorer tomorrow (`2026-11-23`) for `2026-11-22` usage lines to confirm both the public IPv4 address line and EBS disk line settle at `$0.00` after teardown.
