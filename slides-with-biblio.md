---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<audio id="bg-music" src="media/audio/sb.m4a" loop></audio>

<div id="audio-credit"
     style="position: absolute; bottom: 40px; right: 20px; font-size: 0.6em; opacity: 0.6;">
  Music: “Adrift” by Scott Buckley (CC BY 4.0)
</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('bg-music');
    const credit = document.getElementById('audio-credit');

    // hide credit by default
    credit.style.display = 'none';

    const test = new Audio('media/audio/bgm.mp3');

    test.addEventListener('canplaythrough', () => {
      // bgm.mp3 exists → use it, keep credit hidden
      audio.src = 'media/audio/bgm.mp3';
    }, { once: true });

    test.addEventListener('error', () => {
      // bgm.mp3 missing → sb.m4a will play → show credit
      credit.style.display = 'block';
    }, { once: true });

    document.addEventListener('click', () => {
      if (Reveal.getIndices().h === 0) {
        audio.volume = 0.5;
        audio.play();
      }
    }, { once: true });

    Reveal.on('slidechanged', (event) => {
      if (event.indexh > 0) { audio.pause(); }
      else { audio.play(); }
    });
  });
</script>

:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Machine 1 vs. Machine 2: Part Resistance

We performed an independent samples t-test to compare the part resistance between Machine 1 and Machine 2 when `Pressure` is 100 and `Temperature` is 303. The results are visualized below using a boxplot.

**T-Test Results:**
* **t-statistic:** (See R output)
* **p-value:** (See R output)

The t-test will indicate if there is a statistically significant difference in part resistance between the two machines under these conditions.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine_part_resistance_boxplot.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Machine 1 vs. Machine 2: Part Resistance

We performed an independent samples t-test to compare the part resistance between Machine 1 and Machine 2 when `Pressure` is 100 and `Temperature` is 303. The results are visualized below using a boxplot.

**T-Test Results:**
* **t-statistic:** (See R output)
* **p-value:** (See R output)

The t-test will indicate if there is a statistically significant difference in part resistance between the two machines under these conditions.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine_part_resistance_boxplot.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Machine 1 vs. Machine 2: Part Length

We performed an independent samples t-test to compare the part length between Machine 1 and Machine 2 when `Pressure` is 100 and `Temperature` is 303. The results are visualized below using a boxplot.

**T-Test Results:**
* **t-statistic:** (See R output)
* **p-value:** (See R output)

The t-test will indicate if there is a statistically significant difference in part length between the two machines under these conditions.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine_part_length_boxplot.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

-----

:::: {.columns}
::: {.column width="50%"}
### Machine 1 vs. Machine 2: Part Resistance (P=300, T=373)

We performed an independent samples t-test to compare the part resistance between Machine 1 and Machine 2 when `Pressure` is 300 and `Temperature` is 373. The results are visualized below using a boxplot.

**T-Test Results:**
* **t-statistic:** (See R output)
* **p-value:** (See R output)

The t-test will indicate if there is a statistically significant difference in part resistance between the two machines under these conditions.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine_part_resistance_boxplot_p300_t373.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

-----

:::: {.columns}
::: {.column width="50%"}
### Machine 1 vs. Machine 2: Part Length (P=300, T=373)

We performed an independent samples t-test to compare the part length between Machine 1 and Machine 2 when `Pressure` is 300 and `Temperature` is 373. The results are visualized below using a boxplot.

**T-Test Results:**
* **t-statistic:** (See R output)
* **p-value:** (See R output)

The t-test will indicate if there is a statistically significant difference in part length between the two machines under these conditions.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine_part_length_boxplot_p300_t373.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---
# Bibliography
<div id="refs"></div>
