---
title: "Realizing Linear Controllers for Quadruped Robots on Planetary Terrains"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- Aditya Shirwatkar
- admin
- Bharadwaj Amrutur
- Shalabh Bhatnagar
- Ashitava Ghosal
- Shamrao
- Vinod Kumar
- Shishir Kolathaya
# Author notes (optional)


date: "2022-07-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *Conference on Automation Science and Engineering*
publication_short: In *CASE 2022*

abstract: Until now, planetary exploration has been accomplished with wheeled vehicles, which makes movement in highly complex, sandy, and sloping terrain incredibly tough. On the other hand, legged robots have come a long way in the last decade and have reached a stage of development where practical applications appear to be possible.  Legged robots can overcome the difficulties wheeled vehicles face when exploring harsh environments like impact craters to collect critical scientific data. As a result, there is a need to develop simple, stable walking controllers given the limited power resources and reserve maximum onboard compute for scientific equipment while exploring such regions. This work proposes a walking controller for legged robots that is computationally efficient at runtime for traversing planetary terrains. We realize this walking controller on our quadruped Stochlite, using learned linear feedback policies that modulate the end-foot trajectories. The proposed walking controller can traverse on various planetary terrains such as flat, sloped, rugged, loose, and lower-than-Earth gravity conditions in simulation environments. Our controller outperforms the baseline open-loop controller on such planetary terrains by reducing the slippage and increasing the stability. In addition, we have also provided preliminary hardware testing results of our controller.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: 'https://www.youtube.com/watch?v=La3y-xhWm1U&ab_channel=StochLabIISc'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
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