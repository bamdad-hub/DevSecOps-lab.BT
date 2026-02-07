# DevSecOps-lab.BT

## CI/CD Security Pipeline

This project demonstrates a simple DevSecOps pipeline using GitHub Actions.

### Features
- Docker image build
- Vulnerability scanning with Trivy
- Pipeline fails on HIGH or CRITICAL issues

### Tools
- GitHub Actions
- Docker
- Trivy

## Security Pipeline Behavior

This repository intentionally enforces security gates in the CI/CD pipeline.

The GitHub Actions workflow includes a Trivy vulnerability scan that is configured to **fail the build** when HIGH or CRITICAL vulnerabilities are detected in the Docker image.

This behavior is **expected and intentional**.

### Why the pipeline may fail
- The base Docker image may contain known vulnerabilities
- Trivy detects HIGH / CRITICAL CVEs
- The pipeline stops early to prevent insecure artifacts from being released

### DevSecOps Approach
Instead of ignoring vulnerabilities, this project demonstrates:
- Shift-left security
- Enforced security policies in CI/CD
- Fixing vulnerabilities at the source (e.g., base image updates)

This reflects a real-world DevSecOps workflow rather than a green-only demo pipeline.


Note: Some HIGH vulnerabilities may still appear due to upstream base image limitations.
This project demonstrates controlled risk acceptance rather than blind suppression.
