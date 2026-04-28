<div align="center">

<img src="public/Images/Logo.png" alt="XestorDeTarefas" width="140">

# XestorDeTarefas

### 🧭 A túa vida organizada: tarefas, proxectos, notas e calendario nun só sitio.

</div>

---

## 📖 Descrición

Organiza as túas tarefas, proxectos e notas, e velos no calendario mes a mes ou día a día
— no escritorio ou no móbil, sincronizado entre dispositivos coa túa propia base de datos
Firebase e detrás do teu inicio de sesión. En galego, castelán ou inglés, con tema claro
ou escuro. Sen subscrición, sen anuncios, sen depender dun servizo alleo.

![XestorDeTarefas Screenshot](public/Images/Interfaz.png)

**Repositorios**

- 🌐 Web (este repo): [IPardelo/xestor-de-tarefas-web](https://github.com/IPardelo/xestor-de-tarefas-web)
- 🤖 Android: [IPardelo/xestor-de-tarefas-app](https://github.com/IPardelo/xestor-de-tarefas-app)

---

## 🏷️ Badges

[![Versión](https://img.shields.io/badge/versión-2.1.0-6366f1?style=flat-square)](https://github.com/IPardelo/xestor-de-tarefas-web/releases)
[![Licenza](https://img.shields.io/badge/licenza-MIT-22c55e?style=flat-square)](LICENSE)
[![Node](https://img.shields.io/badge/node-%3E%3D18-339933?style=flat-square&logo=node.js&logoColor=white)](https://nodejs.org)
[![Último commit](https://img.shields.io/github/last-commit/IPardelo/xestor-de-tarefas-web?style=flat-square)](https://github.com/IPardelo/xestor-de-tarefas-web/commits)
[![Android](https://img.shields.io/badge/app%20Android-repo-3ddc84?style=flat-square&logo=android&logoColor=white)](https://github.com/IPardelo/xestor-de-tarefas-app)

![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Redux Toolkit](https://img.shields.io/badge/Redux%20Toolkit-2.6-764ABC?style=flat-square&logo=redux&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-6-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![MUI](https://img.shields.io/badge/MUI-6-007FFF?style=flat-square&logo=mui&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer%20Motion-12-0055FF?style=flat-square&logo=framer&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-Firestore-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![ESLint](https://img.shields.io/badge/ESLint-9-4B32C3?style=flat-square&logo=eslint&logoColor=white)
![KeePass](https://img.shields.io/badge/KDBX-kdbxweb-6ABF4B?style=flat-square&logo=keepassxc&logoColor=white)
![i18n](https://img.shields.io/badge/i18n-gl%20%7C%20es%20%7C%20en-8b5cf6?style=flat-square)

---

## 🤔 Por que

As aplicacións de tarefas comerciais pídenche unha conta nun servidor alleo, gardan os teus
datos onde non ves, e tarde ou cedo poñen detrás dun pago o que antes era gratis.
XestorDeTarefas nace da idea contraria: **a app é túa e os datos tamén**.

- 🔐 Os datos viven no teu propio proxecto de Firebase, non nun servizo de terceiros.
- 🧩 Todo nun só sitio: tarefas, proxectos con cliente, notas e calendario, sen saltar entre apps.
- 🖥️📱 O mesmo estado no ordenador e no móbil, sincronizado ao instante.
- 🌍 Pensada en galego dende o primeiro día (e tamén en castelán e inglés).
- 🆓 Sen subscrición, sen anuncios, sen límites artificiais. Código aberto con licenza MIT.

---

## ✨ Funcionalidades

- ✅ Xestión de tarefas: crear, editar, eliminar, completar, buscar, filtrar e ordenar.
- 📝 Módulo de notas: notas de texto e notas tipo lista/checklist con cor personalizada.
- 📌 Ordenación de notas por fixación e última actualización.
- 👥 Xestión de usuarios con rol administrador.
- 📁 Xestión de proxectos con datos de cliente.
- 📅 Vista de calendario anual/mensual/diaria con sincronización con Google Calendar.
- 🔥 Persistencia e sincronización con Firebase Firestore (estado compartido).
- 🔑 Lectura de credenciais KDBX (KeePass) dende Proxectos, restrinxida a admin.
- 🌗 Tema claro/escuro e internacionalización `gl` / `es` / `en`.

---

## ⚙️ Configuración

### Requisitos

- Node.js 18+ (recomendado 20+)
- npm
- Windows, Linux ou macOS

### 1) Clonar e instalar

```bash
git clone https://github.com/IPardelo/xestor-de-tarefas-web.git
cd xestor-de-tarefas-web
npm install
```

### 2) Configurar Firebase

Crea un proxecto en [Firebase](https://console.firebase.google.com), activa **Firestore**,
copia `.env.example` a `.env` e enche os valores do teu proxecto:

```bash
VITE_FIREBASE_API_KEY=
VITE_FIREBASE_AUTH_DOMAIN=
VITE_FIREBASE_PROJECT_ID=
VITE_FIREBASE_STORAGE_BUCKET=
VITE_FIREBASE_MESSAGING_SENDER_ID=
VITE_FIREBASE_APP_ID=
VITE_FIREBASE_SYNC_DOC=tarefas-shared/default
```

> `VITE_FIREBASE_SYNC_DOC` é o documento de Firestore que comparte o estado entre dispositivos.

### 3) Arrancar

```bash
npm run dev     # servidor de desenvolvemento -> http://localhost:5173
npm run build   # build de produción
npm run preview # previsualización da build
npm run lint    # lint do código
```

En Windows tamén podes usar `iniciar-app.bat`, que abre o servidor Vite nunha consola nova
e lanza o navegador automaticamente.

---

## 🧠 Como funciona

```text
src/
  App/                # Store e persistencia
  Components/         # UI por áreas (Tasks, Projects, Notes, Layout, Options...)
  Features/           # Slices Redux (Tasks, Users, Projects, Notes, Theme, Language)
  i18n/               # Traducións gl / es / en
vite.config.js        # Configuración Vite + endpoint local de KDBX
```

- 🧱 **Estado central con Redux Toolkit.** Cada área (tarefas, notas, proxectos, usuarios,
  tema, idioma) é un *slice* independente; a UI só le e despacha accións.
- 🔄 **Sincronización con Firestore.** O estado persístese no documento indicado en
  `VITE_FIREBASE_SYNC_DOC`; calquera cambio propágase ás demais sesións abertas, así que o
  móbil e o ordenador ven o mesmo en tempo real.
- 🔐 **Sesión e roles.** O acceso vai detrás de inicio de sesión; o rol admin desbloquea a
  xestión de usuarios e a lectura de bases KDBX.
- 🗝️ **KDBX en local.** A lectura de bases KeePass (con Argon2) resólvese nun endpoint local
  definido en `vite.config.js`, polo que require un entorno que execute Node.js.
- 📅 **Calendario.** As tarefas con data amósanse na vista anual, mensual e diaria, con
  sincronización opcional co teu Google Calendar.
- ⚛️ **Interface.** React 19 + Tailwind 4 + MUI, con animacións de Framer Motion e tema
  claro/escuro persistente.

---

## 👤 Autor

**[Ismael Castiñeira](https://ipardelo.es)** — [@IPardelo](https://github.com/IPardelo)

Licenza MIT. Ver [`LICENSE`](LICENSE).

```bash
VIVA GHALISIA E A COSTA DA MORTE! 💀
```
