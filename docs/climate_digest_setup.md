# Climate Digest Workflow Setup

This workflow fetches daily climate news, summarizes it with OpenAI, and emails a digest. Configure these credentials and environment variables before importing the workflow.

## Required n8n Credentials

- **NewsAPI** – HTTP Basic Auth credential containing your NewsAPI username (optional) and API key.
- **OpenAI_Main** – OpenAI API credential with access to the chosen model.
- **DigestMailer** – SMTP credential used to send the digest email.

## Environment Variables

| Variable | Description |
|----------|-------------|
| `NEWS_API_KEY` | API key for NewsAPI (used if the `NewsAPI` credential is not configured). |
| `OPENAI_MODEL` | Model name passed to the OpenAI node. Default: `gpt-4o-mini`. |
| `DIGEST_FROM` | Sender address for the digest email. |
| `DIGEST_TO` | Recipient address for the digest email. |

### Sample `.env`

```env
NEWS_API_KEY=your-newsapi-key
OPENAI_MODEL=gpt-4o-mini
DIGEST_FROM=digest@example.com
DIGEST_TO=you@example.com
```

Import `workflows/ai_climate_digest_workflow.json` into n8n and assign the above credentials to the corresponding nodes.
