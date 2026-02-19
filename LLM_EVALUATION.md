# LLM Evaluation Strategy

During development, multiple models were tested:

## OpenAI
- GPT-4o-mini
- Blocked due to API rate limit

## Anthropic
- Claude Haiku
- Marketplace billing restriction

## Amazon Titan
- titan-text-lite-v1 (deprecated)
- titan-text-express-v1 (invalid version)

## Final Model
- Meta LLaMA 3 via Amazon Bedrock

Decision Criteria:
- Stability
- Cost feasibility
- AWS-native integration
- Production compatibility
