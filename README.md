# Thirsty Machines
Final project for the Building AI course
## Summary
AI data centers need huge amounts of water for cooling, but where should new ones go? This Building AI course project looks at how to pick locations with enough water, far from people, and with clean energy nearby — without making things worse for the planet.
## Background

AI is growing fast, and every new model or service needs data centers to run on. What gets talked about less is how much water these data centers use just to stay cool. As I went through this course, I kept coming across the same issue: the places with the most water aren't always the places where a data center should go, and the places that make sense on paper (empty land, lots of sun for solar power) often don't have water nearby at all.

This isn't a small problem. As AI use keeps growing, more data centers will be built, and each one needs a location. Getting that choice wrong means either straining local water supplies, harming ecosystems, or burning a lot of energy just to move or produce water (like desalination near the coast).

I'm not against AI — I think it has real potential, which is part of why I care about getting the infrastructure behind it right.

Some of the problems this project looks at:
* Freshwater sources are often near populated areas or farmland, competing with human and agricultural use
* Desert locations with strong solar potential usually lack water for cooling
* Desalinating seawater solves the water problem but adds significant CO2 emissions
* There's no simple, publicly available way to compare candidate locations across all these factors at once

## How is it used?

Right now, choosing where to build an AI data center mostly comes down to buying land and starting construction — there isn't a standard way to check the full picture first.

This tool is meant for government bodies that handle land concessions and permits for new infrastructure. Instead of approving a location because a company already picked it, a government agency could use this to check a proposed site against water availability, distance from populated areas, energy source, and estimated CO2 impact before granting the land.

It would be used early, during the planning and permitting stage — before construction starts, not after. The main users are the people inside government departments responsible for infrastructure approval, environmental impact assessment, and land use planning. They'd need the tool to give a clear, comparable score or flag for each candidate site, not just raw data, since decisions often need to be made and justified quickly.

## Data sources and AI methods

The project would rely on public datasets that already exist, rather than collecting new data:

* [WRI Aqueduct Water Risk Atlas](https://www.wri.org/aqueduct) — water stress and availability by region
* [WorldPop](https://www.worldpop.org/) — population density, to check distance from populated areas
* [Global Solar Atlas](https://globalsolaratlas.info/) and [Global Wind Atlas](https://globalwindatlas.info/) — renewable energy potential by location
* [World Database on Protected Areas (WDPA)](https://www.protectedplanet.net/) — protected areas to exclude from consideration
* National/regional grid carbon intensity data — to estimate the CO2 impact of powering a site

On the AI/methods side, this is mainly a multi-criteria decision problem: each candidate location gets scored across the factors above (water, distance from people, energy potential, CO2 impact, protected status), with weights reflecting how important each factor is. Locations can then be ranked or filtered out if they fail a hard constraint (e.g. inside a protected area). A simple optimization or clustering approach could help group similar candidate sites and highlight the best trade-offs, rather than pretending there's one perfect answer.

## Challenges

This doesn't solve everything, and it's better to say that clearly now.

* It doesn't know anything about politics, local economics, land disputes, or whether a government will actually stick to the criteria once the land is granted
* The main trade-off — water vs. clean energy vs. CO2 from things like desalination — is still there no matter what. The tool can lay it out clearly, but someone still has to pick what matters most. It doesn't do that for you
* Public datasets have gaps. Water stress numbers and population data can be old or too rough for one specific site, especially in places that aren't well monitored
* It only looks at distance from people, not things like water rights or how a new site would actually affect a community long-term — that needs its own, deeper study
* Someone could use a tool like this to justify a decision they'd already made, instead of actually using it to decide. The scoring needs to stay visible and honest, or that's exactly what happens
* 

## What next?

The next real step would be turning this from an idea into a working prototype — a script that scores a handful of real candidate locations using the public datasets listed above, so the trade-offs become visible instead of theoretical.

Beyond that, this project only really works if it's not just one government or one company checking a site on its own. AI's water and energy footprint is a global issue, so ideally there would be some kind of international body — hard as that is to get agreement on — looking at the environmental, geopolitical and social side of AI infrastructure together. That could eventually cover things well beyond site selection: costs and land concessions, construction and maintenance oversight, required certifications for companies building these sites, risk assessment, and independent third-party checks over time, not just at the approval stage.

There's also a social side worth building in eventually: job security for the people working at these sites so they're not later replaced by the same AI they helped build, and a requirement that some percentage of project profits go toward fixing environmental damage elsewhere — desertification, for example, not just avoiding new damage where the site is built.

None of that is realistic to build alone. It would need input from people who actually work in environmental policy, energy and international regulation — this project is a starting point for the conversation, not the final answer.


## Acknowledgments

* This project idea and structure follows the Building AI course final project template, created by Reaktor Innovations and University of Helsinki
* Thanks to the teams behind the public datasets this project would rely on: [WRI Aqueduct](https://www.wri.org/aqueduct), [WorldPop](https://www.worldpop.org/), [Global Solar Atlas](https://globalsolaratlas.info/), [Global Wind Atlas](https://globalwindatlas.info/), and the [World Database on Protected Areas](https://www.protectedplanet.net/)
* The idea itself came out of following this course and reading more broadly about the environmental footprint of AI infrastructure
