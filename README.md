# Awesome-Database-Change-Management

# Top Database Change Management Platforms Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**
*Focused on Schema Migration, Version Control, CI/CD Integration & Database DevOps*
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Database Change Management**. These tools help developers and DBAs version-control schema changes, automate migrations across environments, and integrate database deployments into CI/CD pipelines.

**Examples** include Liquibase, Flyway, Bytebase, Redgate SQL Change Automation, DbUp, SchemaHero, Atlas, Prisma Migrate, DbForge Source Control, and ApexSQL DevOps (the category leaders).

**Open-source emphasis**: Database change management has a **mature and production-proven open-source ecosystem**. **Liquibase** and **Flyway** are the two dominant tools, each with decades of development and broad database support . **Bytebase** provides a web-based DevOps platform with approval workflows and SQL review . **Atlas** brings Terraform-like declarative schema management with 50+ safety analyzers . **SchemaHero** extends declarative migrations to Kubernetes . This section documents these production-grade solutions.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Redgate SQL Change Automation](https://www.red-gate.com/products/sql-development/sql-change-automation/)**  
  Enterprise database DevOps solution for SQL Server. Extends DevOps processes to databases with migration scripts, automated deployments, and CI/CD pipeline integration . Supports hybrid approaches combining state-based and migration-based workflows .

- **[DbForge Source Control](https://www.devart.com/dbforge/)**  
  Database version control tool from Devart. Integrates with source control systems (Git, SVN, TFS) to version-control database schemas across multiple DBMS platforms.

- **[ApexSQL DevOps](https://www.apexsql.com/)**  
  Database DevOps toolkit for SQL Server. Provides schema and data comparison, source control integration, and automated deployment capabilities.

- **[Bytebase Cloud](https://bytebase.com/)**  
  Managed version of the open-source Bytebase platform. Provides database CI/CD with approval workflows, SQL review, data masking, and audit logging .

- **[Liquibase Secure](https://www.liquibase.com/)**  
  Commercial edition of Liquibase. Adds governance, policy checks, structured rollbacks, and regulatory compliance (SOX, PCI DSS, DORA) mapping . Sold in Starter, Growth, Business, and Enterprise tiers with professional services onboarding .

## Open-Source GitHub Projects

### Migration Frameworks

- **[Liquibase](https://github.com/liquibase/liquibase)**  
  **One of the two dominant open-source database migration tools.** **Apache-2.0 licensed**, Java-based. Uses a **changelog** concept with **changesets** written in SQL, XML, YAML, or JSON . **Key features**: Database-agnostic changelogs supporting **60+ databases**; standardized rollbacks, preconditions, tagging, and drift detection ; integrations with Maven, Ant, Gradle, Spring Boot, and CI/CD tools . **Target audience**: Enterprise and regulated environments needing governance and broad database coverage . **Tradeoff**: XML/YAML changelog format is verbose compared to plain SQL; learning curve is real .

- **[Flyway](https://github.com/flyway/flyway)**  
  **The developer-friendly counterpart to Liquibase.** **Apache-2.0 licensed** (Community edition), Java-based. Uses **versioned SQL scripts** (e.g., `V1__create_table.sql`) applied in order, tracked by a schema history table . **Key features**: **50+ database support** including Oracle, SQL Server, MySQL, PostgreSQL, Snowflake, and BigQuery ; plain SQL-first approach with Java and script migrations also supported; Spring Boot integration with single property update . **Target audience**: Developer-first teams wanting minimal setup and predictable execution . **Tradeoff**: Automatic rollback and schema diff are commercial (paid) features .

- **[Atlas](https://github.com/ariga/atlas)**  
  **Terraform-like declarative schema management.** **Apache-2.0 licensed**, Go-based. Offers both **declarative** (compare current state to desired state) and **versioned** migration workflows . **Key features**: **Schema as Code** (HCL, SQL, or ORM); **50+ safety analyzers** detecting destructive changes, data-dependent modifications, and table locks ; **Security-as-Code** for roles and permissions; **cloud-native CI/CD** with Kubernetes operator, Terraform provider, GitHub Actions, and ArgoCD . **Best for**: Teams wanting declarative, GitOps-friendly schema management with strong linting .

### Database DevOps Platforms

- **[Bytebase](https://github.com/bytebase/bytebase)**  
  **The only database CI/CD project in the CNCF Landscape.** **Apache-2.0 licensed**, Go and TypeScript-based . **Web-based collaboration workspace** for DBAs and developers. **Key features**: **GitOps integration** (GitHub/GitLab) for database-as-code workflows; **200+ SQL lint rules**; **approval workflows** with review and rollback; **dynamic data masking** and **RBAC**; **drift detection** and **1-click rollback** . **Supported databases**: PostgreSQL, MySQL, MongoDB, Redis, Snowflake, Oracle, SQL Server, and more . **Community edition**: Free for up to 20 users and 10 instances; Pro $20/user/month; Enterprise custom . **Best for**: Teams needing a platform with governance and audit trails .

- **[SchemaHero](https://github.com/schemahero/schemahero)**  
  **Kubernetes operator for declarative database schema management.** **Apache-2.0 licensed**, Go-based . **Key concept**: Database table schemas are expressed as **Kubernetes resources** deployed to the cluster; SchemaHero calculates the required `ALTER TABLE` statement and applies it . **Manages databases deployed in the cluster or external** (RDS, Google CloudSQL) . **Best for**: Kubernetes-native teams wanting GitOps for database schemas .

### ORM-Integrated Migrations

- **[Prisma Migrate](https://github.com/prisma/prisma)**  
  **Hybrid declarative/imperative migration tool integrated with Prisma ORM.** **Apache-2.0 licensed**, TypeScript-based . **How it works**: Data model described declaratively in Prisma schema; Prisma generates SQL migration files; generated SQL is fully customizable . **Key features**: Migration history of `.sql` files; shadow database for development; works in development and production . **Note**: For MongoDB, use `db push` instead of `migrate dev` . **Best for**: Teams already using Prisma ORM for application development .

- **[DbUp](https://github.com/DbUp/DbUp)**  
  **Simple .NET library for SQL Server database migrations.** **MIT licensed**, C#-based . **Key concept**: Embed SQL scripts as resources in a console application; DbUp tracks which scripts have run and applies only the needed ones . **Features**: `EnsureDatabase.For.SqlDatabase()` to create database if missing; `GetScriptsToExecute()` for preview; PowerShell and deployment tool integration . **Best for**: .NET teams wanting minimal, embedded migration tooling .

### Additional Strong Open-Source Options

- **Migration Frameworks**: **Liquibase** (60+ databases, enterprise governance), **Flyway** (50+ databases, developer-friendly), **Atlas** (declarative, 50+ analyzers) .
- **DevOps Platforms**: **Bytebase** (CNCF, web GUI, approval workflows), **SchemaHero** (Kubernetes operator) .
- **ORM-Integrated**: **Prisma Migrate** (TypeScript, hybrid), **DbUp** (.NET, simple) .
- **Alternatives**: **golang-migrate** (Go, simple), **Skeema** (MySQL/MariaDB, declarative pure SQL, used by GitHub) , **Alembic** (Python/SQLAlchemy), **Rails ActiveRecord Migrations** (Ruby).

**Frameworks for building custom systems**: Combine **Flyway** for simple SQL-first migrations, **Liquibase** for database-agnostic changelogs with rollback support, **Atlas** for declarative Terraform-style schema management with linting, **Bytebase** for team collaboration with approval workflows and audit trails, and **SchemaHero** for Kubernetes-native GitOps. Add **PostgreSQL** for metadata persistence and **Docker** for deployment.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Database change management tools handle sensitive production schemas and data; ensure proper access controls and compliance with change management policies.
- **Open-source reality**: The open-source ecosystem for database change management is **mature and production-proven**. **Liquibase** and **Flyway** are the two dominant tools, each with broad database support and active communities . **Bytebase** is the only database CI/CD project in the CNCF Landscape, providing web-based governance . **Atlas** brings Terraform-like declarative workflows with 50+ safety analyzers . **SchemaHero** extends declarative migrations to Kubernetes . However, **commercial editions** (Liquibase Secure, Flyway Enterprise, Redgate SQL Change Automation) provide **regulatory compliance mapping, structured rollbacks, and enterprise support** that open-source editions require additional tooling to match . The open-source path is **genuinely viable** for most teams, with the choice driven by workflow preference (SQL-first vs. changelog vs. declarative) and governance requirements.

---

**Made for database engineers, DevOps teams, DBAs, and platform engineers.**
Let's make database change management more open, transparent, and reliable.
