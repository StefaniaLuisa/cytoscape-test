# Gambrell Foundation — The Library: Book Connection Graph

An interactive graph visualization of the Gambrell Foundation's curated library of 50 books, organized into six thematic pillars and connected by 72 semantic relationships. Built as a standalone, browser-ready HTML application — no build step or server required.

---

## Visualizations

### `gambrell-library-cytoscape.html` *(primary)*
Built with **Cytoscape.js**. Renders all 50 books as a force-directed network graph, with edges drawn from the full relationship dataset. This is the recommended version for exploring book connections.

**How to use:**
1. Open the file in any modern browser (or serve locally with `python3 -m http.server 8080`)
2. **Hover** a node — tooltip shows title, author, and pillar
3. **Hover** an edge — tooltip shows the two connected books and the reason for their connection
4. **Click** a book node — highlights its connections, fades unrelated books, and opens a sidebar with synopsis, Gambrell commentary, connected books, and a Learn More link
5. **Click a connected book pill** in the sidebar — animates the camera to that book and loads its detail
6. **Pillar filter chips** (top-left) — toggle one or more pillars to focus the view; mix multiple filters freely
7. **Click the canvas background** — resets all highlights and closes the sidebar
8. **⌖ / + / −** buttons (bottom-right) — fit to view, zoom in, zoom out

### `gambrell-library-graph-v2.html` *(original)*
Built with **D3.js v7**. An earlier version of the visualization using a hierarchical structure (Library → Pillars → Books → Authors → Tags) with 22 hardcoded books. Retained as a reference.

---

## Data Files

| File | Description |
|---|---|
| `books_nodes.csv` | 50 books with full metadata: title, author, pillar, secondary categories, synopsis, Gambrell commentary, post URL, purchase link, and related book IDs |
| `book_relationships_edges.csv` | 72 directed relationships between books, each with a type, strength (1–3), and plain-language reason |
| `taxonomy_reference.csv` | Reference table defining the 6 primary pillars and 9 secondary categories with display rules |
| `Gambrell - The Library (formerly, Reading Room) - Content Plan.gdoc` | Linked Google Doc with the full content plan (external) |

---

## Graph Structure

| | Count |
|---|---|
| Book nodes | 50 |
| Relationship edges | 72 |
| Thematic pillars | 6 |
| Secondary categories | 9 |

**Connection strength scale:**
- **Thematic (1)** — broad shared themes
- **Moderate (2)** — meaningful conceptual overlap
- **Strong (3)** — deep resonance; often cited as paired reads

---

## Thematic Pillars

| Pillar | Color | Description |
|---|---|---|
| Belonging | `#7c3aed` | Connection to community, identity, and collective experience |
| Relationship | `#db2777` | Human connection, care, and interpersonal life |
| Awe & Wonder | `#0284c7` | Curiosity, beauty, discovery, and appreciation |
| Purpose & Meaning | `#b45309` | Meaning, vocation, direction, and significance |
| Luck & Randomness | `#16a34a` | Chance, uncertainty, contingency, and decision-making |
| Philosophy & Spirituality | `#7e22ce` | Ethics, belief systems, spiritual reflection, and existential inquiry |

---

## Secondary Categories

Philosophy · Spirituality · Fiction · Non-fiction · Philanthropy · Book Club · Core/Essentials · Sally's Pick · Wisdom Traditions

---

## Tech Stack

| File | Library | Version |
|---|---|---|
| `gambrell-library-cytoscape.html` | [Cytoscape.js](https://js.cytoscape.org) | 3.29.2 |
| `gambrell-library-graph-v2.html` | [D3.js](https://d3js.org) | 7 |

Both files are self-contained — all data is embedded as JavaScript constants and dependencies are loaded from CDN. No installation, build tools, or backend required.

---

## Quick Start

```bash
# Clone and serve locally
git clone <repo-url>
cd cytoscape-test
python3 -m http.server 8080
# Open http://localhost:8080/gambrell-library-cytoscape.html
```
