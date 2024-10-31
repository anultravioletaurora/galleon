### [OpenAI-Discord-Bridge](https://github.com/anultravioletaurora/OpenAI-Discord-Bridge)

#### Required Configuration
##### ConfigMap
A ConfigMap named ```openai-discord-bridge``` needs to exist and contain the following entries:
| Key | Description |
|-----|-------------|
| ```client_id``` | The generated Client ID of your Discord bot |
| ```gpt_model``` | The GPT model to use |
| ```guild_id``` | The ID of the guild for this bot to join |

##### Secrets
An opaque Secret name ```openai-discord-bridge``` needs to exist and contain the following entries:
| Key | Description | 
|-----|-----|
| ```bot_token``` | The generated token of your Discord bot |
| ```openai_api_key``` | The API key for your OpenAI account |