Here’s the updated README with the new project name and description:

---

## 🎮 Demo
Try our demo at [https://demo.transrag.io](https://demo.transrag.io).

<div align="center" style="margin-top:20px;margin-bottom:20px;">
<img src="https://github.com/infiniflow/transrag/assets/7248/2f6baa3e-1092-4f11-866d-36f6a9d075e5" width="1200"/>
</div>

## 🔥 Latest Updates

- 2025-02-05 Updates the model list of 'SILICONFLOW' and adds support for Deepseek-R1/DeepSeek-V3.
- 2025-01-26 Optimizes knowledge graph extraction and application, offering various configuration options.
- 2024-12-18 Upgrades Document Layout Analysis model in Deepdoc.
- 2024-12-04 Adds support for pagerank score in knowledge base.
- 2024-11-22 Adds more variables to Agent.

## 🌟 Key Features

- **Deep document understanding**-based knowledge extraction from unstructured data with complicated formats.
- **Template-based chunking** for intelligent and explainable processing.
- **Grounded citations** with reduced hallucinations for traceable answers.
- **Compatibility with heterogeneous data sources** such as Word, Excel, images, web pages, and more.
- **Automated and effortless RAG workflow** for seamless integration with businesses.

## 🎬 Get Started

### 📝 Prerequisites

- CPU >= 4 cores
- RAM >= 16 GB
- Disk >= 50 GB
- Docker >= 24.0.0 & Docker Compose >= v2.26.1

> If you have not installed Docker on your local machine, see [Install Docker Engine](https://docs.docker.com/engine/install/).

### 🚀 Start up the server

1. Ensure `vm.max_map_count` >= 262144:

   ```bash
   $ sudo sysctl -w vm.max_map_count=262144
   ```

2. Clone the repo:

   ```bash
   $ git clone https://github.com/infiniflow/transrag.git
   ```

3. Start up the server using Docker images:

   ```bash
   $ cd transrag/docker
   $ docker compose -f docker-compose.yml up -d
   ```

4. Check the server status:

   ```bash
   $ docker logs -f transrag-server
   ```

5. In your web browser, enter the IP address of your server (`http://IP_OF_YOUR_MACHINE`).

6. In [service_conf.yaml.template](./docker/service_conf.yaml.template), select the desired LLM factory in `user_default_llm` and update the `API_KEY` field with the corresponding API key.

## 🔧 Configurations

- [.env](./docker/.env): Fundamental system setups.
- [service_conf.yaml.template](./docker/service_conf.yaml.template): Configures back-end services.
- [docker-compose.yml](./docker/docker-compose.yml): Used for system startup.

To update the HTTP serving port, change `80:80` in [docker-compose.yml](./docker/docker-compose.yml) to `<YOUR_SERVING_PORT>:80`.

### Switch doc engine from Elasticsearch to Infinity

1. Stop containers:

   ```bash
   $ docker compose -f docker/docker-compose.yml down -v
   ```

2. Set `DOC_ENGINE` in **docker/.env** to `infinity`.

3. Restart containers:

   ```bash
   $ docker compose -f docker-compose.yml up -d
   ```

## 🔧 Build a Docker image

- **Without embedding models (2 GB):**

   ```bash
   git clone https://github.com/infiniflow/transrag.git
   cd transrag/
   docker build --build-arg LIGHTEN=1 -f Dockerfile -t infiniflow/transrag:nightly-slim .
   ```

- **With embedding models (9 GB):**

   ```bash
   git clone https://github.com/infiniflow/transrag.git
   cd transrag/
   docker build -f Dockerfile -t infiniflow/transrag:nightly .
   ```

## 📚 Documentation

- [Quickstart](https://transrag.io/docs/dev/)
- [User guide](https://transrag.io/docs/dev/category/guides)
- [References](https://transrag.io/docs/dev/category/references)

## 📜 Roadmap

See the [TransRag Roadmap 2025](https://github.com/infiniflow/transrag/issues/4214)

## 🏄 Community

- [Discord](https://discord.gg/4XxujFgUN7)
- [Twitter](https://twitter.com/infiniflowai)
- [GitHub Discussions](https://github.com/orgs/infiniflow/discussions)

## 🙌 


> Forked from [https://github.com/infiniflow/ragflow](https://github.com/infiniflow/ragflow)

