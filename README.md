# SubQueryNetwork
Full setup of Node infrastructure 
Install Prerequisites:
Install Node.js and Yarn.

Install Docker and Docker Compose.

Create Project Directory:
Make a new directory: mkdir MyStakingProject.

Navigate into it: cd MyStakingProject.

Initialize SubQuery Project:
Run subql init MyStakingProject to scaffold the project.

Choose a network (e.g., Polkadot) and configure basic settings.

Set Up Project Structure:
Edit project.yaml: Define the blockchain network, data sources, and start block.

Update schema.graphql: Define data models (e.g., for staking rewards).

Write mapping logic in src/mappings/: Map blockchain events to your schema.

Generate and Build Code:
Run yarn install to install dependencies.

Run yarn codegen to generate TypeScript types from the schema.

Run yarn build to compile the project.

Create Docker Setup:
Create docker-compose.yml: Define services (postgres, subquery-node, graphql-engine).

Start Services:
Run docker compose up to launch the database, indexer, and query service.

Monitor Indexing:
Check logs: docker logs -f <subquery-node-container> to confirm indexing starts.

Access GraphQL playground at http://localhost:3000 to query data.

Troubleshoot Common Issues:
Reset database if changing startBlock: Use --force-clean or drop schema.

Install btree_gist extension if needed: Access database, run CREATE EXTENSION btree_gist.

Adjust resources/health checks if unhealthy: Increase CPU/memory, relax health check intervals.

Iterate and Optimize:
Monitor performance: Adjust batch size if indexing is slow.

Refine mappings: Update schema.graphql and mappings as needed, then rebuild.

