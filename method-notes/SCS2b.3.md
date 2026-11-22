1. Goal: Provision a micro Ubuntu 24.04 LTS EC2 instance tagged Owner=fisher with restricted SSH and public HTTP/HTTPS.
2. Identity: Generated an ed25519 SSH key pair locally in Ubuntu so the private key never leaves ~/.ssh.
3. Network wall: Configured security group inbound rules for TCP 22 (campus CIDR only), TCP 80 (0.0.0.0/0), and TCP 443 (0.0.0.0/0).
4. Service check: Verified SSH connectivity via key authentication and confirmed nginx serves the custom site on port 80.
5. Lifecycle: Verified instance stop/start behavior (new public IP on start, stopped rather than terminated at end of day).
6. What I might be wrong about: Assuming the campus public IP stays static across sessions; I would find out by checking checkip.amazonaws.com and testing port 22 reachability if SSH times out.
