## Amazon Bedrock AgentCore MCP Server: [Vibe coding with your coding assistant](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/mcp-getting-started.html)

The Amazon Bedrock AgentCore Model Context Protocol (MCP) server helps you transform, deploy, and test Amazon Bedrock AgentCore-compatible agents directly from your preferred development environment. With built-in support for runtime integration, gateway connectivity, and agent lifecycle management, the MCP server simplifies moving from local development to production deployment on Amazon Bedrock AgentCore services.

The MCP server works with popular MCP clients including Kiro, Cursor, Claude Code, and Amazon Q CLI, providing conversational commands to automate complex agent development workflows.

<img width="1912" height="1005" alt="image" src="https://github.com/user-attachments/assets/b9352467-f671-49e8-bb58-e2ca7d0b765d" />


## Como desplegar un MCP en AgentCore Runtime

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

## Como desplegar un Agente en AgentCore Runtime que consuma tools de un mcp





- [CLI toolkit for deploying AI agents to Amazon Bedrock AgentCore](https://github.com/aws/bedrock-agentcore-starter-toolkit)
