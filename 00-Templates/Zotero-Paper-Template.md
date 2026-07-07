---
title: "{{title}}"
authors: [{% for author in creators %}"{% if author.firstName %}{{author.firstName}} {% endif %}{{author.lastName}}"{% if not loop.last %}, {% endif %}{% endfor %}]
year: {% if date %}{{date | format("YYYY")}}{% else %}""{% endif %}
venue: "{{publicationTitle}}"
keywords: [{% for tag in tags %}"{{tag.tag}}"{% if not loop.last %}, {% endif %}{% endfor %}]
status: "❣️todo"
rating: "⭐⭐⭐⭐⭐"
gap: ""
zotero_link: "{{backlink}}"
created: "{{dateAdded | format('YYYY-MM-DD')}}"
---

# {{title}}

> [!INFO] **Citation Info**
> * **Authors:** {% for author in creators %}{% if author.firstName %}{{author.firstName}} {% endif %}{{author.lastName}}{% if not loop.last %}, {% endif %}{% endfor %}
> * **Year:** {% if date %}{{date | format("YYYY")}}{% else %}Unknown{% endif %}
> * **Venue:** {{publicationTitle}}
> * **Zotero Link:** [Open in Zotero Desktop]({{backlink}})
> * **Attachments:** {% for attachment in attachments %}[{{attachment.title}}]({{attachment.desktopLink}}) {% endfor %}

> **Abstract:** 
> {{abstractNote}}

---

## 📝 Review Notes

### 1. Problem
*What problem is the paper trying to solve? Why are current methods not good enough?*

### 2. Motivation
*What is the key message? Why is this research important and urgent?*

### 3. Main Idea
*What is the core idea or approach used to solve the problem?*

### 4. Contribution
*What are the main contributions of this paper (e.g., new algorithm, new dataset, system design, theoretical proof)?*

### 5. Method
*Detailed implementation details (System architecture, steps, evaluation setup).*

### 6. Interesting Ideas
*Interesting ideas, tools, or techniques from the paper that we can learn or reuse.*

### 7. Strength
*Main strengths of the paper's solution.*

### 8. Weakness
*Main weaknesses, limitations, or simplified assumptions made in the paper.*

### 9. Research Gap (of this paper)
*Unsolved gaps or potential improvements left by this paper.*

### 10. Future Work
*Future research directions suggested by the authors.*

---

## 🎨 Highlights & Annotations
*Your highlights and comments from the Zotero PDF Reader will be automatically loaded here:*

{% for annotation in annotations %}
{% if annotation.annotatedText %}
> [!quote] **Highlight (Page {{annotation.pageLabel}})**
> {{annotation.annotatedText}}
> 
> *Your Comment:* {{annotation.comment}}
{% endif %}
{% endfor %}
