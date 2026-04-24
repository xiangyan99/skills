---
name: azure-ai-language-conversations-py
description: Implement Conversational Language Understanding (CLU) using the azure-ai-language-conversations Python SDK. Use when working with ConversationAnalysisClient to analyze conversation intent and entities, building NLP features, or integrating language understanding into applications.
license: MIT
metadata:
  author: Microsoft
  version: "1.0.0"
---

# Azure AI Language Conversations for Python

## System Prompt
You are an expert Python developer specializing in Azure AI Services and Natural Language Processing.
Your task is to help users implement Conversational Language Understanding (CLU) using the `azure-ai-language-conversations` SDK.

When responding to requests about Azure AI Language Conversations:
1. Always use the latest version of the `azure-ai-language-conversations` SDK.
2. Emphasize the use of `ConversationAnalysisClient` with `AzureKeyCredential`.
3. Provide clear code examples demonstrating how to structure the conversation payload.
4. Handle exceptions properly.

## Best Practices
- **Pick sync OR async and stay consistent.** Do not mix `azure.ai.language.conversations` sync clients with `azure.ai.language.conversations.aio` async clients in the same call path. Choose one mode per module.
- **Always use context managers for clients and async credentials.** Wrap every client in `with ConversationAnalysisClient(...) as client:` (sync) or `async with ConversationAnalysisClient(...) as client:` (async). For async `DefaultAzureCredential` from `azure.identity.aio`, also use `async with credential:` so tokens and transports are cleaned up.
- Use environment variables for the endpoint, API key, project name, and deployment name.
- Clearly map the `participantId` and `id` in the `conversationItem` payload.

## Examples

### Basic Conversation Analysis
```python
import os
from azure.core.credentials import AzureKeyCredential
from azure.ai.language.conversations import ConversationAnalysisClient

endpoint = os.environ["AZURE_CONVERSATIONS_ENDPOINT"]
key = os.environ["AZURE_CONVERSATIONS_KEY"]
project_name = os.environ["AZURE_CONVERSATIONS_PROJECT"]
deployment_name = os.environ["AZURE_CONVERSATIONS_DEPLOYMENT"]

client = ConversationAnalysisClient(endpoint, AzureKeyCredential(key))

with client:
    query = "Send an email to Carol about the tomorrow's meeting"
    result = client.analyze_conversation(
        task={
            "kind": "Conversation",
            "analysisInput": {
                "conversationItem": {
                    "participantId": "1",
                    "id": "1",
                    "modality": "text",
                    "language": "en",
                    "text": query
                },
                "isLoggingEnabled": False
            },
            "parameters": {
                "projectName": project_name,
                "deploymentName": deployment_name,
                "verbose": True
            }
        }
    )

    print(f"Top intent: {result['result']['prediction']['topIntent']}")