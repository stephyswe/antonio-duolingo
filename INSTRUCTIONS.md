### Initial Setup

`npx create-next-app@14.0.4 antonio-nextauth5-clone`
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
√ Which style would you like to use? » New York
√ Which color would you like to use as base color? » Slate
√ Would you like to use CSS variables for colors? ... yes
```

`npx shadcn-ui@latest add button`

### Structure 

...

### Concex Clerk

convex setup: https://docs.convex.dev/quickstart/nextjs
``` 
npm i convex@1.8.0
npx convex dev - "a new project" - <enter>
[2]: npm run dev
convex.dev: login - open created project
.
clerk.com - login - create app: "antonio-miro-clone - 
```

clerk setup: https://clerk.com/ - login - add application
```
application name: antonio-miro-clone
create application
copy API KEYS to .env
.gitignore .env
npm i @clerk/nextjs@4.29.5
```

convex clerk tutorial: https://docs.convex.dev/auth/clerk
```
clerk dashboard - jwt templates - new template: "convex" - copy issuer field to convex/auth.config.js
npx convex dev  (validate is ready)
[2]: npm run dev
clerk dashboard - customization/branding - hide clerk branding: "on"
```

.env.local
```
CONVEX_DEPLOYMENT=

NEXT_PUBLIC_CONVEX_URL=

NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
```

### Dashboard layout

...

### Sidebar

```
clerk dashboard: organizations - enable organizations
- jwt templates - convex - claims: add "org_role" & "org_id" - save changes
clerk dashboard: customizations - avatars - Default organization logo - initials - save changes
.
npx shadcn-ui@latest add dialog tooltip
localhost: login - create organization (+) - name: "test" - create org - skip
- create organization (+) - name: "two" - create org - skip
```

### Organisation sidebar

```
localhost: create new account - create an org - name: "invite-test" - invite first account, role: member
- email - accept invite - validate "invite-test" org is added
```

### Navbar

```
npx shadcn-ui@latest add input
npm i query-string@8.1.0 usehooks-ts@2.10.0
localhost: login as first account - remove "two" org - validate "invite members" not shown
```

### Empty states

...

### Create mutation

```
add convex/schema.ts
npx convex dev
convex.dev: app - data/tables/boards - preview at "show schema"
add convex/board.ts
npx shadcn-ui@latest add sonner
localhost: login - organization - create board
convex.dev: app - data/tables/boards - 1 new document
```

### Board list

```
npx shadcn-ui@latest add skeleton
npm i date-fns@3.3.1
```

### Card actions

```
npx shadcn-ui@latest add dropdown-menu alert-dialog
npm i zustand@4.5.0
localhost: login - organization - board item - options - change title - save
```

### Favorite

...

### Querying

```
npm i convex-helpers@0.1.14
localhost: search boards
```

### Canvas layout

open a board

### Liveblocks

```
liveblocks.io: login - projects/development
npm i @liveblocks/client@1.9.7 @liveblocks/react@1.9.7
npx create-liveblocks-app@latest --init --framework react - y x3 - generate liveblock.config.ts (replace with org.repo)
- apikey tab - copy public key to liveblock.config.ts /* Do not commit key! */
localhost: open a board
liveblock.io - rooms tab - show new room id
```

### Room auth

```
npm i @liveblocks/node@1.9.7
liveblock.io: apikey tab - real & copy secret key to .env
localhost: open a board - validate console name & picture
```

.env
```
LIVEBLOCKS_SECRET_KEY=
```

### Room info

localhost: open a board - validate edit title in toolbar

### Participants

```
npx shadcn-ui@latest add avatar
localhost: open a board - users in corner, invite to view more
```

### Room toolbar

...

### Canvas state

...

### Cursors presence

localhost: board - view cursor of invited user

### Insert layer

``` 
npm i nanoid@5.0.4
localhost: board - insert layer
```

### Select layer

localhost: view selection of second user

### Selection box

localhost: selected layer show resize option

### Resize layer

localhost: selected layer can be resized (has bug!)

### Translate layer

localhost: move & fix to resize layer

### Color & delete

...

### Layer depth

...

### Selection net

...

### Other elements

...

### Pencil

`npm i perfect-freehand@1.2.0`

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