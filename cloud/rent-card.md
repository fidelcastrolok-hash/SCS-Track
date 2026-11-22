## The need
- Static marketing and information website (HTML, CSS, and small images—no database or backend app server) for a small local retail and service business in Kenya.
- Traffic: ~150 visitors per day (assumed for a neighborhood storefront site, peaking during daytime hours and near zero overnight).
- Budget: under 1,500 KES per month (~11.60 USD/month) for hosting, domain, and public IPv4 address.

## Measured
- Measured on 2026-11-22 at 12:36 EAT (09:36:57 UTC) on i-04cfedd988b5e8916 (fisher-first-instance, t3.micro, public IP 13.61.35.219).
- Processor architecture (uname -m): x86_64 (2 vCPUs).
- Memory (free -m): 909 MiB total, 339 MiB used, 172 MiB free, 514 MiB buff/cache, 569 MiB available (0 Swap).
- Load average (uptime): 0.00, 0.00, 0.00 (up 19 min).
- CloudWatch CPU (size-scs2b.4 on 2026-11-22): 1.5% average across 1 hour(s); busiest hour began 12:00 at 1.5% average (15.7% max, 0 credits left at launch); t3.micro baseline is 20% CPU (10% per vCPU) per AWS Burstable Performance Instances docs, read 2026-11-22.

## What to rent for what
| Workload | Instance / Service | vCPU / RAM / Arch | Notes |
|---|---|---|---|
| Static site (no server needed) | S3 static website hosting (no server) | Serverless object storage | Cheapest for pure static HTML/CSS/images; no OS patching or SSH needed |
| Small dynamic or Nginx web server | t3.micro or t4g.micro | 2 vCPU, 1.0 GiB RAM (x86_64 / arm64, burstable) | Fits low-traffic Nginx/PHP/Node sites that sit idle most of the day |
| Never for a small client | m5.large or g4dn.xlarge (m-class, GPU) | 2–4 vCPU, 8–16 GiB RAM, steady / GPU | Fixed non-burstable cost or GPU hardware wasted on a small website |
| Predictable all-in-one VPS | Lightsail micro_3_0 (or nano_3_0) | 2 vCPU, 1.0 GiB RAM, 40 GB SSD, 2 TB transfer | Bundles compute, SSD, static IPv4, and transfer in one fixed monthly bill |
| Learning and staging | scs-server (t3.micro in sandbox) | 2 vCPU, 1.0 GiB RAM (x86_64, burstable) | Used to practice SSH, Nginx, security groups, and Linux administration before production |

## My choice
S3 (no server) for pure static production hosting—or t3.micro / Lightsail micro_3_0 if server-side code or SSH control is required.

## Why not bigger, why not smaller
Why not bigger: A t3.small (2.0 GiB RAM) or m5.large (8.0 GiB RAM) doubles or multiplies the monthly bill while our live server uses only 339 MiB RAM and 1.5% average CPU.
Why not smaller: A t3.nano (512 MiB RAM) leaves very little headroom once Ubuntu 24.04 OS services and Nginx run together (339 MiB already used), risking out-of-memory kills during package updates or traffic spikes.

## Prices
- Rate: 1 USD = 129.00 KES, from Central Bank of Kenya (centralbank.go.ke, read 2026-11-22)
- S3 Standard storage (eu-north-1): $0.023/GB-month (~3 KES/GB-month) (aws.amazon.com/s3/pricing, read 2026-11-22)
- EC2 t3.nano On-Demand (eu-north-1): $0.0054/hr (~508 KES/mo) + public IPv4 $0.005/hr (~471 KES/mo) (aws.amazon.com/ec2/pricing/on-demand, read 2026-11-22)
- EC2 t3.micro On-Demand (eu-north-1): $0.0108/hr (~1,017 KES/mo) + public IPv4 $0.005/hr (~471 KES/mo) (aws.amazon.com/ec2/pricing/on-demand, read 2026-11-22)
- EC2 t4g.micro On-Demand (eu-north-1): $0.0086/hr (~810 KES/mo) + public IPv4 $0.005/hr (~471 KES/mo) (aws.amazon.com/ec2/pricing/on-demand, read 2026-11-22)
- EC2 m5.large On-Demand (eu-north-1): $0.100/hr (~9,417 KES/mo, ~9.3x t3.micro compute) (aws.amazon.com/ec2/pricing/on-demand, read 2026-11-22)
- Lightsail micro_3_0 (eu-north-1, 1.0 GiB RAM, 40 GB SSD, 2 TB transfer, static IPv4 included): $7.00/mo (~903 KES/mo) (aws.amazon.com/lightsail/pricing, read 2026-11-22)

## Lightsail or EC2 for this client
Choose Lightsail (micro_3_0) over EC2 for this small client because Lightsail bundles compute, 40 GB SSD, 2 TB data transfer, and a static IPv4 address into one predictable fixed monthly bill (aws.amazon.com/lightsail/pricing, read 2026-11-22) without extra hourly IPv4 or EBS charges.
