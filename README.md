<p align="center"><img src="./img/claude.webp" width="600"   alt=" " /></p>
<h1 align="center"> Claude AI </h1> 
<h4 align="right">Jul 26</h4>

<p>
  <img src="https://img.shields.io/badge/OS-Linux%20GNU-yellowgreen">
  <img src="https://img.shields.io/badge/OS-Windows%2011-blue">
</p>

<br>

# Table of contents
- [Table of contents](#table-of-contents)
- [Claude desde terminal:](#claude-desde-terminal)
  - [Install](#install)
  - [Start](#start)
- [Tools](#tools)
- [Skill](#skill)
  - [Skill (Habilidad)](#skill-habilidad)
  - [MCP (Model Context Protocol)](#mcp-model-context-protocol)

<br>

<p align="center"><img src="./img/claude-code.webp" width="600"   alt=" " /></p>

# Claude desde terminal:
## Install
```PowerShell
irm https://claude.ai/install.ps1 | iex
```
Solo falta agregar esa carpeta a tu PATH. Tienes dos opciones:
```PowerShell
$currentPath = [Environment]::GetEnvironmentVariable('PATH', 'User')
[Environment]::SetEnvironmentVariable('PATH', "$currentPath;$env:USERPROFILE\.local\bin", 'User')
```
> :warning: **Warning:** Después cierra PowerShell por completo y abre una ventana nueva (esto es importante, el cambio no aplica a la ventana actual). 

## Start
Escribe ```claude```
* ```/login``` para autenticarte
* ```Esc``` interrumpe a Claude si está trabajando
* ```/help``` muestra los comandos disponibles
* ```/skills``` ver todos los Skills disponibles
* ```/plugin list``` ver los plugins instalados
* ```exit``` o ```Ctrl+D``` para salir

> :memo: **Note:** Deberia correr tambien desde CMD, PowerShell 
> 
> :memo: **Note:** Carpeta de configuracion de claude ```cd ~/.claude/``` o ```%USERPROFILE%\.claude\skills\```


<br>

# Tools

Claude-StatusBar. https://github.com/afsh4ck/Claude-Status-Bar

<br>

# Skill
Inicialmente es necesario crear la carpeta
```PowerShell
mkdir -p ~/.claude/skills
```
```prompt-master``` es una skill que te ayuda a redactar mejores prompts para cualquier herramienta de IA (Claude, ChatGPT, Midjourney, Cursor, etc.), en lugar de que tú lo hagas a mano por ensayo y error.
```PowerShell
git clone https://github.com/nidhinjs/prompt-master.git ~/.claude/skills/prompt-master
```
***Usage:*** I need a prompt for Claude Code to build...

<br>

```grill-me``` (Interrogame) es un Skill para Claude Code cuyo objetivo es evitar que el modelo empiece a programar haciendo suposiciones. En lugar de generar código inmediatamente, el skill te entrevista de forma sistemática hasta entender completamente el problema.
Agregar el Marketplace:
```bash
# Dentro de Claude Code ejecuta:
/plugin marketplace add alirezarezvani/claude-skills
/plugin install grill-me@claude-code-skills
/plugin list # para verificar que esta instalado
```
***Usage:*** Quiero hacer un sistema... Grill me on this architecture... Grill me before implementing this project.


<br>

<p align="center"><img src="./img/anatomia.jpg" width="600"   alt=" " /></p>

<br>

## Skill (Habilidad)

Una Skill es una capacidad específica que un sistema AI puede ejecutar para resolver una tarea concreta.

Ejemplos:

* "Convertir un PDF a texto"
* "Consultar una base de datos"
* "Enviar un correo"
* "Controlar una impresora 3D"
* "Generar un reporte Excel"

Una Skill normalmente tiene:

* Nombre
* Descripción de lo que hace
* Parámetros de entrada
* Resultado esperado
* Reglas de uso

> :bulb: **Tip:** Un agente AI puede decidir cuándo usar esa Skill.

## MCP (Model Context Protocol)

MCP = Model Context Protocol

Es un estándar creado para conectar modelos AI con herramientas, datos y sistemas externos de forma estructurada.

La idea es:
```
Modelo AI
    |
    |
    MCP
    |
-----------------
|       |       |
Base   API    Archivo
datos          sistema
```
En vez de programar una integración diferente para cada AI, MCP define una forma común.

Ejemplos de recursos conectables:

* Bases de datos
* GitHub
* Sistemas internos
* APIs
* Archivos locales
* Herramientas empresariales

Ejemplo:
Un asistente AI recibe:
"Busca los errores del proyecto y crea un reporte"
El modelo usa MCP para:

1. Leer repositorio
2. Revisar logs
3. Crear documento

<br>

<p align="center"><img src="./img/ecosistema.gif" width="600"   alt=" " /></p>



<br>

---

<div>
  <p>
    <img  align="top" width="42" style="padding:0px 0px 0px 0px;" src="./img/carjavi.png"/> Copyright &nbsp;&copy; 2023 Instinto Digital <a href="https://carjavi.github.io/" title="carjavi.github">carjavi</a>
  </p>
</div>

<p align="center">
    <a href="https://instintodigital.net/" target="_blank"><img src="./img/developer.png" height="100" alt="www.instintodigital.net"></a>
</p>




