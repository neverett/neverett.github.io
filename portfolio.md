---
title: Product documentation portfolio
---

# Introduction

This is a showcase of my professional technical writing work. If you have any questions, or would like to hire me to write technical documentation, email me at everettn AT protonmail DOT com.

## npm documentation

While a technical writer at npm, I was responsible for all product documentation, except for the CLI docs, which were the responsibility of the CLI team. Shortly after I started, I initiated a major project to overhaul the existing documentation and migrate to a new, Jekyll-based documentation website to increase site stability and enable content reuse through YAML.

To create a mind map and content plan for the updated documentation, I read all existing documentation, tested the product extensively on the website and in my local development environment, and partnered with technical support agents and engineers to understand our audience and their needs.

Over seven months, I wrote new content, heavily updated existing content, and took new screenshots. I wrote the new documentation in Markdown and the Liquid template language, with YAML front matter and reusable strings, in a fresh GitHub repository. I worked with npm’s designers and backend engineers to refresh the design and deploy the new documentation to our own server running Jekyll.

While the documentation has been moved to a new website and some of the content has been updated since I left npm, as of August 2023, the overall information architecture and a majority of the articles are my original work, which I have included below.

### Information architecture

#### Sitewide architecture

I created the high-level structure of the documentation shown below. ("Threats and mitigations" and "Integrations" were added after I left npm, and the page design has been slightly updated.) I organized the documentation into high-level, logically distinct categories that could help users easily find the help they needed.

<img width="1181" alt="Screenshot 2023-08-30 at 3 32 35 PM" src="https://github.com/datatoolsrc2023/nlrb_data/assets/417209/e6d6938b-6544-4d80-b129-6b9d0a9f2d1a">

#### Category and subcategory architecture

Within each category, I created task-oriented subcategories and articles. To keep the documentation usable, I stopped at a depth of one subcategory, since too many levels of hierarchy in documentation can be confusing and annoying to navigate.

One example is the "Packages and modules" category. Each subcategory contains a mix of conceptual ("About the public npm registry"), procedural ("Creating a package.json file") and/or reference articles ("npm package scope, access level, and visibility") that can be read separately or individually, and are progressively linked so the reader can move easily through the documentation, stopping when they have completed the task they set out to accomplish, or have satisfied their curiosity.

<img width="1061" alt="Screenshot 2023-08-30 at 3 51 01 PM" src="https://github.com/datatoolsrc2023/nlrb_data/assets/417209/a3bd2bfe-9489-4a6f-900c-9368dc6f02b4">
<img width="1067" alt="Screenshot 2023-08-30 at 3 56 58 PM" src="https://github.com/datatoolsrc2023/nlrb_data/assets/417209/41551f9f-43d1-496b-ad42-15bbffadccc7">

### Sample articles

#### Conceptual content

Conceptual content answers the questions "What is this about?" and "Why is it important?"; conceptual articles are often titled "About [X]". An example of conceptual content I have written is  "About private packages".

<img width="1061" src="https://github.com/datatoolsrc2023/nlrb_data/assets/417209/e1eb4061-0c83-4e27-953f-fc1ad3e9af4d">

#### Procedural content

Procedural content answers the question "How do I…?" and is often titled "[Do]ing [X]" to make it clear what action will be accomplished if you follow the steps in the article. An example of procedural content I have written is "Creating and publishing private packages".

<img width="1061" src="https://github-production-user-asset-6210df.s3.amazonaws.com/417209/264485969-ba97cee5-9ab2-4827-956f-74405e02292f.jpg">

#### Reference content

Reference content answers the question "What are the pieces"?. This content is usually formatted as a table, list, or chart, and is often titled with a noun or noun phrase. An example of reference content I have written is "npm package scope, access level, and visibility".

<img width="1061" src="https://github-production-user-asset-6210df.s3.amazonaws.com/417209/264487895-d904b32e-603d-4301-ad24-d19f8868ff58.png">







