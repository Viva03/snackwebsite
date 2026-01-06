# STARTIN-V2.0 AI Coding Guidelines

## Architecture Overview
- **Full-stack job platform**: Frontend (React/TypeScript/Vite) for student/company dashboards; Backend (FastAPI/SQLAlchemy/PostgreSQL) planned but currently placeholder.
- **Frontend structure**: `src/pages/` for route components, `src/components/` for reusable UI, `src/services/api.ts` for backend integration (currently simulated).
- **Routing flow**: University select → Role selection → Auth → Dashboard (student: home/applied-jobs/profile; company: profile/post-job/applicants).
- **Data flow**: Forms use controlled components with `useState`; auth simulated via `localStorage` (e.g., `companyToken`); API calls placeholder in `connectToBackend()`.

## Key Patterns
- **Theming**: CSS variables in `App.css` (`--primary` for students/indigo, `--teal` for companies); apply via inline styles or classes.
- **Navigation**: Use `react-router-dom` Links; back buttons with `navigate(-1)` or specific paths; logout clears localStorage and redirects.
- **Forms**: Standard React forms with `handleChange` for inputs, `handleSubmit` for events; validation via HTML attributes.
- **Components**: Functional components with TypeScript; import CSS from `../App.css`; use `landing-container` class for centered cards.
- **API Integration**: Call `connectToBackend(actionType, data)` from `services/api.ts`; currently alerts/console logs; replace with real FastAPI endpoints.

## Developer Workflows
- **Frontend dev**: `npm run dev` (Vite HMR); `npm run build` (TypeScript + Vite); `npm run lint` (ESLint); `npm run preview`.
- **Backend setup** (planned): Install from `requirements.txt`; run `uvicorn main:app --reload` (create `main.py` with FastAPI app).
- **Testing**: Frontend none; backend `pytest` planned.
- **Debugging**: Console logs in forms; check localStorage for auth state.

## Conventions
- **File naming**: PascalCase for components (e.g., `CompanyLogin.tsx`); kebab-case for routes (e.g., `/company/login`).
- **Imports**: Group by React, then router, then local pages/components.
- **Styling**: Prefer CSS classes over inline; use `var(--color)` for themes; consistent spacing (40px margins, 20px gaps).
- **Auth checks**: Simulate with localStorage presence; redirect on logout.

## Integration Points
- **External deps**: React Router for SPA; Vite for build; FastAPI/SQLAlchemy for backend (placeholder).
- **Cross-component**: Navbars (`CompanyNavbar.tsx`) handle logout; pages import navbars conditionally.
- **Data persistence**: None yet; plan for PostgreSQL via SQLAlchemy models.

Reference: [App.tsx](frontend/src/App.tsx) for routing; [CompanyLogin.tsx](frontend/src/pages/CompanyLogin.tsx) for form pattern; [App.css](frontend/src/App.css) for styling.</content>
<parameter name="filePath">c:\Users\Viva\STARTIN-V2.0\.github\copilot-instructions.md