# digital_hub

Ein wesentlicher Ansatzpunkt für Innovationen ist gegenwärtig die Digitalisierung - auch im Feld der Vernetzung von Gruppen. Sie bietet eine Vielzahl von Möglichkeiten für alle Arten von Austausch und Innovationen, seien es Produkt-, Prozess-, organisatorische Innovationen. Die Digital Hubs - sie sind wie Kristallisationspunkte für Austausch, und Innovation aller Beteiligten; Hier treffen unterschiedlichste Kompetenzen, Disziplinen, Ideen aufeinander und stellen so Akzeleratoren für Entwicklungen u. Innovationen dar. Diese Hubs, verstanden als digitales Ökosystem vereinen Prinzipien, die ganz wesentlich den Erfolg sichern; sehr prominente Beispiele solcher Hubs stellen das EDIH- und das de:hub-Projekt dar. In wissensökologischer Sicht stellen die Digitalen Hubs "Knowledge Broker" dar, Agenturen des Wissens und Schrittmacher von Wissenstransfer, Erneuerung und Innovation. Dieser Ansatz ist grundlegend für das hier - skizzenhaft vorgestellte - Modellprojekt eines Digital Innovation Hub für die Heidelberger Region. Hier soll im Wesentlichen von den besteheneden Leuchtturm-Projekten gelernt werden.

Leuchttürme sind das EDIH-Projekt: https://s3platform.jrc.ec.europa.eu/digital-innovation-hubs-tool,

EDIHsProjekt

720 Hubs in Europa...



# 🧰 SQL Toolbox – Quick Reference (Webmin + WordPress)

A compact bilingual cheat sheet 🇩🇪 **Deutsch** + 🇬🇧 **English**  
for managing MySQL databases and users via **Webmin** (useful for WordPress setups).  

---

## 📂 Databases
| 🇩🇪 Deutsch | 🇬🇧 English |
|------------|-------------|
| `SHOW DATABASES;` | `SHOW DATABASES;` |
| `CREATE DATABASE \`meinedb\` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;` | `CREATE DATABASE \`mydb\` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;` |
| `DROP DATABASE \`meinedb\`;` | `DROP DATABASE \`mydb\`;` |

---

## 👤 Users
| 🇩🇪 Deutsch | 🇬🇧 English |
|------------|-------------|
| `SELECT User, Host FROM mysql.user;` | `SELECT User, Host FROM mysql.user;` |
| `CREATE USER 'meinuser'@'localhost' IDENTIFIED BY 'MeinPass!';` | `CREATE USER 'myuser'@'localhost' IDENTIFIED BY 'MyPass!';` |
| `DROP USER 'meinuser'@'localhost';` | `DROP USER 'myuser'@'localhost';` |

---

## 🔑 Permissions
| 🇩🇪 Deutsch | 🇬🇧 English |
|------------|-------------|
| `GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, ALTER, INDEX, DROP ON \`meinedb\`.* TO 'meinuser'@'localhost';` | `GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, ALTER, INDEX, DROP ON \`mydb\`.* TO 'myuser'@'localhost';` |
| `SHOW GRANTS FOR 'meinuser'@'localhost';` | `SHOW GRANTS FOR 'myuser'@'localhost';` |
| `FLUSH PRIVILEGES;` | `FLUSH PRIVILEGES;` |

---

## 🩺 Diagnostics
| 🇩🇪 Deutsch | 🇬🇧 English |
|------------|-------------|
| `SELECT DATABASE();` | `SELECT DATABASE();` |
| `SHOW TABLES;` | `SHOW TABLES;` |
| `DESCRIBE wp_options;` | `DESCRIBE wp_options;` |
| `SELECT table_schema, ROUND(SUM(data_length+index_length)/1024/1024,2) AS SizeMB FROM information_schema.tables GROUP BY table_schema;` | `SELECT table_schema, ROUND(SUM(data_length+index_length)/1024/1024,2) AS SizeMB FROM information_schema.tables GROUP BY table_schema;` |

---

## ⚡ WordPress Setup
| 🇩🇪 Deutsch | 🇬🇧 English |
|------------|-------------|
| `CREATE DATABASE \`wp_site\`;` | `CREATE DATABASE \`wp_site\`;` |
| `CREATE USER 'wp_site_user'@'localhost' IDENTIFIED BY 'MeinPass!';` | `CREATE USER 'wp_site_user'@'localhost' IDENTIFIED BY 'MyPass!';` |
| `GRANT ALL PRIVILEGES ON \`wp_site\`.* TO 'wp_site_user'@'localhost';` | `GRANT ALL PRIVILEGES ON \`wp_site\`.* TO 'wp_site_user'@'localhost';` |
| `FLUSH PRIVILEGES;` | `FLUSH PRIVILEGES;` |

---

## 📌 Notes
- Always **separate databases and users** (1 DB = 1 user) for WordPress – avoids conflicts and improves security.  
- Use the **per-DB SQL Execute Widget** in Webmin to run these statements step by step.  
- `FLUSH PRIVILEGES;` applies changes immediately.  
- Default WordPress privileges: `SELECT, INSERT, UPDATE, DELETE, CREATE, ALTER, INDEX, DROP`.  

---

✨ With this cheat sheet you can set up and manage WordPress databases in Webmin **without depending on a buggy GUI**.  

