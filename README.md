# ⛏️ Scatly — Flujo de Análisis de Riesgo y Causas (Next.js)

Aplicación web interactiva desarrollada con Next.js para gestionar proyectos y ejecutar un flujo guiado de análisis sistemático de causas en 7 pasos. Permite crear, visualizar y actualizar información clave de incidentes, personas, causas inmediatas y básicas, y necesidades de acción correctiva.

---

## 🧭 Módulos / Rutas principales

- `/` — Listado de proyectos del usuario y acceso a crear uno nuevo.
- `/login` — Inicio de sesión y manejo de sesión con JWT.
- `/register` — Registro de usuarios.
- `/new/[id]` — Creación/edición de proyecto con flujo de 7 pasos.
- `/project/[id]` — Detalle del proyecto con campos y comentarios estructurados.
- `API /api/*` — Endpoints de autenticación, proyectos, campos, salud e inicialización.

---

## 🌟 Características

- Flujo de formulario en 7 pasos con componentes modulares.
- Validación y manejo de estado con `React Hook Form` y `Zod`.
- Autenticación con JWT y protección de rutas mediante middleware.
- Campos jerárquicos por código (`fields` y `project_fields`).
- UI responsiva con Tailwind CSS y componentes reutilizables.
- Animaciones suaves con Framer Motion.

---

## 🖼️ Vista previa

*(Agrega aquí una imagen o GIF de la app cuando tengas una build estable)*
```md
![Demo](./public/imgs/website.webp)
```

---

## 🚀 Demo en Vivo

💡 Próximamente (despliegue en Vercel en progreso).

---

## 🛠️ Tecnologías utilizadas

- **Next.js 14** — App Router y APIs en `app/api`.
- **React 18** — Componentes y estado.
- **Tailwind CSS 3** — Estilos utilitarios y diseño responsivo.
- **Framer Motion** — Animaciones.
- **Zustand** — Estado global ligero.
- **React Hook Form + Zod** — Formularios y validación.
- **PostgreSQL (`pg`)** — Persistencia de proyectos y campos.
- **JWT (`jsonwebtoken`, `jose`)** — Autenticación y protección de rutas.

---

## 📁 Estructura general del proyecto

```bash
risk-flow-app/
├── app/
│   ├── (main)/            # Grupo principal: Home y flujos
│   │   ├── page.tsx       # Listado de proyectos
│   │   ├── new/[id]/      # Flujo de 7 pasos para proyecto
│   │   └── project/[id]/  # Detalle de proyecto
│   ├── api/               # Endpoints (auth, projects, fields, health, init)
│   ├── login/             # Página de inicio de sesión
│   └── register/          # Página de registro
├── components/            # UI y módulos (form wizard, detail, layout)
├── lib/                   # Base de datos, servicios y utilidades
├── hooks/                 # Hooks (auth, form, navegación)
├── store/                 # Estado global (Zustand)
├── types/                 # Tipos de TypeScript
├── public/                # Imágenes y assets estáticos
├── package.json
└── README.md
```

---

## ⚙️ Instalación y uso

Requisitos: `Node.js >= 18` y `npm`.

1. Instalar dependencias:
   ```bash
   npm install
   ```
2. Iniciar servidor de desarrollo:
   ```bash
   npm run dev
   ```
   Abre `http://localhost:3000` en tu navegador.
3. Construir para producción:
   ```bash
   npm run build
   ```
4. Iniciar build de producción:
   ```bash
   npm start
   ```
5. Linter (opcional):
   ```bash
   npm run lint
   ```

Variables de entorno imprescindibles:
- `POSTGRES_URL` — Cadena de conexión a PostgreSQL.
- `JWT_SECRET` — Clave secreta para firmar/verificar tokens.

---

## 🎯 Funcionalidades clave

- Creación de proyectos con flujo guiado de 7 pasos:
  - Datos del proyecto e investigador/accidentado.
  - Evaluación potencial de pérdida y tipo de contacto.
  - Causas inmediatas y básicas.
  - Necesidades de acción correctiva (NAC).
- Gestión de proyectos: listar, ver detalle, crear y actualizar.
- Campos jerárquicos por código con comentarios asociados.
- Protección de endpoints y páginas mediante middleware JWT.
- Interfaz moderna y responsiva con componentes reutilizables.

---

## ⚠️ Consideraciones y límites actuales

- Requiere configurar `POSTGRES_URL` y `JWT_SECRET` antes de usar endpoints protegidos.
- Las secciones y campos pueden variar según la configuración de `fields`.
- La autenticación se maneja en el cliente con token en `localStorage` y verificación en middleware/handlers.

---

## 🔧 Posibles mejoras

- [ ] Validar rangos y reglas adicionales en cada paso (Zod).
- [ ] Exportar resultados a CSV/PDF desde el detalle del proyecto.
- [ ] Búsqueda y filtros en listado de proyectos.
- [ ] Internacionalización (ES/EN).
- [ ] Tests unitarios e integración.
- [ ] Caching selectivo para lecturas frecuentes.
- [ ] Documentar supuestos y referencias del modelo de análisis.
- Consulta también: `FRONTEND_IMPROVEMENTS.md` y `BACKEND_IMPROVEMENTS.md`.

---

## 💡 Aprendizajes

- Arquitectura con App Router y middleware de Next.js.
- Manejo de formularios complejos y estado modular.
- Diseño de modelos jerárquicos para campos y comentarios.
- Integración de PostgreSQL con pool de conexiones y servicios.

---

## 📄 Licencia

Este proyecto utiliza la licencia **MIT**. Consulta el archivo `LICENSE` para detalles.

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas:

1. Fork del repositorio.
2. Crea una rama: `git checkout -b feature/mi-mejora`.
3. Commit: `git commit -m "feat: añade mejora X"`.
4. Push: `git push origin feature/mi-mejora`.
5. Abre un Pull Request.

---

## 👨‍💻 Autor

**Charles Castillo (FROSTYLAN)**

- 🌐 `https://github.com/FROSTYLAN`
- 💼 `https://linkedin.com/in/charles-castillo-772968234`

---

⭐ Si te resultó útil, considera dar una estrella al repositorio.
🚀 ¡Gestiona proyectos y analiza causas con un flujo claro y confiable!