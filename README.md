
**New Feature Launch**
# AI Copilot Launch- Draw.io — Smart Diagram Generator 

AI Copilot is an intelligent diagram assistant integrated into Draw.io Desktop that converts natural language into structured diagrams. It helps users quickly generate flowcharts, system architectures, process maps, agent workflows, trees, and connected diagrams — without manual block placement.

This tool is designed for developers, architects, students, analysts, and product teams who want fast diagram creation from human-readable instructions.

---

---
### 🔐 API Key Setup (Required)

AI Copilot needs an LLM API key to generate diagrams from natural language.

Steps:

Open AI Copilot → Settings

Select your model provider

Paste your API key

Click Save

Generate diagram normally

No restart required.

### 🤖 Recommended Model Providers

Based on tested results and diagram quality:

✅ Preferred (Best diagram reasoning + structure):

Claude

Gemini

⚠️ Use GPT only if needed

Works fine for simple flows

May produce weaker structure for very complex architectures compared to Claude/Gemini

🧠 Model Selection Tip

If your diagram is:

Large architecture → Use Claude

Multi-agent / routing / layered system → Use Claude

Flowcharts & structured logic → Use Gemini

Quick simple shapes → Any model works

🔑 Where to Get API Keys

Claude → Anthropic Console

Gemini → Google AI Studio

GPT → OpenAI Platform

(Create key → copy → paste into Copilot Settings)
---

# Core Capabilities

### Natural Language → Diagram
Describe what you want in plain English — Copilot generates connected diagram structures automatically.

Examples:
- User login flow with validation and error branch
- Microservice architecture with API gateway and database
- HR and IT agent routing workflow

No strict syntax required.

---

### Supported Diagram Types

Copilot can generate:

- Flowcharts
- System architecture diagrams
- Agent workflows
- API & backend architecture
- Data pipelines
- Decision trees
- Control flow diagrams
- Service interaction maps
- Layered architecture
- Tool‑agent pipelines
- Validation flows
- Branching logic diagrams

---

### Simple + Complex Mode

Copilot adapts to request complexity.

Single Shape Mode examples:
- draw a circle
- create three rectangles
- add a database block
- draw five nodes not connected

Connected Flow Mode examples:
- start → process → decision → end
- user submits form then validate then store
- controller calls service calls repository

---

### Smart Intent Detection

Copilot detects:
- steps
- decisions
- branches
- loops
- tools
- repositories
- databases
- routers
- agents
- pipelines

---

### Auto Layout Engine

Generated diagrams are automatically:
- spaced properly
- non‑overlapping
- hierarchy aligned
- edge routed
- readable at scale

---

### Model Flexibility

Supports multiple AI providers selectable in settings depending on quality, speed, or quota.

---

## User Guide

Step 1 — Open Copilot panel inside Draw.io.

Step 2 — Enter diagram description using natural language.

Step 3 — Click Generate Diagram.

Step 4 — Edit shapes manually if needed (all output is standard Draw.io objects).

---

## Prompt Writing Guide

Best pattern: short step‑style flow description instead of essays.

Good:
Start → validate input → if valid save → else error → end

Better:
User sends request to API → API calls service → service reads database → response returned

---

## Tested Prompt Examples

Simple shapes:
draw a circle  
create three rectangles not connected  
add two databases and one process block  

Basic flow:
start process decision valid yes dashboard no error end

Login flow:
User logs in → validate → if valid dashboard → else error → end

API layered flow:
Controller calls service → service calls repository → repository queries database → result returns

Data pipeline:
Receive CSV → validate → if invalid stop → if valid transform → load warehouse → retry on failure → alert admin

Agent workflow:
User query → router decides HR or IT → HR agent uses HR tool → IT agent uses ticket tool → both return → router responds

Architecture:
UI → API gateway → auth service + order service → databases → logging → response

Tree:
Decision tree for loan approval with credit score branches

Parallel flow:
Start → split processing and logging → join → output

---

## Tips for Better Results

- Use arrows or words like then, next, after
- Mention decisions explicitly
- Name components clearly
- Use yes/no branches
- Say “not connected” if no edges desired
- List architecture components and relationships

