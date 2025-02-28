---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}


# Non-archival publications:

- Dynamics of Moral Behaviour in Heterogeneous Populations of Learning Agents (Extended Abstract & Poster) @ [The 2025 Multi-disciplinary Conference on Reinforcement Learning and Decision Making (RLDM)](https://rldm.org/) - Trinity College Dublin, Dublin, Ireland. June 2025.
- Moral Alignment for AI Agents via Reinforcement Learning with Intrinsic Rewards (Poster) @ [UK Multi-Agent Systems Symposium (UK-MAS)](https://www.turing.ac.uk/events/uk-multi-agent-systems-symposium-2025-uk-mas) - The Alan Turing Institute, London, UK. March 2025.
