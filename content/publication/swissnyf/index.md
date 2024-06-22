---
title: "SwissNyF: Tool Grounded LLM Agents for Black Box Setting"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- Dhruv Jain
- Eshaan Agarwal
- Raunak Pandey


date: "2024-02-15T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2024-02-15T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *ICLR LLM Agents Workshop*
publication_short: In *LLMAgent ICLR*

abstract: While Large Language Models (LLMs) have demonstrated enhanced capabilities in function-calling, these advancements primarily rely on accessing the functions’ responses. This methodology is practical for simpler APIs but faces scalability issues with irreversible APIs that significantly impact the system, such as a database deletion API. Similarly, processes requiring extensive time for each API call and those necessitating forward planning, like automated action pipelines, present complex challenges. Furthermore, scenarios often arise where a generalized approach is needed because algorithms lack direct access to the specific implementations of these functions or secrets to use them. Traditional tool planning methods are inadequate in these cases, compelling the need to operate within black-box environments. Unlike their performance in tool manipulation, LLMs excel in black-box tasks, such as program synthesis. Therefore, we harness the program synthesis capabilities of LLMs to strategize tool usage in black-box settings, ensuring solutions are verified prior to implementation. We introduce TOPGUN, an ingeniously crafted approach leveraging program synthesis for black box tool planning. Accompanied by SwissNYF, a comprehensive suite that integrates black-box algorithms for planning and verification tasks, addressing the aforementioned challenges and enhancing the versatility and effectiveness of LLMs in complex API interactions. 

# Summary. An optional shortened abstract.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://hex-plex.github.io/publication/swissnyf'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Illustration of Pipeline'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.


# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
---
