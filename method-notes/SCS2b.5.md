1. Audited all active AWS resources in eu-north-1 using cloud-sweep and the EC2 Console before running any teardown.
2. Recorded running instance i-04cfedd988b5e8916, its 8 GiB EBS root volume, and public IPv4 13.61.35.219 in cloud/bill-reading.md with dates.
3. Cross-checked accrued costs using both the AWS Billing console and rent-card.md hourly rates converted to KES.
4. Configured the fisher-monthly AWS Cost Budget with 80% actual and 100% forecasted email alerts (or verified --budget-demo) to prevent surprise spend.
5. Recorded the fault guess in ~/scs-faults using break.sh --guess before running teardown and verified clean state afterward.
6. Overtime — what on the bill I could not match to my list, and when I will look again: Same-day hourly usage lines do not appear immediately on the AWS Cost Explorer / Bills breakdown due to billing ingestion delay, so I will check Cost Explorer tomorrow morning (next working day, 2026-11-23) to verify every address and disk charge line settled at zero after teardown.
