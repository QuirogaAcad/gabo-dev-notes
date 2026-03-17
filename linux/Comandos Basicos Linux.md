# 🐧 Comandos Básicos de Linux

---

## 📋 Referencia Rápida

| Comando | Descripción |
|---------|-------------|
| `ls` | Listar archivos y directorios |
| `cd` | Cambiar de directorio |
| `pwd` | Mostrar directorio actual |
| `mkdir` | Crear un directorio |
| `rm` | Eliminar archivos o directorios |
| `cp` | Copiar archivos o directorios |
| `mv` | Mover o renombrar archivos |

---

## 📂 Navegación

### `ls` — Listar contenido

```bash
ls          # lista básica
ls -la      # lista detallada con archivos ocultos
```

> `-l` formato largo · `-a` muestra ocultos · `-la` combina ambos

---

### `cd` — Cambiar directorio

```bash
cd nombre-carpeta   # entrar a una carpeta
cd ..               # subir un nivel
cd ~                # ir al directorio home
cd /                # ir a la raíz del sistema
```

---

### `pwd` — Directorio actual

```bash
pwd
# Ejemplo de salida: /home/usuario/documentos
```

---

## 🗂 Gestión de Archivos y Directorios

### `mkdir` — Crear directorio

```bash
mkdir nueva-carpeta               # crear una carpeta
mkdir -p carpeta/subcarpeta       # crear carpetas anidadas
```

---

### `rm` — Eliminar

```bash
rm archivo.txt        # eliminar un archivo
rm -r carpeta         # eliminar carpeta y su contenido
rm -rf carpeta        # forzar eliminación sin confirmación
```

> ⚠️ `rm -rf` es irreversible. Usarlo con cuidado.

---

### `cp` — Copiar

```bash
cp archivo.txt backup.txt         # copiar un archivo
cp -r carpeta1 carpeta2           # copiar carpeta completa
```

---

### `mv` — Mover o renombrar

```bash
mv archivo.txt carpeta/           # mover archivo a carpeta
mv nombre_viejo.txt nombre_nuevo.txt   # renombrar archivo
```

---

## 🔎 Conceptos para Investigar

- [ ] Permisos de archivos con `chmod` y `chown`
- [ ] Diferencia entre rutas absolutas y relativas
- [ ] Comandos `cat`, `less` y `more` para leer archivos
- [ ] Uso de wildcards (`*`, `?`) con estos comandos