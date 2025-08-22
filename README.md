# My .NET Portfolio

A consolidated repository showcasing:

- A console tool for async LINQ-based text analysis  
- A secure ASP .NET Core Web API with EF Core migrations and JWT authentication  
- A Blazor WebAssembly front end consuming the secure API  
- A React/Next.js front end with SSR/SSG and client-side auth  
- GitHub Actions CI/CD workflows and Dockerized deployments to Azure
- Current state status: `In progress` 

---

## Repository Structure

- `cmd/console-tool`  
  Console application with dependency injection and async file processing.  

- `src/Api`  
  ASP .NET Core Web API with controllers, DTOs, middleware, and EF Core data access.  

- `src/Core`  
  Shared domain models, service interfaces, and business logic abstractions.  

- `src/Infrastructure`  
  EF Core `DbContext`, migrations, data seeding, and repository implementations.  

- `src/UI.Blazor`  
  Blazor WebAssembly project consuming the secure Web API.  

- `src/UI.NextJs`  
  Next.js front end using API routes and client-side data fetching.  

- `tests`  
  xUnit test projects for console tool and API.  

- `docs`  
  Week-by-week roadmap and architecture decisions.  

- `.github/workflows/ci-cd.yml`  
  CI/CD pipeline for build, test, Docker image builds, and Azure deployments.  

---

## Prerequisites

- .NET 8.0 SDK  
- Node.js 18+ and npm or yarn  
- Azure CLI (for deployment)  
- GitHub account with Actions enabled  

---

## Getting Started

1. Clone the repository and enter the directory  
   ```bash
   git clone https://github.com/malicious-virtue/my-dotnet-portfolio.git
   cd my-dotnet-portfolio
   
2. Follow component README files for detailed setup and run instructions:
- Console Tool: `cmd/console-tool/README.md`
- Blazor UI: `src/UI.Blazor/README.md`
- Next.js UI: `src/UI.NextJs/README.md`
  
3.  Web API quick start
   ```bash
   cd src/Api
   dotnet restore
   dotnet ef database update
   dotnet run
```
- Browse Swagger at `https://localhost:5001/swagger`.

## Running test

- Run all tests from the root directory:
  ```bash
  dotnet test
  ```
- This executes unit tests for both the console tool and the Web API.

## CI/CD Pipeline

The `ci-cd.yml` workflow:- Restores, builds, and tests all .NET projects.
- Builds Docker images for console tool, API, Blazor, and Next.js apps.
- Pushes images to your container registry.
- Deploys API and Blazor apps to Azure App Service and Next.js to Azure Static Web Apps.
Configure Azure publish profiles and secrets (`AZURE_API_PUBLISH_PROFILE`, `AZURE_BLAZOR_PUBLISH_PROFILE`, `AZURE_STATIC_WEB_APPS_TOKEN`) in your GitHub repository settings.

## License

his project is licensed under the [MIT License](https://github.com/malicious-virtue/my-dotnet-portfolio/blob/main/LICENSE).
