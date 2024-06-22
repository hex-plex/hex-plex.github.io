---
title: "LatentCBF: Control Barrier Definition on Latent Space"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- Qin Lin
- John M. Dolan


date: "2023-01-03T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *Conference on Decision and Control*
publication_short: In *CDC 2023*

abstract: Safe execution of policies is crucial for an autonomous system. A popular choice for safety guarantees is CBF(Control Barrier Function). Traditional control barrier functions rely on explicit knowledge of the system dynamics and constraints. Hence We propose LatentCBF (LCBF), acontrol barrier function definition on the latent space of the agent’s observation. LCBFs exploit the properties of deep neural networks to learn a representation of the system used to construct a barrier function. This function acts as a safety constraint that the control signal must satisfy, regardless ofthe complex system dynamics and uncertainties. By learning this constraint in a latent space, LCBFs have the potential to enable the safe operation of complex systems in a wide range of applications, from autonomous driving to robotics and beyond.
# Summary. An optional shortened abstract.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://hex-plex.github.io/publication/latentcbf'
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
  caption: 'Complete Pipeline'
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
