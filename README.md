Ein Projekt das wir Woche für Woche erweitern auch die Read.md wird sich erweitern


# Read.md Syntax Guide
## Heading 2
### Heading 3

**bold**, *italic*, ~~strikethrough~~, `inline code`

- Bullet item
  - Nested item
1. Numbered item
2. Another item
- [x] Done task
- [ ] Open task

[Link text](https://example.com)
![Alt text](image.png)

> Blockquote

---   (horizontal rule)

| Column A | Column B |
|----------|----------|
| cell     | cell     |

```python
print("fenced code block with language")
```

# Git-Befehle für GitHub

## Einrichtung (einmalig)
```bash
git --version                                  # Git installiert?
git config --global user.name "Dein Name"
git config --global user.email "deine@mail.at"
git config --global init.defaultBranch main    # Standard-Branch heißt main
git config --list                              # Einstellungen anzeigen
```

## Repository anlegen oder holen
```bash
git init                                       # neues Repo im aktuellen Ordner
git clone https://github.com/NAME/REPO.git     # Repo von GitHub herunterladen
```

## Mit GitHub verbinden
```bash
git remote add origin https://github.com/NAME/REPO.git   # Verbindung herstellen
git remote -v                                  # Verbindungen anzeigen
git remote set-url origin NEUE-URL             # URL ändern
```

## Täglicher Ablauf
```bash
git status                  # Was hat sich geändert?
git add datei.py            # einzelne Datei vormerken
git add .                   # alle Änderungen vormerken
git commit -m "Nachricht"   # Änderungen speichern
git push -u origin main     # erstes Mal hochladen
git push                    # danach nur noch das
git pull                    # Änderungen von GitHub holen
git fetch                   # Änderungen nur herunterladen, nicht einbauen
```

## Verlauf und Unterschiede ansehen
```bash
git log                     # kompletter Verlauf
git log --oneline           # kurz, eine Zeile pro Commit
git log --oneline --graph --all   # mit Branch-Grafik
git diff                    # was habe ich noch nicht vorgemerkt?
git diff --staged           # was ist vorgemerkt?
git show COMMIT-ID          # Details zu einem Commit
```

## Branches
```bash
git branch                  # Branches auflisten
git branch neuer-branch     # Branch anlegen
git switch neuer-branch     # Branch wechseln
git switch -c neuer-branch  # anlegen und wechseln
git merge neuer-branch      # in den aktuellen Branch einbauen
git branch -d neuer-branch  # lokal löschen
git push origin neuer-branch            # Branch auf GitHub hochladen
git push origin --delete neuer-branch   # auf GitHub löschen
```

## Änderungen rückgängig machen
```bash
git restore datei.py              # Änderungen an Datei verwerfen
git restore --staged datei.py     # aus "vorgemerkt" zurücknehmen
git commit --amend -m "Neue Nachricht"   # letzten Commit anpassen (vor dem Push!)
git revert COMMIT-ID              # Commit durch Gegen-Commit aufheben (sicher)
git reset --soft HEAD~1           # letzten Commit zurücknehmen, Änderungen bleiben
git reset --hard HEAD~1           # letzten Commit samt Änderungen löschen (Vorsicht!)
git stash                         # Änderungen kurz zwischenlagern
git stash pop                     # wieder zurückholen
```

## Dateien verwalten
```bash
git rm datei.py             # löschen und vormerken
git rm --cached datei.py    # nicht mehr verfolgen, Datei bleibt lokal
git mv alt.py neu.py        # umbenennen
```

## .gitignore (Dateien ausschließen)
```bash
echo "secret.csv" >> .gitignore
echo ".venv/" >> .gitignore
echo ".idea/" >> .gitignore
```

## Zusammenarbeit auf GitHub
```bash
git pull --rebase           # Änderungen holen, eigene obendrauf setzen
git tag v1.0                # Version markieren
git push origin v1.0        # Tag hochladen
```
Fork, Pull Request und Issues werden auf der GitHub-Webseite erledigt.

## Anmeldung bei GitHub
GitHub akzeptiert beim Push kein Passwort mehr, sondern ein **Personal Access Token** (GitHub → Settings → Developer settings → Tokens) oder SSH. Am einfachsten ist die GitHub CLI:
```bash
brew install gh
gh auth login
```

## Typischer Ablauf für ein erstes Projekt
```bash
git init
git add .
git commit -m "Erster Commit"
git branch -M main
git remote add origin https://github.com/NAME/REPO.git
git push -u origin main
```
Das Repo muss vorher auf GitHub angelegt sein (grüner Button **New**).
