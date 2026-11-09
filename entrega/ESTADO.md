# Estado de la entrega

> **Claude:** este es el marcador. Léelo al empezar cada conversación. Al terminar un paso y **comprobarlo**, marca su casilla `[x]`, pon la fecha y apunta en «Notas» lo útil. No marques nada que no hayas comprobado.

## Pasos

- [x] **1. Preparar el ordenador** — git, Node.js 22, pnpm y Claude Code instalados → `pasos/01-preparar-el-ordenador.md` — ✅ 9-nov-2026
- [x] **2. Quedarte el código** — tu copia (Fork) en tu GitHub, descargada y compilando en local → `pasos/02-quedarte-el-codigo.md` — ✅ 9-nov-2026
- [x] **3. Publicar la web** — desplegada en tu Vercel (o Railway) con URL provisional funcionando → `pasos/03-publicar-en-vercel-o-railway.md` — ✅ 9-nov-2026
- [ ] **4. Conectar el dominio** — `clinicagirones.es` y `www` apuntan a tu despliegue, con candado (HTTPS), y el correo sigue funcionando → `pasos/04-conectar-el-dominio.md`
- [ ] **5. Formulario de contacto** — los mensajes de `/contacto` llegan de verdad al correo → `pasos/05-formulario-de-contacto.md`
- [ ] **6. Cierre con Vicente** — Vicente ha borrado su copia en Railway; la web solo vive en tu cuenta → `pasos/06-cierre-con-vicente.md`
- [ ] **7. Ya sabes hacer cambios** — has hecho al menos un cambio real con Claude y se ha publicado solo → `pasos/07-cambios-del-dia-a-dia.md`

## Situación de partida (9-nov-2026, la escribió Vicente)

- Código en GitHub: `ViBaTo/clinica-girones` (rama `main`). Compila limpio desde cero (`pnpm install && pnpm build` comprobado).
- Despliegue actual: Railway de Vicente → sirve `www.clinicagirones.es` (CNAME a `0nwdawk1.up.railway.app`).
- `clinicagirones.es` (raíz, sin www) → todavía apunta al hosting antiguo de Ramnet (IP `178.18.242.153`, WordPress).
- Correo: `MX 10 mail.clinicagirones.es` → `178.18.242.153` (Ramnet). SPF: `v=spf1 a mx include:ramnet.com.es ~all`. **No tocar.**
- DNS del dominio gestionado en el proveedor con servidores `ns.gestiondecuenta.com` / `ns2` / `ns3` / `ns4`.
- Formulario de contacto: **simulado, no envía**.
- Variables de entorno: ninguna.

## Notas (Claude: apunta aquí lo que vaya saliendo)

- Paso 1: git 2.56, Node 24.19, pnpm 10.15.1 (instalado con npm -g). Claude Code se usa desde la app de escritorio.
- Usuario de GitHub del nuevo dueño: ernestocergir-lab (git firma como ernestocergir-lab <ernestocergir@gmail.com>, config local del repo)
- Repositorio nuevo (URL): https://github.com/ernestocergir-lab/clinica-girones (fork; carpeta local conectada, pnpm build OK con 12 páginas)
- Plataforma elegida (Vercel / Railway): Vercel (elegido 9-nov-2026)
- URL provisional del despliegue: https://clinica-girones.vercel.app (11 rutas + foto equipo → 200, comprobado 9-nov-2026)
- Fecha de cambio de DNS:
- Servicio de envío del formulario:
- Foto DNS antes del cambio (9-nov-2026, vía 8.8.8.8) — para volver atrás:
  - A `@` → 178.18.242.153 · CNAME `www` → 0nwdawk1.up.railway.app
  - ⛔ MX `@` → 10 mail.clinicagirones.es · A `mail` → 178.18.242.153 · TXT `@` → v=spf1 a mx include:ramnet.com.es ~all
  - NS: ns / ns2 / ns3 / ns4.gestiondecuenta.com
- Valores que pide Vercel (9-nov-2026): A `@` → 216.198.79.1 · CNAME `www` → 1d3723ba5617db42.vercel-dns-017.com. Principal: www (clinicagirones.es → 308 → www) ⇒ tras el DNS, cambiar `siteUrl` a https://www.clinicagirones.es.
