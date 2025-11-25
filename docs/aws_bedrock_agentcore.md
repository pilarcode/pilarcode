

# Como desplegar un MCP en AgentCore Runtime

### Instalar el CLI
pip install bedrock-agentcore-starter-toolkit

### Configurar el MCP server (desde el directorio 00-experiments/mcp/)
agentcore configure --entrypoint mcp_server.py --protocol MCP --non-interactive

### Desplegar a AWS
agentcore launch

### Obtener el endpoint URL
agentcore status --verbose

### Probar el mcp en el entorno de pruebas (opcion: Con identidad Protocolo MCP)
<img width="1650" height="596" alt="image" src="https://github.com/user-attachments/assets/f3650d2a-6ba6-4bd3-a755-034a034b1b5f" />


- [CLI toolkit for deploying AI agents to Amazon Bedrock AgentCore](https://github.com/aws/bedrock-agentcore-starter-toolkit)
