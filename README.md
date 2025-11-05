<!--
SPDX-License-Identifier: Apache-2.0
SPDX-FileCopyrightText: 2025 The Linux Foundation
-->

# Test Repository: HTTP API Tool

This repository contains test workflows for the
[http-api-tool-docker](https://github.com/lfreleng-actions/http-api-tool-docker)
GitHub Action.

## Purpose

This repository tests both deployment modes of the HTTP API Tool action:

- **UVX mode** (default): Fast deployment using `uvx` to run the tool
  directly from PyPI
- **Docker mode**: Containerized deployment using the published Docker
  image from GHCR

## Workflows

### Test HTTP API Tool

**Workflow**: `.github/workflows/testing.yaml`

This workflow runs on manual trigger (`workflow_dispatch`) and performs
parallel testing of both deployment modes against the Linux Foundation
website.

**Features**:

- ✅ Two parallel jobs testing the same endpoint
- ✅ Configurable URL and expected HTTP status code via workflow inputs
- ✅ Detailed performance metrics in job summaries
- ✅ Comparison of both deployment modes

**Default Test**:

- URL: `https://linuxfoundation.org`
- Expected HTTP Code: `200`
- Retries: `3`

## Running the Tests

1. Go to the **Actions** tab in this repository
2. Select "Test HTTP API Tool"
3. Click "Run workflow"
4. (Optional) Customize the URL and expected status code
5. Click "Run workflow" to start

## Results

After the workflow completes, check the job summaries for:

- HTTP status code received
- Success/failure status
- Total request time
- Connection time
- Time delay (retry wait time)

The workflow will show which deployment mode (if any) performs better for
the given endpoint.

## Repositories

Official repositories:

- GitHub:
  [lfreleng-actions/http-api-tool-docker](https://github.com/lfreleng-actions/http-api-tool-docker)
- Docker Image:
  [ghcr.io/lfreleng-actions/http-api-tool-docker](https://ghcr.io/lfreleng-actions/http-api-tool-docker)
- PyPI Package:
  [http-api-tool](https://pypi.org/project/http-api-tool/)

## License

Apache-2.0
