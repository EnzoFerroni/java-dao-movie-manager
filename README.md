# DAO Movie Manager

[![Java](https://img.shields.io/badge/Java-17-007396?logo=openjdk&logoColor=white)](https://openjdk.org)
[![H2](https://img.shields.io/badge/H2-in--memory%20DB-1F4E79)](https://www.h2database.com)
[![Maven](https://img.shields.io/badge/Maven-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A small Java exercise implementing the Data Access Object (DAO) pattern with plain JDBC over an in-memory H2 database.

## Table of Contents

- [About](#about)
- [Design](#design)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [License](#license)

## About

Written for a systems programming course at Universidade Presbiteriana Mackenzie
(2024). The program manages a list of movies (title, duration and age rating) and
shows how a generic DAO interface keeps SQL out of the business code.

## Design

| Class | Role |
| --- | --- |
| `DAO<T>` | Generic interface: `get`, `getAll`, `insert`, `update`, `delete` |
| `Filme` | Entity: id, title, duration, age rating |
| `FilmeDAO` | JDBC implementation of `DAO<Filme>` with prepared statements |
| `DBM` | Opens and closes connections; creates the `filmes` table on startup |
| `GerenciadorDeFilmes` | Entry point that exercises every DAO operation |

The database is H2 in memory (`jdbc:h2:mem:databd`), so no setup is needed and the
data is discarded when the program exits.

## Getting Started

Requirements: JDK 17.

```bash
git clone https://github.com/EnzoFerroni/java-dao-movie-manager.git
cd java-dao-movie-manager/ProjetoDAO/GerneciadorNomes
./mvnw compile exec:java -Dexec.mainClass=br.mackenzie.ps2.bobana.GerneciadorNomes.GerenciadorDeFilmes
```

Or open the folder in an IDE and run `GerenciadorDeFilmes`.

## Project Structure

```
ProjetoDAO/GerneciadorNomes/src/main/java/br/mackenzie/ps2/bobana/GerneciadorNomes/
├── DAO.java
├── DBM.java
├── Filme.java
├── FilmeDAO.java
└── GerenciadorDeFilmes.java
```

## License

Released under the [MIT License](LICENSE). Copyright (c) 2024 Enzo Ferroni.
