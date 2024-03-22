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
- record: 1 Spanish /es.svg
- save changes
```

.env
```
DATABASE_URL=
```

### Courses page

```
npm run db:studio - courses - add record - change title to "EMPTY_STRING"
- record(s): 2 French /fr.svg - 3 Croatian /hr.svg - 4 Italian /it.svg
- save changes
localhost: /courses
```

### User progress

```
npx shadcn-ui@latest add sonner 
npm run db:push
npm run db:studio - user_progress table
localhost: select a course in /courses, updates db
```

### Seed script

```
npm i -D tsx@4.7.1
npm run db:seed - removes user_progress data
```

### Schema

```
npm i -D tsx@4.7.1
npm run db:push - 
npm run db:studio - more tables
```

### Units

```
npm run db:seed
localhost: /learn show JSON of lessons 
```

### Lesson button

```
npm i react-circular-progressbar@2.1.0
npm run db:seed
localhost: /learn show button and info
```

### Lesson header

``` 
npx shadcn-ui@latest add progress
localhost: click lesson inside a course
```

### Exit modal

```
npx shadcn-ui@latest add dialog
npm i zustand@4.5.2
localhost: click exit icon in lesson
```

### Challenge cards

localhost: quiz cards appear in lesson

### Challenge footer

```
npm i react-use@17.5.0
localhost: play audio on click quiz card
```

### Challenge actions

localhost: choose quiz card & validate answer & hearts counter

### Challenge finish screen (freesound.org for audio)

```
npm i react-confetti@6.1.0
npm run db:seed
localhost: select course, go into lesson, select card until end, confetti at finish screen
```

### Challenge practice

localhost: select course, go into a comp. lesson, regain heart

### Shop

localhost: visit /shop, buy heart

### Stripe

Stripe API KEY & Webhook
```
npm i stripe@14.20.0
stripe.com - login - create store "antonio-duolingo"
click developers tab
api keys - copy secret key to .env
.
webhooks - "test in local environment"
download & open stripe cli 
run stripe login - visit link - allow access
run stripe listen --forward-to localhost:3000/api/webhooks/stripe
copy webhook signing secret to .env
.
stripe.com - search "billing portal" - customer portal
click "activate test link"
validate Billing - "Manage Billing" show "Stripe Plan"
.
npm run db:push
localhost: /shop - upgrade - pay with "42" - access settings to cancel
```

.env
```
NEXT_PUBLIC_APP_URL=http://localhost:3000
STRIPE_API_KEY=
STRIPE_WEBHOOK_SECRET=
```

Webhook production
```
stripe.com - login - developers tab - "add endpoint"
copy vercel endpoint to stripe "endpoint url" + "api/webhook/
select events - checkout.session.completed & invoice.payment.succeeded
click "add events" - "add endpoint"
click "reveal signing secret" - copy to vercel env vars
copy endpoint url to vercel env var NEXT_PUBLIC_APP_URL + remove "/" at end
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