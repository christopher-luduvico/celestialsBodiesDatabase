# Celestial Bodies Database

Banco de dados relacional em PostgreSQL desenvolvido como projeto prático para a certificação **Relational Database** do [freeCodeCamp](https://www.freecodecamp.org/).

O projeto modela uma hierarquia astronômica utilizando integridade referencial, chaves primárias auto-incrementais, chaves estrangeiras e restrições de unicidade e nulidade.

## Estrutura do Banco (`universe`)

O banco de dados é composto por cinco tabelas principais:

- **`galaxy`**: Galáxias catalogadas (`galaxy_id`, `name`, `notes`, `age`, `distance`, `has_black_hole`).
- **`star`**: Estrelas vinculadas a uma galáxia via `galaxy_id` (`star_id`, `name`, `galaxy_id`, `temp`, `is_hot`).
- **`planet`**: Planetas orbitando estrelas via `star_id` (`planet_id`, `name`, `star_id`, `moons_count`, `has_life`).
- **`moon`**: Satélites naturais vinculados a planetas via `planet_id` (`moon_id`, `name`, `planet_id`, `radius`, `is_rocky`).
- **`asteroid`**: Corpos menores do sistema (`asteroid_id`, `name`, `size_km`).

### Relacionamentos

```text
galaxy (1) ──< (N) star (1) ──< (N) planet (1) ──< (N) moon
