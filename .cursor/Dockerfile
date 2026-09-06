# Base image for the Infer.NET Cloud Agent development environment.
# Uses the official .NET 10 SDK image so `dotnet build`/`dotnet test` work out of the box.
FROM mcr.microsoft.com/dotnet/sdk:10.0

# Tooling required by Cursor Cloud Agents and general development.
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        git \
        curl \
        ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Opt out of telemetry / first-run noise for deterministic, non-interactive builds.
ENV DOTNET_CLI_TELEMETRY_OPTOUT=1 \
    DOTNET_NOLOGO=1 \
    DOTNET_SKIP_FIRST_TIME_EXPERIENCE=1
