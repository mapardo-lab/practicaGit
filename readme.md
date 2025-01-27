### 11)

Se trata de pasar al anterior COMMIT, por eso el uso de `HEAD~1`, eliminando todos los cambios que había realizado y que tenía en el 'working area', entonces se usa el modificador `--hard`.

```         
git reset --hard HEAD~1
```

### 12)

Mediante el comando git reflog buscamos el id del commit que nos interesa y mediante git reset `--hard <id>` nos movemos a ese commit

```         
git reflog 
git reset --hard 69d813e
```

### 13)

No aparece ningún conflicto. La rama `styled` se encuentra en commit hijo del commit en el que se encuentra rama `master`, así que el comando no cambia nada

```         
git merge master
```

### 19)

Aparecen conflictos ya que el fichero `git-nuestro.md` tiene versiones diferentes en los commits de las dos ramas que se han juntado. Se trata de un merge no "fast-forward".

```         
git checkout styled 
git merge htmlify
```

### 21)

No aparece ningún conflicto ya que se trata de un "merge fast-forward".

```         
git merge styled
```

### 25)

Se declara alias `graph` en modo global que luego se utiliza para sacar diagrama

```         
git config --global alias.graph "log --graph --pretty=oneline --decorate" 
git graph
```

### 26)

Podría aplicarse un "merge fast-forward" mediante el comando `git merge title` ya que no se ha hecho ningún "commit" adicional en la rama `master`.

```         
git merge --no-ff title
```

### 27)

```         
git reset HEAD~1
```

### 28)

```         
git checkout -- git-nuestro.md
```

### 29)

```         
git branch -D title
```

### 30)

Se mira el identificador del "commit" en el que estaba la rama `title`.

```         
git reflog
```

Se cambia puntero `HEAD` a ese "commit".

```         
git ckeckout 39fdecf 
```

Se crea rama `title` en ese "commit".

```         
git branch title
```

Se cambia a rama `master`.

```         
git checkout master
```

Se realiza "merge fast-forward" desde master absorbiendo rama `title`.

```         
git merge title 
```

### 32)

Se mira el identificador del "commit" inicial.

```         
git reflog 
```

Se cambia puntero `HEAD` y rama `master` a "commit" inicial.

```         
git reset --hard 698e779 
```

### 33)

Se mira el identificador del "commit" inicial.

```         
git reflog 
```

Se cambia puntero `HEAD` y rama `master` a "commit" inicial.

```         
git reset --hard 39fdecf 
```
