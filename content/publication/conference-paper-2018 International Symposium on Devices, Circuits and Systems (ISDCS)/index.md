---
title: "Modeling the effect of variability on the timing response of CMOS inverter-transmission gate structure"
authors:
- Arvind Sharma
- Naushad Alam
- admin
- Bulusu Anand

date: "2018-03-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2018-06-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication:   2018 International Symposium on Devices, Circuits and Systems (ISDCS)
publication_short: IEEE ISDCS

abstract: This paper presents a novel delay model for Inverter followed by Transmission Gate (Inv-Tx) structure. Our model is novel in the sense that it considers the series stack effect along with the internal node voltage and parasitic capacitances while treating the Inv-Tx structure as a single entity. The model is derived for an unexplored scenario when a static signal is present at the input of Inverter and signal transition happens at the input of Tx gate of the Inv-Tx structure. Since we consider Inv-Tx structure as a single entity, the series stack effect is taken into account, thereby making the model more accurate. We also demonstrate the transformation of our delay model into the Logical Effort model. The derived model is verified for wide range of transistor sizes, signal transition times, and load capacitances. The proposed model shows good agreement with HSPICE simulation results. The maximum (average) error in the estimated delay compared to HSPICE simulations is only 4% (2%). The proposed model is also effective in accounting for process variability. The proposed model is employed for statistical analysis of 256×1 MUX structure. We observe that in the presence of variability, the proposed model predicts mean and standard deviation of the delay with a maximum error of only 3% and 4% respectively. Therefore, the presented model can also be used for statistical analysis to save simulation time significantly.

# Summary. An optional shortened abstract.
summary: This paper presents a novel delay model for Inverter followed by Transmission Gate (Inv-Tx) structure. Our model is novel in the sense that it considers the series stack effect along with the internal node voltage and parasitic capacitances while treating the Inv-Tx structure as a single entity.

# tags:
# - Source Themes
featured: true

links:
- name: Link
  url: https://ieeexplore.ieee.org/abstract/document/8379660
# url_pdf: http://eprints.soton.ac.uk/352095/1/Cushen-IMV2013.pdf
# url_code: '#'
# url_dataset: '#'
# url_poster: '#'
# url_project: ''
# url_slides: ''
# url_source: '#'
# url_video: '#'

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
projects:
- internal-project

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: example
---

<!-- {{% alert note %}}
Click the *Cite* button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /alert %}}

{{% alert note %}}
Click the *Slides* button above to demo Academic's Markdown slides feature.
{{% /alert %}} -->

<!-- Supplementary notes can be added here, including [code and math](https://sourcethemes.com/academic/docs/writing-markdown-latex/). -->

