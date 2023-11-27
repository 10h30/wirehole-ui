# All-in-One Network Solution

## Overview
This GitHub repository provides a comprehensive, all-in-one network solution using Docker Compose. It integrates **Unbound**, **Pi-hole**, and **wg-easy** to offer a robust combination of DNS resolution, ad-blocking, and VPN capabilities. This setup is ideal for creating a private, secure, and efficient networking environment.

### Components
- **Unbound**: A validating, recursive, and caching DNS resolver.
- **Pi-hole**: Network-wide ad blocking and DNS server.
- **wg-easy**: Simple WireGuard VPN server setup.

## Getting Started

### Prerequisites
- Docker and Docker Compose installed on your system.
- Basic knowledge of Docker and networking concepts.

### Installation Steps
1. **Clone the Repository**: Clone this repo to your local machine.
2. **Configure Environment Variables**:
   - Set the `WEBPASSWORD` for Pi-hole in the `environment` section.
   - Change `WG_HOST` to your host's public address or URL in `wg-easy` service.
   - Set `PASSWORD` for wg-easy access.

3. **Adjust Network Settings**:
   - Ensure the subnet configuration in `networks -> private_network` matches your network setup.
   - Modify the IP addresses for each service under `networks -> private_network -> ipv4_address` as needed.

4. **Persistent Data**:
   - Create directories `./etc-pihole/` and `./etc-dnsmasq.d/` for Pi-hole persistence.
   - For WireGuard (`wg-easy`), create a directory at the root level for configuration persistence.

5. **Launch Services**:
   - Run `docker-compose up -d` to start all services in detached mode.
   - Services will be created and started based on the configuration in the `docker-compose.yml` file.

### Usage
- **Pi-hole**: Access the Pi-hole admin interface via `http://<pihole-ip>/admin`.
- **wg-easy**: Access the WireGuard interface on `http://<wg-easy-ip>:51821`.

### Network Configuration
- The `docker-compose.yml` file specifies a private network with a custom subnet (`10.2.0.0/24`).
- Each service is assigned a specific IP within this subnet for easy management and communication.

## Security Notice
- Make sure to change default passwords and settings for production environments.
- Regularly update your Docker images for security patches.

## Support
For any issues or help regarding the setup, please open an issue in this GitHub repository.

---
*Note: This README assumes a certain level of expertise with Docker and network management. If you're unfamiliar with these concepts, please refer to the official Docker and respective service documentation for more information.*

