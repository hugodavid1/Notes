**Insérer un dossier dans le gitignore lorsqu'il est déjà sur le dépot distant :**

```bash
git rm -r --cached .idea
git commit -m "Remove .idea from version control"
git push origin nom_de_la_branche
```

[]: # (END)
