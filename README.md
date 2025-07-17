# Roblox‑Rojo‑Template

Plantilla lista para clonar y empezar juegos de Roblox usando **Rojo 7**, **Wally** y **Rokit**.

---

## Requisitos

- **Git** 2.30 o superior  
- **Roblox Studio** + plugin “Rojo”  
- **Rokit** y **Wally** se descargan solos con el primer comando

> Funciona en Windows 11, macOS o Linux; sólo necesitas Git.

---

## Primer uso (3 pasos)

```bash
git clone https://github.com/TuUsuario/roblox-rojo-template.git MiJuego
cd MiJuego
rokit install     # descarga Rojo 7.5.1 y Wally 0.3.2 (según rokit.toml)
wally install     # instala dependencias declaradas en wally.toml
rojo serve        # abre sincronía en localhost:34872
```
Nota para principiantes
 • TuUsuario = tu nombre de usuario en GitHub.
 • MiJuego = la carpeta que Git creará en tu PC; cámbiala por el nombre que quieras para tu proyecto local.
 Ejemplo real:
 git clone https://github.com/CrafterPunk/roblox-rojo-template.git Plataforma3D

 
1. Abre Roblox Studio
2. Pestaña Plugins → Rojo → Connect
3. Tu lugar aparece con el código de src/ y las dependencias de Packages/.

---

Estructura de carpetas
```text
src/
  shared/   -- código accesible por cliente y servidor
  server/   -- sólo servidor
  client/   -- sólo cliente

Packages/   -- módulos instalados con Wally
default.project.json  -- mapa Rojo
rokit.toml  -- versiones fijadas de herramientas
wally.toml  -- dependencias del juego
```
Comandos útiles

# Generar un .rbxl listo para subir
```bash
rojo build default.project.json -o build/Juego.rbxlx
```

# Crear sourcemap y habilitar autocompletado de tipos
```bash
rojo sourcemap default.project.json -o sourcemap.json
wally-package-types -s sourcemap.json Packages/
```


Actualizar herramientas

# Ejemplo: pasar a Rojo 7.6 (cuando exista)
```bash
rokit add rojo@7.6.0  (ejemplo)
rokit install
git commit -m "Bump Rojo 7.6"
```

¡Listo! Clona, instala, conecta y programa.



