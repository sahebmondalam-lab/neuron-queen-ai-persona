# Setup Guide

The persona is plain text, so it works anywhere that accepts custom instructions. Take the block from `persona/PERSONA.md` and use it as follows.

## ChatGPT
- **Settings → Personalization → Custom instructions**, paste into "How would you like ChatGPT to respond?"
- Or create a **Custom GPT** and paste it into Instructions.
- Or just paste it as your first message in a new chat.

## Claude
- Create a **Project** and paste it into the project instructions.
- Or paste it as your first message. In **Settings → Profile** you can also add preferences.

## Grok
- Paste it as your first message in a new chat (or in any custom-instructions field your version offers).

## Gemini
- Create a **Gem** and paste it into the instructions.
- Or use it as your first message.

## Meta AI, DeepSeek, Mistral Le Chat, Copilot and others
- Use the custom-instructions or system-prompt field if one exists. Otherwise paste it as the first message.

## API (any provider)

Put the persona in the system role:

```python
persona = open("persona/PERSONA.md", encoding="utf-8").read()
messages = [
    {"role": "system", "content": persona},
    {"role": "user", "content": "হ্যালো!"},
]
# send `messages` with your provider's SDK
```

## Local models (Ollama, LM Studio)

Ollama Modelfile:

```
FROM llama3
SYSTEM """<paste persona text here>"""
```

LM Studio: paste into the **System Prompt** box.

## Tips

- Tell it your preferred name and language style in your first message.
- If it drifts out of character in a long chat, repeat the persona block or say "bokkor" to refresh.
- Results vary by model. Each platform's own rules always apply.

## Troubleshooting

| Problem | Fix |
|---|---|
| Replies in English only | Greet in Bangla or add "Reply in Bangla by default" |
| Too formal | Add "Be more teasing and casual" |
| Forgets character | Re-paste the persona or say "bokkor" |
