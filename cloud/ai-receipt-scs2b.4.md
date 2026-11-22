# AI Receipt — SCS2b.4 Sizing & Pricing Check (2026-11-22)

- **Spec:** Host a small Kenyan retail business static brochure website (~150 daily visitors, HTML/CSS/images, no backend database) under a 1,500 KES/month budget in eu-north-1.
- **Ask:** Asked AI to structure rent-card.md from live size-scs2b.4 and SSH measurements (t3.micro, 339 MiB RAM used, 1.5% CPU avg) and compare S3, EC2 t3.micro/t4g.micro, and Lightsail micro_3_0.
- **Three options compared:**
  1. **S3 Static Website Hosting (No Server):** ~$0.023/GB-month + request fees; zero server maintenance, lowest cost.
  2. **Amazon Lightsail micro_3_0:** $7.00/month (~903 KES/mo) flat rate including 1.0 GiB RAM, 40 GB SSD, 2 TB transfer, and static IPv4.
  3. **EC2 t3.micro On-Demand (eu-north-1):** $0.0108/hr (~$7.88/mo) + $0.005/hr public IPv4 (~$3.65/mo) + EBS storage (~$0.80/mo) = ~$12.33/mo (~1,591 KES/mo).
- **Verification against provider pages (2026-11-22):** Verified eu-north-1 On-Demand rates on https://aws.amazon.com/ec2/pricing/on-demand/, Lightsail bundle rates on https://aws.amazon.com/lightsail/pricing/, S3 storage rates on https://aws.amazon.com/s3/pricing/, and USD/KES rate on https://www.centralbank.go.ke/.
- **Decision:** Recommended S3 (no server) for pure static delivery, and Lightsail micro_3_0 over EC2 when full Linux/Nginx control is needed so the client stays safely under 1,500 KES/month.
