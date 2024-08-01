# ePrijzen Database

Deze SQLite-database is ontworpen voor gebruik binnen de ePrijzen-omgeving. Hoewel de database geen wachtwoorden of persoonlijke gegevens bevat, zijn er nog steeds gegevens aanwezig die zorgvuldig moeten worden behandeld.

## Inhoud

- [Database Overzicht](#database-overzicht)
- [Contactgegevens](#contactgegevens)
- [Licentie](#licentie)

## Database Overzicht

### Table: energy

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| fromdate | VARCHAR (10) | Yes | None | Yes |
| fromtime | VARCHAR (5) | Yes | None | Yes |
| kind | VARCHAR (10) | Yes | None | Yes |
| price | DOUBLE | Yes | None | No |
| country | VARCHAR (3) | No | NL | Yes |

### Table: countries

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| country_id | VARCHAR (6) | No | None | Yes |
| country_iso | VARCHAR (2) | No | None | No |
| country | VARCHAR (20) | No | None | No |

### Table: api_users

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| email | VARCHAR | No | None | Yes |
| password | VARCHAR | No | None | No |
| hits | INTEGER | No | None | No |

### Table: generation

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| fromdate | varchar(10) | No | None | Yes |
| fromtime | varchar(5) | No | None | Yes |
| mw | INT | No | None | No |
| kind | varchar(10) | No | None | Yes |
| country | varchar(3) | No | NL | Yes |

### Table: leveranciers

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| leverancier | VARCHAR | Yes | None | Yes |
| fromdate | VARCHAR (10) | Yes | None | Yes |
| kind | VARCHAR (2) | Yes | None | Yes |
| price | FLOAT | No | None | No |
| country | VARCHAR (10) | Yes | None | Yes |

### Table: users

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| user_id | INTEGER | No | None | Yes |
| datetime | INTEGER | No | None | No |
| kaal_opslag_allin | CHAR | No | 'k' | No |
| ochtend | INTEGER | No | 8 | No |
| middag | INTEGER | No | 16 | No |
| opslag_electra | DOUBLE | No | None | No |
| opslag_gas | DOUBLE | No | None | No |
| melding_lager_dan | DOUBLE | No | 0.001 | No |
| ode_gas | DOUBLE | No | None | No |
| ode_electra | DOUBLE | No | None | No |
| eb_electra | DOUBLE | No | None | No |
| eb_gas | DOUBLE | No | None | No |
| country | VARCHAR (5) | No | 'NL' | No |
| locale | CHAR (5) | No | 'de_DE' | No |
| api_price | DOUBLE | No | 0.004152778 | No |
| api_calls | INTEGER | No | 740 | No |
| salt_key | VARCHAR (20) | No | "ThEoIsTheBest" | No |
| api_key | VARCHAR (100) | No | None | No |
| api_valid_date | VARCHAR (10) | No | None | No |

### Table: belasting_regels

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| kind | VARCHAR (1) | No | None | Yes |
| btw | DOUBLE | No | None | No |
| opslag | DOUBLE | No | None | No |
| ode | DOUBLE | No | None | No |
| eb | DOUBLE | No | None | No |
| start_date | VARCHAR (10) | No | None | Yes |
| end_date | VARCHAR (10) | No | None | No |

### Table: belastingen

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| kind | VARCHAR (1) | No | None | Yes |
| datum | VARCHAR (10) | No | None | Yes |
| btw | INTEGER | No | None | No |
| opslag | DOUBLE | No | None | No |
| eb | DOUBLE | No | None | No |
| ode | DOUBLE | No | None | No |

### Table: dates

| Column Name | Data Type | Not Null | Default Value | Primary Key |
|-------------|-----------|----------|---------------|-------------|
| dte |  | No | None | No |

## Contactgegevens

Voor vragen of ondersteuning, neem contact op met de ontwikkelaar:

- **Ontwikkelaar**: Theo van der Sluijs
  - **Website**: [itheo.tech](https://itheo.tech)
  - **E-mail**: [theo@vandersluijs.nl](mailto:theo@vandersluijs.nl)
  - **GitHub**: [tvdsluijs](https://github.com/tvdsluijs)
  - **Telegram**: [tvdsluijs](https://t.me/tvdsluijs)

## Licentie

Dit project valt onder de MIT-licentie. Zie het [LICENSE](./LICENSE)-bestand voor meer informatie.
