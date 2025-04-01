<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->




<!-- PROJECT LOGO -->
<br />
<div align="center">
  </a>

  <h3 align="center">Segmented Generation & Trait-Based Systems</h3>

  <p align="center">
    This project visualizes identity by transforming a user's MBTI, moral alignment, and favorite color into layered Voronoi diagrams. Through recursive subdivision and trait-driven visual rules, the system encodes psychological attributes into a unique generative portrait.
<!--     <br />
    <a href="https://github.com/manguyen0017/4-comma-Assignment_01/blob/main/pdf/Yonkoma__The_Headaches_of_Iterative_AI_Generation.pdf"><strong>Link to PDF Report»</strong></a>
    <br /> -->
    <br />
    <a href="https://manguyen.myportfolio.com/">Michael Nguyen</a>
    &middot;
    <a href="https://sites.google.com/view/viza626/home">VIZA 626</a>
  </p>
</div>

[![Voronoi][images-fig1]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig1.png)

Figure 1. Full output visual of one complete generative portrait progressing from favorite color to deepest sublayer.

<!-- Abstract -->
## Abstract
This generative art project visualizes identity using layered Voronoi diagrams that interpret a user’s MBTI, moral alignment, and favorite color into nested geometric compositions. Each trait modifies how cells are spatially positioned, how their colors evolve across depths, and how moral values shift over generational inheritance. Inspired by psychological visualizations and procedural aesthetics, the system offers a customizable personality portrait.

<!-- Introduction and Related Works -->
## Introduction and Related Works

Generative systems that integrate psychological models have seen increasing interest for personalized design, often borrowing from personality theory and procedural visualization. Recent work has investigated how identity can shape creative output through data-informed inputs.

Guckelsberger et al. (2017) introduced explainable AI systems for creative co-design, allowing deeper interpretation of procedural generative tools [1]. Similarly, Abdul et al. (2018) reviewed explainability in AI systems as a means of increasing user trust and understanding [2]. These ideas inform how layered personality traits can be visualized.

Most recently, research by [Electronics Journal] (2024) highlights how MBTI and Big Five personality traits can influence generative AI systems for more meaningful and emotionally resonant outputs [4]. This supports the decision to blend personality psychology with algorithmic visual structures.

Previous systems by Holtzman (2016) explored aesthetic computation via user-controlled input mappings [3], echoing our aim to transform preference into generative form. This system extends such mappings into a trait-driven Voronoi space.


### Built With
* ChatGPT
* P5.js

## Methodology

The generator was implemented in p5.js with d3.voronoi to create layered Voronoi diagrams. Users input their favorite color (HSV), MBTI code, and moral alignment (e.g., Chaotic Good). These values drive the construction of three nested diagram layers, each shaped by identity traits.

[![Voronoi][images-fig2]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig2.png)

Figure 2. A visual overview of how HSV color, MBTI code, and moral alignment collectively influence color, pattern structure, and visual behavior of the generative system.

[![Voronoi][images-fig3]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig3.png)

Figure 3. Pipeline stages from selected HSV input to final nested Voronoi output, showing how personality and color traits evolve across layers.

### Layer Structure & Pipeline

* Base Layer: 4 Voronoi cells based on MBTI letters. Each letter influences cell position and shifts hue (e.g., I/E = ±20°).
* Sublayer 2: Each base cell spawns 3 smaller cells. Traits (e.g., Good = +1, Evil = -1) mutate per cell with probabilistic inheritance.
* Sublayer 3: Each sublayer 2 cell creates 2 more cells. Traits inherit again with a 70% chance to persist, 20% to neutralize, and 10% to flip.

[![Voronoi][images-fig4]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig4.png)

Figure 4. MBTI pairings and their additive influence on hue; INFP (cooler) and ESTJ (warmer) demonstrate contrasting shifts.

[![Voronoi][images-fig5]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig5.png)

Figure 5. Lawful, Neutral, and Chaotic alignment styles shown across all layers. Lawful maintains order, Neutral blends evenly, and Chaotic introduces irregular variance.

[![Voronoi][images-fig6]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig6.png)

Figure 6. Good, Neutral, and Evil alignment influences on color vibrancy. Good brightens, Evil darkens, and Neutral balances saturation.


### Color Logic