---

## Known Behavior

- Very complex diagrams need clearer step wording
- Dense graphs improve with ordered prompts
- No‑connection diagrams require explicit wording

---

## Ideal Use Cases

- Software architecture design
- Backend flow mapping
- Agent systems
- AI pipelines
- DevOps flows
- Business processes
- Decision trees
- Data pipelines
- API maps
- Tool orchestration diagrams

---

## Advantages

- Natural language driven
- No rigid syntax
- Simple to enterprise diagrams
- Clean auto layout
- Fully editable output
- Multi‑model compatible
- Fast diagram bootstrapping

---

AI Copilot accelerates diagram creation. Generate fast, refine visually, deliver professionally.


---
About
----- 

**drawio-desktop** is a diagramming desktop app based on [Electron](https://electronjs.org/) that wraps the [core draw.io editor](https://github.com/jgraph/drawio).

Download built binaries from the [releases section](https://github.com/jgraph/drawio-desktop/releases).

**Can I use this app for free?** Yes, under the apache 2.0 license. If you don't change the code and accept it is provided "as-is", you can use it for any purpose.

Security
--------

draw.io Desktop is designed to be completely isolated from the Internet, apart from the update process. This checks github.com at startup for a newer version and downloads it from an AWS S3 bucket owned by Github. All JavaScript files are self-contained, the Content Security Policy forbids running remotely loaded JavaScript.

No diagram data is ever sent externally, nor do we send any analytics about app usage externally. There is a Content Security Policy in place on the web part of the interface to ensure external transmission cannot happen, even by accident.

Security and isolating the app are the primarily objectives of draw.io desktop. If you ask for anything that involves external connections enabled in the app by default, the answer will be no.

Support
-------

Support is provided on a reasonable business constraints basis, but without anything contractually binding. All support is provided via this repo. There is no private ticketing support for non-paying users.

Purchasing draw.io for Confluence or Jira does not entitle you to commercial support for draw.io desktop.

Developing
----------

**draw.io** is a git submodule of **drawio-desktop**. To get both you need to clone recursively:

`git clone --recursive https://github.com/jgraph/drawio-desktop.git`

To run this:
1. `npm install` (in the root directory of this repo)
2. [internal use only] export DRAWIO_ENV=dev if you want to develop/debug in dev mode.
3. `npm start` _in the root directory of this repo_ runs the app. For debugging, use `npm start --enable-logging`.

Note: If a symlink is used to refer to drawio repo (instead of the submodule), then symlink the `node_modules` directory inside `drawio/src/main/webapp` also.

To release:
1. Update the draw.io sub-module and push the change. Add version tag before pushing to origin.
2. Wait for the builds to complete (https://travis-ci.org/jgraph/drawio-desktop and https://ci.appveyor.com/project/davidjgraph/drawio-desktop)
3. Go to https://github.com/jgraph/drawio-desktop/releases, edit the preview release.
4. Download the windows exe and windows portable, sign them using `signtool sign /a /tr http://rfc3161timestamp.globalsign.com/advanced /td SHA256 c:/path/to/your/file.exe`
5. Re-upload signed file as `draw.io-windows-installer-x.y.z.exe` and `draw.io-windows-no-installer-x.y.z.exe`
6. Add release notes
7. Publish release

*Note*: In Windows release, when using both x64 and is32 as arch, the result is one big file with both archs. This is why we split them.

Local Storage and Session Storage is stored in the AppData folder:

- macOS: `~/Library/Application Support/draw.io`
- Windows: `C:\Users\<USER-NAME>\AppData\Roaming\draw.io\`

Not open-contribution
---------------------

draw.io is closed to contributions (unless a maintainer permits it, which is extremely rare).

The level of complexity of this project means that even simple changes 
can break a _lot_ of other moving parts. The amount of testing required 
is far more than it first seems. If we were to receive a PR, we'd have 
to basically throw it away and write it how we want it to be implemented.

We are grateful for community involvement, bug reports, & feature requests. We do
not wish to come off as anything but welcoming, however, we've
made the decision to keep this project closed to contributions for 
the long term viability of the project.
