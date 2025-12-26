# Configuración Obsidian Git

## Plugins necesarios

1. **Obsidian Git** (ya instalado)
2. **Dataview** (instalar desde Community Plugins)
3. **Templater** (ya instalado)

---

## Configuración recomendada: Obsidian Git

Abre `Settings > Community Plugins > Obsidian Git > Options`:

### Automatic

| Setting | Valor | Por qué |
|---------|-------|---------|
| `Auto backup every X minutes` | `10` | Backup frecuente sin ser molesto |
| `Auto pull on startup` | `ON` | Sincroniza al abrir Obsidian |
| `Auto push on backup` | `ON` | Sube cambios automáticamente |
| `Commit message` | `vault backup: {{date}}` | Mensaje claro |

### Commit

| Setting | Valor |
|---------|-------|
| `Commit message on auto backup` | `auto: {{date}} {{time}}` |
| `Date format` | `YYYY-MM-DD` |
| `Time format` | `HH:mm` |

---

## Configuración: Daily Notes

`Settings > Core Plugins > Daily Notes`:

| Setting | Valor |
|---------|-------|
| `New file location` | `00 Diario` |
| `Template file location` | `templates/Daily Note` |
| `Date format` | `YYYY-MM-DD` |

---

## Configuración: Templater

`Settings > Templater`:

| Setting | Valor |
|---------|-------|
| `Template folder location` | `templates` |

---

## Configuración: Dataview

`Settings > Dataview`:

| Setting | Valor |
|---------|-------|
| `Enable JavaScript Queries` | `ON` (opcional) |
| `Automatic view refresh` | `ON` |

---

## Comandos útiles

| Atajo | Comando |
|-------|---------|
| `Cmd+P` → "Git: Push" | Subir cambios manualmente |
| `Cmd+P` → "Git: Pull" | Bajar cambios |
| `Cmd+P` → "Open daily note" | Crear/abrir nota del día |

---

## Remote (opcional)

Si quieres sincronizar con GitHub/GitLab:

```bash
cd ~/Documents/elmiona
git remote add origin git@github.com:TU_USUARIO/elmiona.git
git push -u origin main
```

---

> Vault inicializado: {{date}}
