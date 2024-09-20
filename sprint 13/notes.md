### Week 1 
02-9-2024 / 08-9-2024

Vercel = *Een cloudplatform waarmee ontwikkelaars websites en webservices kunnen hosten met directe implementatie.*

Static map: is de public map van ejs. wat je van client site kunt inladen 

Src map: stylesheet toevoegen aan je static moet in de app.html .In routes map kan je de route (pagina’s)zetten. In de lib staan de components die je kan hergebruiken.

in js haal je data op. je kunt classes maken in het zelfde bestand. alles wat je nodig hebt staat bij elkaar.  

export let data: In js daarna kan er in de html data.person gebruiken .

page.server.js 

page.svelte  zelfde als (view)

### Sveltekit installatie op vs code

1. **Visual Studio Code installeren**: Zorg ervoor dat je Visual Studio Code (VSCode) geïnstalleerd hebt op je computer.
2. **Node.js installeren**: Installeer Node.js, omdat je deze nodig hebt om SvelteKit-projecten te draaien.
3. **SvelteKit project aanmaken**:
    - Open een terminal in VSCode.
    - Voer het volgende commando uit om een nieuw SvelteKit-project aan te maken:
        
        ```bash
        npm init svelte@next my-svelte-project
        
        ```
        
    - Volg de instructies op het scherm om het project te configureren.
4. **Navigeren naar je projectmap**:
    - Ga naar de map van je project:
        
        ```bash
        cd my-svelte-project
        ```
        
5. **NPM-pakketten installeren**:
    - Installeer de benodigde pakketten met:
        
        ```bash
        npm install
        ```
        
6. **Project starten**:
    - Start de ontwikkelserver met:
        
        ```bash
        npm run dev
        ```
        
    - Open je browser en ga naar de URL die in de terminal wordt weergegeven om je SvelteKit-project te bekijken.
7. **Svelte for VSCode installeren**:
    - Ga naar de extensiemarkt in VSCode en installeer de "Svelte for VSCode" extensie voor betere ondersteuning van Svelte in de editor.

**3  leer vragen**

1. hoe zet je een basis set-up van sveltekit op je vs code?
2. hoe maak je routes aan als je met svelte werkt?
3. hoe voeg je styling toe aan je website met sveltekit?