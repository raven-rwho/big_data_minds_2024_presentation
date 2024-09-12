---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /intro.png
# some information about your slides (markdown enabled)
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# Implementing and scaling of Data Mesh while using Palantir Foundry
## a retrospective of the last 6 year journey
17.9.24 Berlin - Peter Krauß-Hohl

---
transition: fade-out
class: text-center
---
<br>
<br>

# Let me tell you a story

<br>
<br>

## The year is 2018 and we are in Berlin. 
<br>
<br>

## More precisely in the office of Axel Springer National Media&Tech.


<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/features/slide-scope-style
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
layout: image-right
image: /guenther.png
---

# Our protagonist

Günther aka PO central DWH -  he would love to help but...

- There are analytical request from all parts of the org 
- the data quality is - let's say questionable
- dwh consists of ~2500 tables, without documentation and inconsistent naming (mapping tables from id_a -> id_b)
- the developer retention is 6 months
- he is PO number 15 in 2 years

---
layout: image-right
image: /eliza.png
---

# Data Science

Eliza (name is fictitious) is a Data Scientist 

She is hired to figure out ihow to keep a user in the subscription for germanies biggest newspaper.

She was super exited:
- what is the right ml model to approach it
- Maybe some easy linear regression
-  or deep learning

---
layout: image-right
image: /eliza_equations.png
---

# First things first
<br>
<br>

__get the data and make my hands dirty!__

But wait, __how do I get the data?__ I don't have access to the Oracle cluster that all the raw events that I definitely need are stored...

Hmmm, can't be so hard to get access, let's ask Günther!

<small> -> Eliza is sending requests that she needs the raw data and maybe a bit of documentation to understand it.... 
</small> 

---
layout: image-right
image: /guenther_helpless.png
---
# There is no way to help

Guenther would love to help Eliza, but there is no way to prioritize her higher and he can't give her access, because:

- not allowed
- license
- no one who has the time to explain

---
layout: image-right
image: /eliza_frust.png
---
# How should I work on my churn problem then???

After waiting 6 weeks Eliza got one copy of a table via E-Mail and realized after 6 hours that she needs different data and don't get an answer

---
layout: image-right
image: /peter_cartoon.png
---

# Peter
We need a Data Lake

Peter got the task to build a data lake and the requirements are:
- scale infinitly
- native accessible for all personas (DS, Eng, SQL)
- structured & unstructured
- in the cloud

<v-click>
<div style="display: flex; justify-content: center; align-items: center;">

__Time to data__ -> is the crucial KPI to work on.

</div>
</v-click>

---
layout: image-right
image: /foundry.png
---

# Palantir Foundry
<br>

Luckily we had the possibility to introduce Foundry from the company Palantir quite fast in our org and by following a few simple rules (which were hard to maintain), we managed to build up an environment in which every employ who get's her login to our Single-Sign on has immediate access to all the data and access to a quite powerful tool-set to work with it

---
layout: image-right
image: /rules.png
---

# Rules

1. only sources that we know already that we need are allowed to be connected to the Data Lake
2. everyone gets reading access to everything
3. __no dependencies__ <- copy it and build your own pipeline 
<br>
<br>
<br>
<br>
<br>
<v-click>
-> Hey, wait sounds nice - but wasn't this talk about Data Mesh???
</v-click>

---
layout: image-right
image: /back_to_the_future.png
---
# Let's jump some years to the future
Data Lake architecture is implemented

- all neccessary sources are ingested (only the neccessary ones)
- time to data is down to minutes
- production grade data products:
  - ml based optimizations
  - dashboards
  - business relevant data sets


<!-- # Let's jump some years into the future!
<div style="display: flex; justify-content: center; align-items: center; height: 100%;">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/IIl8y89gGJM?si=Iy0dWcL_YqOyFLgD" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-<picture>; " referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div> -->

---
layout: image-right
image: /x_functional_teams.png
---

# Cross functional teams
our actors found friends

- Guenther joined the team "Justice League" and they are building optimizations for ad revenue
- Eliza joined the recomendation teams aka the "Avengers"

---
layout: image-right
image: /desaster_batman.png
---

# The Ad System broke down
desaster for Justice League

- System generated prices which are way off
- hard to track where the error comes from
- significant financial impact

---
layout: image-right
image: /victory_pose.png
---

# What has happened?
1/3
<v-click>
  <div style="display: flex; justify-content: center; align-items: center;">
    <img src="/data_product_1.png" alt="Image 1" style="width: 90px;">
  </div>
</v-click>
---
layout: image-right
image: /team_piggyback.png
---

