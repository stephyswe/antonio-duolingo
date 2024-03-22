### Initial Setup

`npx create-next-app@14.1.1 antonio-duolingo-clone`
```
√ Would you like to use TypeScript? Yes
√ Would you like to use ESLint? Yes
√ Would you like to use Tailwind CSS? Yes
√ Would you like to use `src/` directory? No
√ Would you like to use App Router? (recommended) Yes
√ Would you like to customize the default import alias (@/\*)? No
```
`cd folder`

`npx shadcn-ui@latest init`
```
√ Which style would you like to use? » Default
√ Which color would you like to use as base color? » Slate
√ Would you like to use CSS variables for colors? ... yes
```

`npx shadcn-ui@latest add button`

### Buttons

...

### Marketing Skeleton

...

### Authentication (Clerk)

```
npm i @clerk/nextjs@4.29.9
clerk.com - login - create app: "antonio-duolingo-clone" - create application
copy API KEYS to .env
.gitignore .env
```

.env
```
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
```

### Footer

...

### Main layout

`npx shadcn-ui@latest add sheet`

### Sidebar

...

### Learn page wrappers

...

### Drizzle & Neon (elephantSQL)

dn: https://orm.drizzle.team/docs/get-started-postgresql

```
neon.tech: login - create instance - copy env to .env
npm i @neondatabase/serverless@0.9.0 drizzle-orm@0.30.1 dotenv@16.4.5
npm i -D drizzle-kit@0.20.14 pg@8.11.3
npm run db:push
validate table at neon dashboard
npm run db:studio - courses - add record - change title to "EMPTY_STRING"
- record: "1, Spanish, /es.svg" - save changes
```

.env
```
DATABASE_URL=
```

### Courses page

```
npm run db:studio
```

### Deployment

foreach
```
git add .
git commit -m "XX: message"
git push
validate deployment succeed
```

once
```
github.com/new - create repo
use second option - "push an existing repo"
.
vercel.com/new - import - deploy
settings - environment variables - add from .env
```