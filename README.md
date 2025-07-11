# My Personal Docker Playground

This project is a curated collection of self-hosted services that I find interesting and useful. It's managed through a single `docker-compose.yml` file for easy setup, maintenance, and updates.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- [Docker Compose](https://docs.docker.com/compose/install/)

### Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/nicholaslck/my-playground.git
    cd my-playground
    ```

2.  **Create a `.env` file:**

    Before you can launch the services, you need to create a `.env` file in the root of the project. This file will contain the environment variables required by the services in the `docker-compose.yml` file.

    You can start by copying the example file:

    ```bash
    cp .env.example .env
    ```

    Now, edit the `.env` file with your desired settings.

    **Example `.env` file:**
    ```
    GENERIC_TIMEZONE=Pacific/Auckland
    N8N_HOST=n8n.your-domain.com
    ```

## Usage

-   **Start all services:**

    ```bash
    docker-compose up -d
    ```

-   **Stop all services:**

    ```bash
    docker-compose down
    ```

-   **Update all services:**

    ```bash
    docker-compose pull
    docker-compose up -d
    ```

## Services

This project includes the following services:

| Service | Description | Access |
| :--- | :--- | :--- |
| [Wallos](https://github.com/ellite/Wallos) | An open-source personal subscription tracker. | `http://localhost:8282` |
| [Open WebUI](https://github.com/open-webui/open-webui) | A user-friendly web UI for various AI models. | `http://localhost:8801` |
| [n8n](https://n8n.io/) | A powerful workflow automation tool. | `http://localhost:5678` |
| [deepwiki-open](https://github.com/AsyncFuncAI/deepwiki-open) | AI-Powered Wiki Generator for GitHub/Gitlab/Bitbucket Repositories. | `http://localhost:8001` and `http://localhost:8300` |
| [openlist](https://github.com/OpenListTeam/OpenList) | A new AList Fork to Anti Trust Crisis. | `http://localhost:5244` and `http://localhost:5245` |
| adventurelog | A personal adventure logging application. | `http://localhost:8015` |

## Directory Structure

After running `docker-compose up -d` for the first time, a `mnt/` directory will be created in the project root. This directory is used for persistent storage for the services.

```
.
├── mnt/
│   ├── wallos/
│   │   ├── db/
│   │   └── logos/
│   ├── open-webui/
│   │   └── data/
│   └── n8n/
│       ├── data/
│       └── files/
├── docker-compose.yml
└── README.md
```

## Configuration

All service configurations are managed through the `docker-compose.yml` file and the `.env` file. Please refer to the official documentation of each service for more advanced configuration options.

## Contributing

Contributions are welcome! Please feel free to open an issue or submit a pull request.

## License

This project is open-source and available under the [MIT License](LICENSE).