# What has happened?
2/3
<v-click>
  <div style="display: flex; justify-content: center; align-items: center;">
    <img src="/data_product_2.png" alt="Image 2" style="width: 210px;">
  </div>
</v-click>

---
layout: image-right
image: /hulk_batman.png
---

# What has happened?
3/3
<v-click>
  <div style="display: flex; justify-content: center; align-items: center;">
    <img src="/data_product_3.png" alt="Image 3" style="width: 273px;">
  </div>
</v-click>

---
layout: image-right
image: /tradeoff.png
---

# Independent vs central


## indissoluble tradeoff
<br>

### Independency
  - the fastest and most expensive
  - things are doubled
<br>
<br>

### Centralization
  - controlled
  - more cost-efficient 

---
layout: image-right
image: /super_hero.png
---

# Data Mesh for the rescue
Like in the discusion about Micro Services or a monolithic structure - this is just about scaling the service that you are working on to many people and therefore the Data Mesh approach offers some tooling

<!-- add picture of the fixed graph-->

---
layout: image-right
image: data_mesh_book.jpg
---

# Core Ideas of Data Mesh

- Decentralized teams and data ownership

- Data Products powered by Domain Driven Design

- Self-serve Shared Data Infrastructure

- Global federated Governance

[Zhamak Dehghani](https://martinfowler.com/articles/data-mesh-principles.html)

[Book - Data Mesh](https://martinfowler.com/articles/data-mesh-principles.html)

---
layout: full
---

# Data Products powered by Domain Driven Design

- **Discoverable**
  - Set of meta information to allow the automatic registration in a central registry.


<v-click>

- **Understandable**
  - The specific meaning of coherent data - what kind of entities and the relationships between them
</v-click>

<v-click>  

- **Addressable**
  - A data product offers a permanent and unique address to allow the user or system to access it.
</v-click>

<v-click>

- **Natively Accessible**
  - It can be accessed by different personas - scientist (SQL), engineers (API) , analyst(Spreadsheet or SQL)
</v-click>

<v-click>

- **Secure**
  - Encryption, Access Control, Data retention, Regulations, Confidentially Levels
</v-click>

<v-click>

- **Trustworthy**
  - Interval of Change, Timeliness Completeness, Stat shape of data, precision&accuracy over time
</v-click>

<v-click>

- **Valuable on its own**
  - No need to add more to be generate value
</v-click>

---
layout: image-right
image: foundry_mesh.png
---

# Data Mesh with Foundry

| **Characteristics**                    | **Status**        |
| --------------------------------------- | ----------------- |
| **Discoverable**                        | ✅                |
| **Understandable**                      |                 |
| **Addressable**                         | ✅                |
| **Natively Accessible**                 | ✅                |
| **Secure**                              | ✅                |
| **Trustworthy**                         |                 |
| **Valuable on its own**                 |                 |

---
layout: full
---
# Foundry Home

<img src="/foundry_home.png" alt="Image" style="width: 100%; height: auto;">

---
layout: full
---
# Data Catalogue

<img src="/catalogue.png" alt="Image" style="width: 100%; height: auto;">

---
layout: full
---
# Documentation

<img src="/documentation.png" alt="Image" style="width: 100%; height: auto;">


---
layout: full
---
# Lineage

<img src="/lineage.png" alt="Image" style="width: 100%; height: auto;">

---
layout: image-right
image: /shake_hands_heroes.png
---

# Dataset as a product
<v-click>
  <div style="display: flex; justify-content: center; align-items: center;">
    <img src="/data_product_mesh.png" alt="Image 3" style="width: 400px;">
  </div>
</v-click>

<!-- add picture of the fixed graph-->

---
layout: image-right
image: /missing.png
---
# not covered


- no data contracts
- no way to enforce communication with owners

---
layout: image-right
image: /long_way.png
---
# long way to go

- use the open API's of Foundry to track ownership
- use the ontology to define data contracts
- other aspects of data mesh
  - business owners are not in the team

---
layout: end
class: text-center
---

# Thank You

### Thats me

[Blog](https://pkrauss-hohl.site) · [GitHub](https://github.com/raven-rwho) · [Linkedin](https://www.linkedin.com/in/kraussdevelopment/)

<PoweredBySlidev mt-10 />

---
layout: center
class: text-center
---

# Questions?

---
layout: image-right
image: /mature_vs_start.png
---
# A question that you might have

Data Mesh or Central Data Team?

## no binary answer!

- depends on maturity of your data landscape 
- like microservices this is all about scaling the org
- if you need to work with many ppl on the same data - you need it
- otherwise - go fast and break things