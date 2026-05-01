# Git config

## Configuración inicial

```bash
git config --global user.email "cgalvisleon@gmail.com"
git config --global user.name "Cesar Galvis Leon"
git config --global init.defaultBranch main
```

Config local (Celsia):
```bash
git config --local user.email "cgalvisl@celsiainternet.com"
git config --local user.name "Cesar Galvis Leon"
```

---

## Setup de aliases

Ejecutar una sola vez para registrar todos los aliases:

```bash
# Vista
git config --global alias.l "log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
git config --global alias.s "status -s -b"
git config --global alias.v "! git describe --tags --abbrev=0"
git config --global alias.b "! git describe --tags --abbrev=1"

# Ramas
git config --global alias.new "! git checkout -b $1"
git config --global alias.set "! git checkout $1"
git config --global alias.del "! git branch -D $1"
git config --global alias.rn "! git branch -m $1"
git config --global alias.main "! git branch -M main"
git config --global alias.lb "! git branch -v"
git config --global alias.lba "! git branch -a"
git config --global alias.lbr "! git branch -r"
git config --global alias.pb "! git push --set-upstream origin $1"
git config --global alias.odel "! git push origin --delete $1 $2"
git config --global alias.orn "! git push origin --delete $1; git push origin $2"
git config --global alias.set-head "! git remote set-head origin"

# Pull
git config --global alias.get "! git pull origin $1"
git config --global alias.getall "! git pull origin"
git config --global alias.bring "! git pull origin $1"

# Commit + push (origin)
git config --global alias.prepare "! git add .; git commit -m 'Prepare'"
git config --global alias.initial "! git add .; git commit -m 'Initial'; git push -u origin --all"
git config --global alias.update "! git add .; git commit -m 'Update'; git push -u origin $1"
git config --global alias.upd "! git add .; git commit -m 'Update'; git push -u origin $1"
git config --global alias.backup "! git add .; git commit -m 'Backup'; git push -u origin $1"
git config --global alias.feat '! feat() { git add . && git commit -m "feat:$1" && git push -u origin; }; feat'
git config --global alias.review '! review() { git add . && git commit -m "review:$1" && git push -u origin; }; review'
git config --global alias.fix '! fix() { git add . && git commit -m "fix:$1" && git push -u origin; }; fix'
git config --global alias.bug '! bug() { git add . && git commit -m "bug:$1" && git push -u origin; }; bug'
git config --global alias.deploy "! git add .; git commit -m 'Deploy'; git push -u origin $1"
git config --global alias.down "! git add .; git commit -m 'Down'; git push -u origin $1"
git config --global alias.rollback "! git add .; git commit -m 'Rollback'; git push -u origin $1"
git config --global alias.merge "! git add .; git commit -m 'Merge'; git push -u origin $1"

# Commit + push (josephine)
git config --global alias.jbackup "! git add .; git commit -m 'Backup'; git push -u josephine $1"
git config --global alias.jreview "! git add .; git commit -m 'Review'; git push -u josephine $1"
git config --global alias.jmerge "! git add .; git commit -m 'Merge'; git push -u josephine $1"
git config --global alias.jdeploy "! git add .; git commit -m 'Deploy'; git push -u josephine $1"
git config --global alias.jfix "! git add .; git commit -m 'Fixing'; git push -u josephine $1"
git config --global alias.jbring "! git pull josephine $1"

# Reset
git config --global alias.rhs "git reset HEAD^ --soft"
git config --global alias.rhh "git reset HEAD^ --hard"
git config --global alias.clean "git rm -r --cached ."
git config --global alias.chout "! git checkout -- $1"

# Tags
git config --global alias.tag "! git tag $1"
git config --global alias.tags "! git push -u origin --tags"
git config --global alias.tago "! git ls-remote --tags origin"
git config --global alias.tagdel "! git tag -d $1"
git config --global alias.tagodel "! git push origin --delete $1"
```

---

## Referencia de aliases

### Vista

| Alias | Uso          | Descripción          |
|-------|--------------|----------------------|
| `l`   | `git l`      | Log gráfico          |
| `s`   | `git s`      | Estado corto         |
| `v`   | `git v`      | Última versión       |
| `b`   | `git b`      | Versión abreviada    |

### Ramas

| Alias      | Uso                       | Descripción          |
|------------|---------------------------|----------------------|
| `new`      | `git new <rama>`          | Crear rama           |
| `set`      | `git set <rama>`          | Cambiar rama         |
| `del`      | `git del <rama>`          | Borrar rama local    |
| `rn`       | `git rn <rama>`           | Renombrar rama       |
| `main`     | `git main`                | Renombrar a main     |
| `lb`       | `git lb`                  | Listar ramas         |
| `lba`      | `git lba`                 | Listar todas         |
| `lbr`      | `git lbr`                 | Listar remotas       |
| `pb`       | `git pb <rama>`           | Publicar rama        |
| `odel`     | `git odel <rama>`         | Borrar rama origin   |
| `orn`      | `git orn <vieja> <nueva>` | Renombrar en origin  |
| `set-head` | `git set-head`            | Actualizar HEAD      |

