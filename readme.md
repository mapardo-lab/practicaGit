### 11)

Se trata de pasar al anterior 'commit', por eso el uso de `HEAD~1`. Para eliminar todos los cambios que se habían realizado y que se encontraban en el 'working area', se usa el modificador `--hard`.

```         
git reset --hard HEAD~1
```

### 12)

Mediante el comando `git reflog` se busca el identificador del 'commit' que nos interesa. Mediante la orden `git reset --hard <id>` el puntero `HEAD` y rama `master` se mueve a ese 'commit'.

```         
git reflog 
git reset --hard 69d813e
```

### 13)

No aparece ningún conflicto. La rama `styled` (rama que absorbe) se encuentra en 'commit' hijo del 'commit' en el que se encuentra rama `master`. Al estar más actualizada la rama `styled` que la rama `master` el comando no produce ningún cambio.

```         
git merge master
```

### 19)

Aparecen conflictos ya que el fichero `git-nuestro.md` tiene versiones diferentes en los 'commits' de las ramas `styled` y `htmlify`. Se trata de un 'merge' no 'fast-forward'.

```         
git checkout styled 
git merge htmlify
```

### 21)

No aparece ningún conflicto ya que se trata de un 'merge fast-forward'.

```         
git merge styled
```

### 25)

Se declara alias `graph` en modo global que luego se utiliza para sacar el diagrama.

```         
git config --global alias.graph "log --graph --pretty=oneline --decorate" 
git graph
```

### 26)

Podría aplicarse un 'merge fast-forward' mediante el comando `git merge title` ya que no se ha hecho ningún 'commit' adicional en la rama `master`.

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

```         
git reflog
git ckeckout 39fdecf 
git branch title
git checkout master
git merge title 
```

### 32)

```         
git reflog 
git reset --hard 698e779 
```

### 33)

```         
git reflog 
git reset --hard 39fdecf 
```
