# Sprint 15

## choices choices

- onderzoek een nieuwe tech-stack voor het ontwerpen en bouwen van een website voor een opdrachtgever. (documenteren, onderzoek, lerend vermogen)
- verantwoord en presenteer je jouw gemaakte keuze
- neem je mentorrol in jaar 1 serieus (samerwerking met diversieteit

16- 10 

code review gehad met shyanta die werkt voor NL ziet 

Vraag;  wij moeten een infinite canvas maken,  we gebruiken nu flex box maar is dit handig?  is dit het beste of zou grid beter passen? 

- gebruik flex
_

## Talk Presentation by Kevin Levis

How I Make Choices

Directus: A headless CMS

Role: Lead a team managing the developer experience (the actual platform, not the background)

What do we do?

- We ask ourselves how to help people understand what Directus is and its capabilities.
- Extensions in the marketplace ⇒

How do they make money?

- Directus Cloud
- Open source: It's an open-source project unless you make $5 million a year.
- They make money through professional services
- Directus Plus

Trade-offs (Choices)

The Iron Triangle

- Choose between fast, good, or cheap
- Only choose 2 of these; having all 3 never works
- Your product will be either expensive, slow, or low quality

Perfectionism

Tech Stack Selection

Performance vs. Maintainability

- By what degree, over what scale and cost?
- At Directus, they prioritize performance
- Tailwind = CSS utility library, makes development quicker. But vanilla CSS is good and could save time in future maintenance

Velocity (how fast you can build something) vs. Flexibility
_
Innovation (tests) vs. Reliability (income)

## Talk syanta

Shyanta is een techlead bij Triple.

Hypersolid heeft ongeveer 500+ mensen in dienst.

De kernactiviteiten zijn: development, design, technical operations en data & insights.

Sfeer is belangrijk, gezelligheid ook.

Ze werken met web, React Native, en smart TV (websites die op tv draaien, op oude browsers met weinig RAM en geheugen. Daarom gebruiken ze Svelte. Het draait op hele kleine bundel-files, wat handig is voor smart TV).

Ze hebben 3 losse teams die allemaal dezelfde stack gebruiken.

Way of working:

Ze gebruiken Scrum, met een daily stand-up.

Ze houden retrospectives en sprint reviews.

Ze gebruiken Jira (in plaats van project boards en issues).

*Waarom kies je en bepaal de tech stack?*

- Het ligt aan je eindproduct - de keuze voor een tech stack hangt af van wat je uiteindelijk wilt bereiken
- Performance vereisten - sommige projecten hebben specifieke prestatie-eisen die bepaalde technologieën noodzakelijk maken
- Team expertise - kies technologieën waar je team ervaring mee heeft of snel in kan leren
- Schaalbaarheid - overweeg hoe goed de gekozen stack kan meegroeien met je project
- Onderhoud op lange termijn - denk na over de toekomstbestendigheid en onderhoudbaarheid van de gekozen technologieën

There needs to be a balance

AI

Ethics: Built on theft

Costs: Lots of money

Accuracy

Directus AI

Concerns:

- It's a distraction; they don't want to be seen as an AI company
- It's not accurate
- Dependency on 3rd party services (bring your own API key)

Cost-benefit analysis

SWOT (Strengths, Weaknesses, Opportunities, Threats)

Weighted decision matrix

Using Directus:
CMS lots of people use it, I don't think it's the best CMS.
We're not a content management system. It can be used but it might lack some features.
Features need to benefit 80% of users.

The tech you use probably doesn't matter.
You're going to make some bad decisions; over time, you'll learn.

Directus TV

gebruik van componetne is heilig. het framewiej waarin je giet staat hier los van. 

1. formuleer een stand punt en selecteer argumenten.  
2. maak een agrumenten schema 
    - serie argumenten verzamet en die zeg je in een schema.
3. beoordelen van aanvaarbaarheid 
4. argumentenschema uitwerken 

___

**18-10**

## Next.js research (analyseren)

### What is Next.js?

Next.js is a React framework for building full-stack web applications. You use React Components to build user interfaces, and Next.js for additional features and optimizations.

Under the hood, Next.js also abstracts and automatically configures tooling needed for React, like bundling, compiling, and more. This allows you to focus on building your application instead of spending time with configuration.

**accessibility**

For optimal accessibility when using a screen reader while reading the docs, we recommend using Firefox and NVDA, or Safari and VoiceOver.

What is your project named? my-app
Would you like to use TypeScript? No 
Would you like to use ESLint? No
Would you like to use Tailwind CSS? No 
Would you like to use `src/` directory? Yes
Would you like to use App Router? (recommended)  Yes
Would you like to customize the default import alias (@/*)? No / Yes*



**Routing:**

**Define pages;** 

You can define a page by default exporting a component from a `page.js` file.

**Data fetching**

```js
export default async function Page() {
let data = await fetch('https://api.vercel.app/blog')
let posts = await data.json()
return (
<ul>
{posts.map((post) => (
<li key={[post.id](http://post.id/)}>{post.title}</li>
))}
</ul>
)
}
```

css: 

Next.js has built-in support for CSS Modules using the `.module.css` extension.

Er zijn 2 verschillende manieren o het zelfde te maken.  /pages en /app

**20-10**

**Wat is jsx?**

**JSX (JavaScript XML)** is a syntax extension for JavaScript that is used with React to describe what the UI should look like. It looks similar to HTML but is used inside JavaScript code to define the structure and content of user interfaces

1. **Page Components (`page.js`)**:

2. **Layout Files (`layout.js`)**:

- Layout files define the shared structure (like a header or footer) that persists across different pages.
- In the **App Router**, each folder can have its own `layout.js` file.
- Name it **`layout.js`** to define a layout for a specific route or set of routes.
- 

**3. Helper or Utility Functions (`fetch-json.js`)**:

- Utility functions (like your `fetch-json.js` file) are typically placed in a separate `lib/` or `utils/` folder.
- The file should be named based on its purpose. In your case, `fetch-json.js` makes sense since it describes its role in fetching JSON data.

4. **Server-side Files (`server.js`)**:

If `server.js` contains server-side logic, such as custom API routes or middleware, it should be named and located according to its purpose.

Custom API routes are defined in the `pages/api/` or `app/api/` directories, and each file becomes an API endpoint.

API data inladen 

```

export default async function Page() {
  try {
    // Fetch data van de API
    const res = await fetch('https://fdnd-agency.directus.app/items/fabrique_art_objects', { cache: 'no-store' });

    // Check of de response is OK (status 200-299)
    if (!res.ok) {
      throw new Error("Failed to fetch data");
    }

    // response naar JSON
    const data = await res.json();
    console.log("API data:", data);

    // const data 
    const artObjects = data.data;

```

images inladen met de api 

```js
  <section>
        <h1>Art Objects</h1>
        <ul>
          {artObjects.map((artObject) => (
            <li key={artObject.id}>
              <img
                src={'https://fdnd-agency.directus.app/assets/' + artObject.image}
                alt={artObject.title || 'Art Object'}
                width={300}
                height={200}
              img/>
            </li>
          ))}
        </ul>
      </section>
```

**21-10**

is het gebruikelijk dat er in next.js of react bijna alles in functies of variabels worden gemaakt?

Yes, in React (and modern JavaScript in general), it's common to define components as functions, and these functions are typically assigned to constants (variables). This is called a **functional component**, and it is one of the most common ways to create components in React today.

**22-10**

Difference Between `.js` and `.jsx`

- **`.js` (JavaScript)**: This is the general JavaScript file extension. It can contain regular JavaScript code as well as JSX (the HTML-like syntax React uses). Most modern tools and compilers like **Next.js**, **Create React App**, **Vite**, etc., are configured to handle JSX inside `.js` files without any issues.
- **`.jsx` (JavaScript XML)**: This file extension specifically indicates that the file contains JSX syntax. It’s more explicit because it tells developers and the build system that this file has JSX inside, which might help with clarity in some cases.

### When to Use `.js` vs `.jsx`

- **Use `.js`** if you want a simpler setup. In most React/Next.js projects, JSX can be used inside `.js` files, and there's no need to change the extension to `.jsx`. Since you are already using `page.js`, it's consistent to use `.js` for the component as well.
- **Use `.jsx`** if you want to be explicit about the fact that the file contains JSX. Some developers prefer this for readability, especially in large codebases where not all JavaScript files contain JSX.
