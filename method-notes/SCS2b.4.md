1. Measured live CPU, memory, and architecture on i-04cfedd988b5e8916 (13.61.35.219) using size-scs2b.4 and SSH (uname -m, free -m, uptime) on 2026-11-22.
2. Verified that t3.micro runs x86_64 and idles at 1.5% CPU and 339 MiB RAM used, making steady m5.large or GPU instances unnecessary.
3. Looked up eu-north-1 pricing directly on the AWS EC2, S3, and Lightsail pricing pages on 2026-11-22 rather than relying on memory.
4. Converted all USD monthly totals into Kenyan Shillings (KES) using the 2026-11-22 Central Bank of Kenya exchange rate so the client budget is clear.
5. Compared EC2 unbundled hourly costs (compute + EBS + hourly public IPv4) against Lightsail fixed $7.00/month bundle and S3 serverless hosting.
6. What I might be wrong about, and how I would find out: My assumed 150 daily visitors and static-only workload could underestimate traffic spikes or future form/database needs, which I would find out by checking /var/log/nginx/access.log and CloudWatch CPU/credit metrics after one week of real traffic.
