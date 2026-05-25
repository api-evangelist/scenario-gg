# Scenario (scenario-gg)
Scenario is a Paris- and San Francisco-headquartered AI platform for game asset generation founded in 2021 by Emmanuel de Maistre and Hervé Nivon. The Scenario REST API lets game studios and creative teams generate consistent, on-brand images, video, audio, and 3D assets, train custom LoRA models on their own reference art, automate batch asset pipelines, and integrate AI-generated visuals into production tools like Unity. Scenario aggregates 500+ AI models from 50+ providers behind a single workspace and API, with full commercial licensing for generated assets and enterprise SSO, SOC 2 Type II, and governance controls.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/scenario-gg/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - AI, Artificial Intelligence, Game Assets, Game Development, Generative AI, Image Generation, Video Generation, Audio Generation, 3D Assets, Custom Model Training, LoRA, ControlNet, Creative AI, Asset Pipeline

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Base URL

`https://api.cloud.scenario.com/v1`

Authentication: HTTP Basic Auth using Base64-encoded `API_KEY:API_SECRET` in the `Authorization` header. API keys are created in the Scenario web app on a paid plan (Pro, Max, or Enterprise).

## APIs

### Scenario Models API
List, inspect, and manage custom and base AI models available to a Scenario account. Returns training status, training progress, model type (image, video, audio, 3D), and metadata for the 500+ base models and any LoRA models trained on a team's reference art. Custom training typically completes in 30 minutes to one hour from 10-50+ reference images.

**Human URL:** [https://docs.scenario.com/reference/getmodels](https://docs.scenario.com/reference/getmodels)

- [Documentation — List models](https://docs.scenario.com/reference/getmodels)
- [Documentation — Get model by id](https://docs.scenario.com/reference/getmodelsbymodelid)

### Scenario Generation API
Generate game-ready images, video, audio, and 3D assets from text prompts, reference images, or ControlNet guides. Supports text-to-image, image-to-image, ControlNet (txt2img and img2img), text-to-3D, image-to-3D, and modality-specific endpoints for video and audio. Accepts prompt, negative prompt, numSamples, guidance, numInferenceSteps, width, height, and modelId; returns an async job that resolves into one or more assets. A `dryRun` parameter returns the compute-unit cost without executing the job.

**Human URL:** [https://docs.scenario.com/reference/postgeneratecustom](https://docs.scenario.com/reference/postgeneratecustom)

- [Documentation — Generate with any model](https://docs.scenario.com/reference/postgeneratecustom)
- [Documentation — Image-to-Image](https://docs.scenario.com/docs/image-to-image)
- [Documentation — ControlNet](https://docs.scenario.com/docs/controlnet)
- [Documentation — 3D Model Generation](https://docs.scenario.com/docs/3d-model-generation)

### Scenario Jobs API
Inspect the status, progress, metadata, and output assets of an asynchronous generation or training job. Generation and training requests return a `jobId` immediately; clients poll the Jobs API (or receive a webhook callback) to retrieve the final assets once the job reaches a terminal state.

**Human URL:** [https://docs.scenario.com/reference/getjobsbyjobid](https://docs.scenario.com/reference/getjobsbyjobid)

### Scenario Assets API
List, retrieve, upload, and manage the images, video, audio, and 3D assets stored in a team's Scenario workspace. Includes endpoints for project-private assets, public asset retrieval, and asset upload for use as reference images, training data, or ControlNet inputs. All assets carry full commercial-use licensing for paid-plan accounts.

**Human URL:** [https://docs.scenario.com/reference/getassets](https://docs.scenario.com/reference/getassets)

- [Documentation — List assets](https://docs.scenario.com/reference/getassets)
- [Documentation — Get asset by id](https://docs.scenario.com/reference/getassetsbyassetid)
- [Documentation — Get public asset by id](https://docs.scenario.com/reference/getpublicassetsbyassetid)
- [Documentation — Uploading Assets](https://docs.scenario.com/docs/uploading-images)

### Scenario Usage API
Retrieve unified compute-unit consumption for an account, filtered by date range, project, or model. Compute units match the metering used by the Scenario web application and are consumed by both generation jobs and custom training jobs.

**Human URL:** [https://docs.scenario.com/reference/getusages](https://docs.scenario.com/reference/getusages)

## Plans

| Plan | Monthly | Annual | Credits / Limits | Notes |
|---|---|---|---|---|
| Starter | $15 | $10 | 1,500 credits, 50 GB | Single-user workspace, 65+ core models, no API access |
| Pro | $45 | $30 | 5,000 credits, 500 GB | API access, custom model training, priority queue |
| Max | $75 | $50 | 10,000 credits, up to 25 seats, 1 TB+ | Team collaboration, monitoring dashboards |
| Enterprise | Custom | Custom | 10 TB+ | SSO, SOC 2 Type II, governance, dedicated team |

## SDKs and Tools

- [Scenario Unity Plugin](https://github.com/scenario-labs/Scenario-Unity) — Generate inside the Unity Editor
- [LTX-2](https://github.com/scenario-labs/LTX-2) — In-house audio-video generative model and LoRA trainer
- [diffusers](https://github.com/scenario-labs/diffusers) — State-of-the-art diffusion models in PyTorch
- [PowerPaint](https://github.com/scenario-labs/PowerPaint) — Inpainting (insertion, removal, outpainting)
- [FastSAM](https://github.com/scenario-labs/FastSAM) — Fast Segment Anything
- [ai-toolkit](https://github.com/scenario-labs/ai-toolkit) — Stable Diffusion utilities
- [model-police](https://github.com/scenario-labs/model-police) — Model checkpoint validator
- [awesome-blender-script](https://github.com/scenario-labs/awesome-blender-script) — Blender scripting resources

## Common Links

- [Welcome to the Scenario API](https://docs.scenario.com/docs/welcome-to-scenario-api)
- [API Key and Authentication](https://docs.scenario.com/docs/api-key-and-authentication)
- [Obtain Your API Key](https://docs.scenario.com/docs/step-1-obtain-your-api-key)
- [Overviewing the API (Help Center)](https://help.scenario.com/en/articles/overviewing-the-api/)
- [Creating an API Key (Help Center)](https://help.scenario.com/en/articles/creating-an-api-key/)
- [Scenario REST API marketing page](https://www.scenario.com/features/api)
- [Custom Model Training](https://www.scenario.com/features/train)
- [Scenario OpenAPI Specification (swagger.yaml)](https://cdn.cloud.scenario.com/static/api/swagger.yaml)
- [Scenario Web App](https://app.scenario.com)
- [Sign Up](https://app.scenario.com/signup)
- [LinkedIn](https://www.linkedin.com/company/scenario-com)
- [GitHub Organization](https://github.com/scenario-labs)
- [Pricing](https://www.scenario.com/pricing)

## Maintainers

- **Name:** Kin Lane
- **Email:** info@apievangelist.com
- **X:** [apievangelist](https://x.com/apievangelist)
- **URL:** [apievangelist.com](https://apievangelist.com)

---

specificationVersion: 0.16
