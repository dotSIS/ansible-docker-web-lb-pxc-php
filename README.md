<div class="info">
    <p align='center'>
        <img src="https://raw.githubusercontent.com/dotSIS/ansible-docker-web-lb-pxc-php/main/media/terra_network.jpg">
    </p>
</div>

# My ansibled docker network.

## Network specs:
- Load balancer:    Nginx
- Server:           2 Nginx reverse proxy servers + 2 Nginx custom PHP-FPM servers
- Database:         3 PXC custom images

## Requirements:
Click the links for the instructions on how to install each of the tools on your machine.
- Virtualization:   [`Docker`](https://docs.docker.com/get-docker/)
- CMT:              [`Ansible`](https://docs.ansible.com/ansible/latest/installation_guide/index.html)

## Clone
- `git clone https://github.com/dotSIS/ansible-docker-web-lb-pxc-php.git`
## Installation & Deployment
  ### Part 1 - Deploy load balancer, reverse proxy, php servers, & database bootstrap
  - `ansible-playbook -i hosts main-u.yml -K`
  ### Part 2 - Deploy joiner databases
  - Uncomment last resource on `main-u.yml`
  - `ansible-playbook -i hosts main-u.yml -K`
  ### Part 3 - Web
  - Visit `http://localhost:8080` on your browser.
  ### Part 4 - Undeploy
  - `ansible-playbook -i hosts main-d.yml -K`