### Pull

| Alias    | Uso                  | Descripción          |
|----------|----------------------|----------------------|
| `get`    | `git get <rama>`     | Pull desde origin    |
| `getall` | `git getall`         | Pull todo origin     |
| `bring`  | `git bring <rama>`   | Pull rama origin     |

### Commit + Push — origin

| Alias      | Uso                      | Descripción          |
|------------|--------------------------|----------------------|
| `prepare`  | `git prepare`            | Commit sin push      |
| `initial`  | `git initial`            | Commit inicial       |
| `update`   | `git update <rama>`      | Commit update        |
| `upd`      | `git upd <rama>`         | Commit update        |
| `backup`   | `git backup <rama>`      | Commit backup        |
| `feat`     | `git feat "<msg>"`       | Commit feat          |
| `review`   | `git review "<msg>"`     | Commit review        |
| `fix`      | `git fix "<msg>"`        | Commit fix           |
| `bug`      | `git bug "<msg>"`        | Commit bug           |
| `deploy`   | `git deploy <rama>`      | Commit deploy        |
| `down`     | `git down <rama>`        | Commit down          |
| `rollback` | `git rollback <rama>`    | Commit rollback      |
| `merge`    | `git merge <rama>`       | Commit merge         |

### Commit + Push — josephine

| Alias     | Uso                     | Descripción          |
|-----------|-------------------------|----------------------|
| `jbackup` | `git jbackup <rama>`    | Backup a josephine   |
| `jreview` | `git jreview <rama>`    | Review a josephine   |
| `jmerge`  | `git jmerge <rama>`     | Merge a josephine    |
| `jdeploy` | `git jdeploy <rama>`    | Deploy a josephine   |
| `jfix`    | `git jfix <rama>`       | Fix a josephine      |
| `jbring`  | `git jbring <rama>`     | Pull de josephine    |

### Reset

| Alias   | Uso                   | Descripción          |
|---------|-----------------------|----------------------|
| `rhs`   | `git rhs`             | Reset soft HEAD^     |
| `rhh`   | `git rhh`             | Reset hard HEAD^     |
| `clean` | `git clean`           | Limpiar caché        |
| `chout` | `git chout <archivo>` | Descartar cambios    |

### Tags

| Alias      | Uso                    | Descripción          |
|------------|------------------------|----------------------|
| `tag`      | `git tag <nombre>`     | Crear tag local      |
| `tags`     | `git tags`             | Publicar tags        |
| `tago`     | `git tago`             | Listar tags origin   |
| `tagdel`   | `git tagdel <nombre>`  | Borrar tag local     |
| `tagodel`  | `git tagodel <nombre>` | Borrar tag origin    |

---

## Técnicas

### Merge y conflictos

```bash
git merge <rama>
git merge -X theirs <rama>     # Acepta todos los cambios de <rama>
git rebase origin/<rama>

git checkout --theirs .        # Acepta cambios de origin
git checkout --ours .          # Acepta cambios locales
git checkout --theirs <file>
git checkout --ours <file>

git rhs   # Reset soft: deshace commit, conserva cambios
git rhh   # Reset hard: deshace commit y cambios

git reset <id> --soft
git reset <id> --hard
```

### Descartar cambios en un archivo

```bash
git checkout -- <file>
git checkout origin/<rama> -- <file>
```

### Gitignore — quitar archivos ya rastreados

```bash
git ls-files -ci --exclude-standard    # Ver archivos ignorados pero rastreados
git rm --cached <file>
git rm --cached -r <directorio>
git check-ignore -v <file>             # Verificar regla que lo ignora
```

### Historial — buscar y eliminar commits

```bash
# Buscar texto en historial
git log --all --grep="texto"
git grep "texto" $(git rev-list --all)

# Eliminar commits por mensaje (requiere: brew install git-filter-repo)
git filter-repo --force --commit-callback '
if b"texto" in commit.message:
    commit.drop()
'
```

### Remoto — cambiar URL

```bash
git remote set-url origin <nueva-url>
git remote set-url origin git@github-celsia:CelsiaInternet/<repo>.git
```

---

## SSH — múltiples cuentas

```bash
ssh-keygen -t ed25519 -C "cgalvisleon@gmail.com" -f ~/.ssh/id_ed25519_personal
eval "$(ssh-agent -s)"
ssh -T git@github-cgalvisleon

# Agregar remote con host alias
git remote add origin git@github-cgalvisleon:<repo>.git
git remote add origin git@github-celsia:<repo>.git
```

Archivo `~/.ssh/config`:
```
Host github-cgalvisleon
  HostName github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519_personal

Host github-celsia
  HostName github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519_celsia
```
