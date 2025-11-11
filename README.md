# Homepage-Dashboard

A static homepage dashboard for organizing and accessing self-hosted services using [Homer](https://github.com/bastienwirtz/homer).

## What This Repo Achieves

This repository provides a simple, customizable dashboard to centralize access to your home server services. It uses Homer, a lightweight static homepage generator that displays services as tiles with icons and links, configured via YAML files. The goal is to create an easy-to-navigate hub for managing applications like Docker containers, monitoring tools (Grafana, Prometheus), media servers (Jellyfin, Plex), and more, all from a single web page.

## Features

- **Static and Lightweight**: No backend required; serves as a simple HTML page.
- **Customizable Icons**: Extensive icon set for popular services in the `assets/icons/` directory.
- **YAML Configuration**: Easy to add, remove, or modify services via `config.yml`.
- **Custom Styling**: Override styles with `assets/custom.css`.
- **Deployment Ready**: Includes Kubernetes deployment manifest (`hommer-deployment.yml`) for easy hosting.

## Setup and Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/Homepage-Dashboard.git
   cd Homepage-Dashboard
   ```

2. **Configure Services**:
   - Edit `config.yml` to add your services. Example:
     ```yaml
     title: "My Dashboard"
     subtitle: "My Home Services"
     services:
       - name: "Docker"
         icon: "docker.png"
         url: "http://localhost:2375"
       - name: "Grafana"
         icon: "grafana.png"
         url: "http://grafana.local"
     ```
   - Add custom icons to `assets/icons/` if needed.

3. **Customize Styling** (Optional):
   - Modify `assets/custom.css` for theme adjustments.

4. **Serve the Dashboard**:
   - Use any static web server (e.g., Nginx, Apache) to serve the files.
   - For local testing: `python -m http.server 8000` then visit `http://localhost:8000`.

## Deployment

- **Kubernetes**: Use `hommer-deployment.yml` to deploy to a Kubernetes cluster.
  ```bash
  kubectl apply -f hommer-deployment.yml
  ```

- **Docker**: Build and run as a container if desired (not included; see Homer docs for Docker setup).

## Contributing

Feel free to add more icons or improve configurations. Submit pull requests or issues for enhancements.

## License

This project is licensed under the MIT License. See Homer's repository for its licensing details.