# 0x0F. Load Balancer

## Introduction

This project focuses on setting up a load balancer to improve the web server infrastructure's redundancy and reliability. The tasks involve configuring Nginx on multiple web servers and installing HAProxy as the load balancer to distribute incoming traffic among these servers.

## Tasks

### Task 0: Double the number of webservers

#### Script: [0-custom_http_response_header](./0-custom_http_response_header)

This script installs and configures Nginx on a server with a custom HTTP response header. The custom header `X-Served-By` contains the hostname of the server, allowing tracking of which server is handling requests.

### Task 1: Install your load balancer

#### Script: [1-install_load_balancer](./1-install_load_balancer)

This script installs and configures HAProxy version 1.5 on a server. It enables management via the init script and distributes requests using a round-robin algorithm among the web servers.

## Usage

1. Clone this repository:

    ```bash
    git clone https://github.com/your_username/alx-system_engineering-devops.git
    ```

2. Navigate to the project directory:

    ```bash
    cd alx-system_engineering-devops/0x0F-load_balancer
    ```

3. Execute the desired script(s) with appropriate permissions:

    ```bash
    ./0-custom_http_response_header
    ```

    ```bash
    ./1-install_load_balancer
    ```

## Requirements

- Ubuntu 16.04 LTS
- Bash (version 4.4 or later)
- HAProxy version 1.5

## Resources

- [Introduction to load-balancing and HAproxy](https://www.digitalocean.com/community/tutorials/an-introduction-to-haproxy-and-load-balancing-concepts)
- [HTTP header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
- [Debian/Ubuntu HAProxy packages](https://haproxy.debian.net/)

## Author

Your Name

## Acknowledgments

Special thanks to [ALX - Software Engineering Program](https://www.alxafrica.com/software/) for providing the project guidelines and resources.

