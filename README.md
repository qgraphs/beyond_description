# Beyond Description

Interactive result charts for **"Beyond Description: Modelling Iconicity and
Sensorimotor Grounding in Museum Audio Description"** — Szymon Pindur & Agata
Hołobut, EADH 2026.

Live: https://qgraphs.github.io/beyond_description/

| page | what it shows |
|---|---|
| `lancaster.html` | six perceptual channels, rated by dictionary lookup |
| `binder.html` | the same channels, rated in context by a fine-tuned BERT model |
| `iconicity.html` | iconicity overall and within each word class |

Hover any cell to see the vocabulary that produces it; click to pin, Escape to
close. The word lists are direction-aware — a cell above the corpus mean shows
the words pushing it up, one below shows those pushing it down.

`static/` holds matching PNGs for the slide deck; link each image to its page.
It also holds `iconicity_vs_lexicon.png`, a standalone figure comparing the
corpus against the Winter iconicity lexicon.

## Method in one paragraph

404 English museum audio descriptions across seven movements, modelled at token
level as `rating ~ Movement + (1|text) + (1|Painter) + (1|Institution)` in lme4,
with Movement sum-coded so each coefficient is a deviation from the corpus mean.
Ratings are corpus-referenced percentiles. Per-word shares are the regression's
implied weights (Chattopadhyay & Zubizarreta, *Biometrika* 2023) aggregated by
lemma; they sum to the fitted deviation exactly, and reproduce leave-one-lemma-out
refitting at r = .978. Stability percentages come from a cluster bootstrap over
painters.

Funded by the National Science Centre, Poland — *Reverberations: Museum Audio
Description and Intersemiotic Translation Practices*, 2024/53/B/HS2/04292.
