# Browserless Documentation Index

This directory contains detailed documentation for the Browserless BQL (Browser Query Language) schema and related concepts. Below is a guide to help you find the information you need.

## Core Concepts

*   **[Introduction.md](Introduction.md)**: An introduction to Browserless offerings (BQL, BaaS, REST) and a getting started guide.
*   **[BrowserQL.md](BrowserQL.md)**: An overview of the Browser Query Language, its syntax, and general usage patterns. Start here to understand the basics of BQL.
*   **[HybridBQL.md](HybridBQL.md)**: Documentation on Hybrid BQL, which likely combines different querying approaches or extends standard BQL capabilities.
*   **[APIs.md](APIs.md)**: Information about the Browserless APIs, including endpoints and authentication.
*   **[REST-API-Example.md](REST-API-Example.md)**: Examples of using the REST API for common tasks like screenshots.
*   **[BaaS-Example.md](BaaS-Example.md)**: Examples of using Browsers as a Service (BaaS) with Puppeteer/Playwright.
*   **[Example-Booking.md](Example-Booking.md)**: A placeholder or example file for Booking.com automation (currently empty).
*   **[Advanced.md](Advanced.md)**: Advanced topics and configurations for power users.
*   **[UseCases.md](UseCases.md)**: Examples and common use cases for Browserless automation.
*   **[References.md](References.md)**: General references and external links.
*   **[Responses.md](Responses.md)**: Details on the structure and types of responses returned by Browserless operations.

## Schema & Types

*   **[Ops-mutations.md](Ops-mutations.md)**: Comprehensive documentation of all **Mutations** available in BQL (e.g., `goto`, `click`, `type`, `screenshot`). This is the primary reference for actions you can perform.
*   **[Ops - directives.md](Ops%20-%20directives.md)**: Documentation for BQL **Directives** (e.g., `@deprecated`, `@include`), which modify the behavior of queries and mutations.
*   **[types-objects.md](types-objects.md)**: Definitions of **Object** types returned by mutations or used within the schema (e.g., `HTTPResponse`, `ScreenshotResponse`).
*   **[types-scalars.md](types-scalars.md)**: Definitions of **Scalar** types (basic data types) used in the schema (e.g., `String`, `Int`, `Boolean`).
*   **[types-enums.md](types-enums.md)**: Definitions of **Enum** types (enumerated lists of values) used for specific parameters (e.g., `KeyboardEvent`, `ScreenshotType`).
*   **[types-inputs.md](types-inputs.md)**: Definitions of **Input** types used as arguments for mutations (e.g., `CookieInput`, `ViewportInput`).
*   **[types-schemas.md](types-schemas.md)**: Information about the underlying GraphQL schemas and type definitions.

## Navigation Guide for Agents

*   **To perform an action:** Check **[Ops-mutations.md](Ops-mutations.md)** to find the appropriate mutation.
*   **To understand arguments:** Look up Input types in **[types-inputs.md](types-inputs.md)** and Enums in **[types-enums.md](types-enums.md)**.
*   **To understand return values:** Refer to **[types-objects.md](types-objects.md)** and **[types-scalars.md](types-scalars.md)**.
*   **To learn about the protocol:** Read **[BrowserQL.md](BrowserQL.md)** and **[APIs.md](APIs.md)**.
