## Branching Strategy 
**GitHub Flow** 
```text 
main 
│ 
├── feature/product-recommendations 
├── feature/review-system 
├── bugfix/cart-error 
└── hotfix/payment-fix
```

## Naming Convention
1. feature/product-recommendations
2. feature/newsletter-signup
3. bugfix/cart-calculation
4. hotfix/login-failure

## Pull Requests
**Regeln:**
- Änderungen über Feature-Branches
- Pull Requests nach main
- Mindestens 1 Review
- Erfolgreiche CI-Pipeline erforderlich

## Commit messages
**Conventional Commits:**
- feat: add recommendation system
- fix: correct sqlite path
- docs: update README
- chore: update gitignore

## Release Prozess
1. Änderungen in main mergen
2. Version bestimmen (SemVer)
3. Tag erstellen
4. GitHub Release publizieren

**Beispiel:**
```text
git tag -a v1.0.0 -m "Initial release - TechStyle Modernization Baseline"

git push origin v1.0.0
```

## Merge Strategy
- Feature Branches werden per Pull Request in `main` gemergt.
- Standardmässig wird "Squash and Merge" verwendet.
- Merge Commits werden nur bei grösseren Releases verwendet.
- Rebase kann vor dem Erstellen eines Pull Requests verwendet werden, um die Historie sauber zu halten.

## Review Requirements
- Jede Änderung benötigt mindestens 1 Review.
- Der Autor eines Pull Requests darf nicht selbst approven.
- Alle CI-Checks müssen erfolgreich sein.

## Merge Conflicts
- Der Entwickler, der den Pull Request erstellt hat, löst Merge-Konflikte.
- Grössere Konflikte werden gemeinsam im Team besprochen.
- Die Lösung wird im Pull Request dokumentiert.