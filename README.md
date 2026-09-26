📈 GitHub Stats

<img width="1173" height="366" alt="image" src="https://github.com/user-attachments/assets/d8b37324-4a56-43fa-909a-012a85eb9de9" />


# 📈 GitHub Stats

<img width="1173" height="366" alt="image" src="https://github.com/user-attachments/assets/d8b37324-4a56-43fa-909a-012a85eb9de9" />

## 🚀 Featured Projects

### [kuhaku.dev](https://kuhaku.dev) - Personal Blog Architecture & Migration
This repository contains the Flask application and routing logic for my personal blog. It is currently undergoing a structural migration to dynamic Jinja2 templates and a cleanly decoupled Repository Pattern architecture.

**Application Architecture (Data Layer)**
The backend has been refactored to cleanly separate data structures from data retrieval, allowing for a seamless toggle between mock data (for local development) and a production database (MongoDB).
- **`dtos/`**: Pure Python `@dataclass` definitions representing the data shape (e.g., `ArticleSummary`, `SocialActivity`). Contains zero business logic, getters, or database queries.
- **`repository/`**: Contains the business logic for fetching data, utilizing Python Protocols to enforce strict interfaces across domains (Homepage, Articles, Common, Devlogs).
- **Mock vs. Real Repositories**: Toggle between hardcoded data implementations for fast local UI development and production implementations designed for a database connection pool.
- **Global Registry (`AppRepositories`)**: Instantiated once at startup as a Singleton. Flask routes rely entirely on this registry, keeping them completely agnostic to whether the underlying data is mock or real.

**Template Architecture & Routing**
To protect unmigrated content and ensure a clean public codebase, the project uses a split-directory architecture managed by a custom Jinja loader (`ABTestingLoader`):
- **`templates_final/`**: The modernized, fully refactored Jinja templates utilizing `base.html` inheritance. This is publicly tracked in Git and served on standard routes (`/`).
- **`templates_original/`**: Raw, original HTML actively being transformed. Intentionally excluded via `.gitignore` to prevent revealing sensitive data. Served strictly on `/migration/` routes to allow side-by-side local testing without conflicting namespaces.

---

### PyGraph
*Public* • **TypeScript** • ⭐ 5

A published VS Code extension designed to help developers handle complex refactors and untangle spaghetti code.

---

### iteration_spaces
*Public* • **Python**

Experiments with SpGEMM optimizations. Contains benchmarks on an experimental optimization for matrix multiplication (matmul), utilizing Python for explicit algorithm viewing and testing.
