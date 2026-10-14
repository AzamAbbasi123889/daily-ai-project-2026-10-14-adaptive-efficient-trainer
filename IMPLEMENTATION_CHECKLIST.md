# Implementation Checklist

Build the application yourself using `PROJECT_BRIEF.md`.

## Initial setup

- [ ] Read the project specification.
- [ ] Review the architecture and data model.
- [ ] Create a Python virtual environment.
- [ ] Install and pin the required dependencies.
- [ ] Configure credentials through environment variables.
- [ ] Review the data privacy and security requirements.

## Project acceptance criteria

- [ ] API returns per‑layer memory usage within ±5% of torch.cuda.memory_allocated
- [ ] Upload size limit 50 MB enforced
- [ ] Response latency < 5 seconds for 10 MB model
- [ ] Generated config respects GPU memory budget (≤95% of total)
- [ ] Config includes keys: batch_size, amp_enabled, checkpoint_layers, grad_accum_steps
- [ ] Unit tests verify optimizer never exceeds memory limit on 2 GB, 4 GB, and 8 GB simulated GPUs
- [ ] Script runs without SyntaxError
- [ ] Script reproduces the recommended settings when executed with the same model/dataset sample
- [ ] User can trigger script execution via a POST /run endpoint for a 1‑epoch dry‑run
- [ ] Set up repo, Dockerfile, CI
- [ ] Implement model upload endpoint
- [ ] Write Profiler with torch.cuda.memory hooks
- [ ] Define heuristic rule table
- [ ] Implement Optimizer logic
- [ ] Create Jinja2 training script template
- [ ] Add /config endpoint
- [ ] Integrate MLflow logging
- [ ] Add optional React UI (basic file picker + result view)
- [ ] Write end‑to‑end tests
- [ ] Prepare README and portfolio write‑up
- [ ] Unit tests for each Optimizer rule (pytest).
- [ ] Integration test: upload sample model → receive config → dry‑run → assert no OOM.
- [ ] Load‑test using Locust to simulate 5 concurrent users uploading.
- [ ] Security test: ensure only .pt files are accepted, scan for malicious code with safetensors.
- [ ] MLflow verification: each request creates a run with expected tags.
- [ ] Docker Compose for local development (GPU passthrough).
- [ ] GitHub Actions CI builds multi‑arch Docker image and pushes to GitHub Container Registry.
- [ ] Optional cloud deployment via Render or Fly.io (GPU‑enabled tier).
- [ ] Use OpenTelemetry for request tracing; expose Prometheus metrics.

## Before completion

- [ ] Implement the planned MVP features.
- [ ] Add unit and integration tests.
- [ ] Run the test suite.
- [ ] Measure the evaluation metrics in the brief.
- [ ] Record actual results and known limitations.
- [ ] Document setup and deployment.
- [ ] Update the README to reflect the implemented features.
- [ ] Add only verified outcomes to your resume.