Color is represented in HSB mode:
* Hue starts from favorite color and gradually shifts based on MBTI and depth.
* Saturation/Brightness are modified by alignment (e.g., Evil darkens, Good brightens).

Randomness is locked to a user-defined seed for consistent results. Users can toggle layers, traits, and highlights in the UI.

[![Voronoi][images-fig7]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig7.png)

Figure 7. Trait inheritance math showing the probability of child cells adopting Good, Neutral, or Evil values from parents. Visualized numerically in layer output (+1, 0, -1, etc).

### Technical Highlights

* Trait inheritance probabilities: Good/Evil pass down with 70% chance, 20% stay Neutral, 10% flip.
* Chaotic alignments introduce positional noise and irregular clustering.
* Hue adjustments intensify with depth but are clamped for visual consistency.

### Tools & Implementation

I used ChatGPT as a coding assistant to:
* Debug logic issues and restructure messy code.
* Translate abstract systems (e.g., alignment inheritance) into functional code.
* Refactor components into reusable class-based architecture.

Technical Features:
* Deterministic seed-based generation
* Trait-based color blending and structure.
* Chaotic alignment introduces irregular positioning.
* UI toggles for interactive exploration.

Libraries Used:
p5.js · p5.sound · d3.v5

[![Voronoi][images-fig8]](https://github.com/manguyen0017/Segmented-Generative-Pipeline-Assignment_02/blob/main/images/fig8.png)

Figure 8. Randomized exploration examples.

## Result and Future Work
This system generates abstract portraits that uniquely visualize a user's identity through color progression, shape variation, and trait inheritance. Moral alignment influences saturation and brightness—Good brightens cells, Evil darkens them—while MBTI letters introduce hue shifts and structural variation in seed placement. Chaotic alignments introduce spatial irregularity, contrasting with lawful symmetry. The result is a layered, symbolic portrait that evolves from user input into a generative form.

Each layer—base, sublayer 2, and sublayer 3—adds depth both visually and conceptually. Traits are inherited probabilistically across layers, creating continuity or divergence based on moral logic. This layering not only reveals personality structure but also invites interpretation through color, structure, and transformation over depth.


### Future Work
* Integrate simulation rules inspired by Conway’s Game of Life to allow cell growth/decay.
* Animate trait inheritance and diagram evolution as a time-based transformation.
* Replace current geometric shapes with smoother, curved cells using Bézier-based styling.
* Unintended Failure – Fixing one issue causes another absurd problem.


## Conclusion
Through procedural layering, trait inheritance, and color transformation, this project encodes identity into generative visuals. It not only explores the aesthetic effects of personality and alignment, but proposes a compelling approach to personal data portraiture—where generative systems become reflective mirrors of user input rather than arbitrary aesthetics.



<!-- Bibliography -->
## Bibliography 
[1] Guckelsberger, C., Salge, C., & Colton, S. (2017). Addressing the “Why?” in Computational Creativity: A Non-Anthropocentric, Minimal Model of Intentional Creative Agency. Proceedings of the Eighth International Conference on Computational Creativity.

[2] Abdul, A., Vermeulen, J., Wang, D., Lim, B. Y., & Kankanhalli, M. (2018). Trends and Trajectories for Explainable, Accountable and Intelligible Systems: An HCI Research Agenda. Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems.

[3] Holtzman, H. (2016). The Art of Interaction: What HCI Can Learn from Interactive Art. Interactions, 23(2), 44–49.

[4] Electronics. (2024). Integrating Generative AI with Personality Models. Electronics, 13(23), 4751. https://www.mdpi.com/2079-9292/13/23/4751

<!-- CONTACT -->
## Contact

Michael Nguyen - manguyen@tamu.edu

Personal Website: [manguyen.myportfolio.com](https://manguyen.myportfolio.com)




<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

This work is submitted as part of Assignment 1 for the VIZA 626 course at Texas A&M University, under the instruction of Professor You-Jin Kim, during the Spring 2025 semester.

VIZA 626 Class Website: [https://sites.google.com/view/viza626/](https://sites.google.com/view/viza626/home)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[images-fig1]: images/fig1.png
[images-fig2]: images/fig2.png
[images-fig3]: images/fig3.png
[images-fig4]: images/fig4.png
[images-fig5]: images/fig5.png
[images-fig6]: images/fig6.png
[images-fig7]: images/fig7.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
