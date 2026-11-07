<!doctype html>
<html lang="fr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="description" content="Explorations sur la préhistoire et le potentiel scientifique de la RDC. Explorations of the prehistory and scientific potential of the DRC.">
<meta property="og:title" content="Le Grand Inconnu">
<meta property="og:description" content="Ishango, Katanda et la Semliki : ce qui est établi, débattu et hypothétique. / What is established, debated and hypothetical.">
<meta property="og:type" content="website">
<style>html{color-scheme:light}body{margin:0}img{max-width:100%}</style>
<title>Le Grand Inconnu</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500..800&family=IBM+Plex+Mono:wght@400;500&family=Source+Serif+4:ital,opsz,wght@0,8..60,400..700;1,8..60,400..600&display=swap">
<style>
/* Concept: a field notebook for the Semliki valley. Basalt-ash neutrals, lake-water teal as the single accent,
   laterite and ochre only as evidence labels. The one bold move is the tally of notches taken from the Ishango bone. */
:root {
  --bg: #E8ECEB;
  --surface: #F5F7F6;
  --fg: #1A2325;
  --muted: #55656A;
  --line: #C7D0CF;
  --lake: #166A72;
  --est-bg: #D3E6E7; --est-fg: #0E4C53;
  --deb-bg: #F0E5C4; --deb-fg: #5E4306;
  --hyp-bg: #F0DACF; --hyp-fg: #8A3417;
  --font-display: 'Bricolage Grotesque', 'Segoe UI', system-ui, sans-serif;
  --font-body: 'Source Serif 4', Georgia, 'Times New Roman', serif;
  --font-mono: 'IBM Plex Mono', ui-monospace, Menlo, Consolas, monospace;
}
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --bg: #11181A; --surface: #182224; --fg: #E3EBEA; --muted: #94A5A7; --line: #2B3A3C;
    --lake: #5CC2C9;
    --est-bg: #17383B; --est-fg: #8FDADF;
    --deb-bg: #3A3012; --deb-fg: #E8CD76;
    --hyp-bg: #3A2218; --hyp-fg: #F0A483;
    color-scheme: dark;
  }
}
:root[data-theme="dark"] {
  --bg: #11181A; --surface: #182224; --fg: #E3EBEA; --muted: #94A5A7; --line: #2B3A3C;
  --lake: #5CC2C9;
  --est-bg: #17383B; --est-fg: #8FDADF;
  --deb-bg: #3A3012; --deb-fg: #E8CD76;
  --hyp-bg: #3A2218; --hyp-fg: #F0A483;
  color-scheme: dark;
}

/* language switch: only the inactive language is hidden */
html:not([data-lang="en"]) [lang="en"] { display: none; }
html[data-lang="en"] [lang="fr"] { display: none; }

body {
  background: var(--bg);
  color: var(--fg);
  font-family: var(--font-body);
  font-size: 1.0625rem;
  line-height: 1.65;
  -webkit-text-size-adjust: 100%;
}
body::before {
  content: ""; position: fixed; inset: 0 0 auto; height: env(safe-area-inset-top, 0px);
  background: var(--bg); z-index: 10;
}
.wrap {
  max-width: 70rem; margin-inline: auto;
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
}
a { color: var(--lake); text-underline-offset: 0.2em; }
a:focus-visible, button:focus-visible { outline: 2px solid var(--lake); outline-offset: 3px; }
h1, h2, h3 { font-family: var(--font-display); text-wrap: balance; margin: 0; letter-spacing: -0.015em; }
p { margin: 0; }
.mono { font-family: var(--font-mono); font-size: 0.75rem; letter-spacing: 0.09em; text-transform: uppercase; color: var(--muted); }

/* top bar */
.bar { position: sticky; top: env(safe-area-inset-top, 0px); z-index: 5; background: var(--bg); border-bottom: 1px solid var(--line); }
.bar .wrap { display: flex; align-items: center; justify-content: space-between; gap: 1rem; padding-block: 0.7rem; }
.brand { font-family: var(--font-display); font-weight: 700; font-size: 1.2rem; letter-spacing: -0.02em; color: var(--fg); text-decoration: none; }
.langs { display: flex; border: 1px solid var(--line); }
.langs button {
  font-family: var(--font-mono); font-size: 0.75rem; letter-spacing: 0.08em; padding: 0.35rem 0.7rem;
  background: transparent; color: var(--muted); border: 0; cursor: pointer;
}
.langs button[aria-pressed="true"] { background: var(--lake); color: var(--bg); }

/* views */
.view { display: none; }
.view.on { display: block; }

/* hero */
.hero { padding-block: clamp(2.5rem, 7vw, 5rem) clamp(2rem, 5vw, 3.5rem); }
.hero h1 { font-weight: 700; font-size: clamp(2.3rem, 7.2vw, 4.8rem); line-height: 1.02; max-width: 16ch; margin-top: 1rem; }
.hero .lede { max-width: 38rem; margin-top: 1.4rem; font-size: 1.2rem; color: var(--muted); }
.tally-fig { margin: 2.6rem 0 0; max-width: 36rem; }
.tally { display: block; width: 100%; height: auto; }
.tally path { stroke: var(--lake); stroke-width: 2.6; stroke-linecap: round; fill: none; }
.tally text { fill: var(--muted); font-family: var(--font-mono); font-size: 18px; font-weight: 500; }
.tally-fig figcaption { margin-top: 0.5rem; font-size: 0.9rem; color: var(--muted); max-width: 34rem; }

/* explorations */
.section-head { display: flex; align-items: baseline; justify-content: space-between; gap: 1rem; border-top: 1px solid var(--line); padding-top: 1rem; }
.section-head h2 { font-size: 1.5rem; font-weight: 700; }
.explore { padding-block: 0 3rem; }
.cards { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 1.25rem; margin-top: 1.5rem; }
.card { background: var(--surface); border: 1px solid var(--line); padding: 1.3rem 1.3rem 1.4rem; display: flex; flex-direction: column; gap: 0.7rem; min-width: 0; }
.card h3 { font-size: 1.3rem; font-weight: 700; line-height: 1.2; }
.card p { color: var(--muted); font-size: 0.98rem; line-height: 1.55; }
.card.feature { grid-column: span 2; border-top: 4px solid var(--lake); color: var(--fg); text-decoration: none; }
.card.feature h3 { font-size: clamp(1.6rem, 3.4vw, 2.2rem); }
.card.feature p { color: var(--fg); font-size: 1.08rem; max-width: 34rem; }
.card.feature .go { margin-top: auto; font-family: var(--font-mono); font-size: 0.8rem; letter-spacing: 0.06em; color: var(--lake); }
a.card.feature:hover h3 { text-decoration: underline; text-decoration-color: var(--lake); text-underline-offset: 0.18em; }
.card.soon { background: transparent; border-style: dashed; }
.card.soon h3 { color: var(--muted); }

/* method */
.method { padding-block: 0 4rem; }
.method-grid { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 1.25rem; margin-top: 1.5rem; }
.method-grid > div { display: flex; flex-direction: column; gap: 0.6rem; align-items: flex-start; min-width: 0; }
.method-grid p { font-size: 0.98rem; line-height: 1.55; color: var(--muted); }
.method .intro { margin-top: 1rem; max-width: 40rem; }

/* evidence tags */
.tag { display: inline-block; font-family: var(--font-mono); font-size: 0.72rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; padding: 0.12rem 0.5rem; line-height: 1.5; vertical-align: 0.08em; }
.tag.est { background: var(--est-bg); color: var(--est-fg); }
.tag.deb { background: var(--deb-bg); color: var(--deb-fg); }
.tag.hyp { background: var(--hyp-bg); color: var(--hyp-fg); }

/* article */
.article { padding-block: clamp(1.5rem, 4vw, 3rem) 4rem; }
.back { font-family: var(--font-mono); font-size: 0.8rem; letter-spacing: 0.06em; }
.a-head { margin-top: 2rem; max-width: 46rem; }
.a-head h1 { font-size: clamp(2rem, 5.6vw, 3.6rem); font-weight: 700; line-height: 1.05; margin-top: 0.8rem; }
.a-head .lede { margin-top: 1.2rem; font-size: 1.2rem; color: var(--muted); }
.a-head .meta { margin-top: 1.2rem; }
.legend { display: flex; flex-wrap: wrap; gap: 0.5rem 1rem; margin-top: 1.4rem; padding-top: 1rem; border-top: 1px solid var(--line); font-size: 0.9rem; color: var(--muted); }
.legend span.item { display: inline-flex; align-items: center; gap: 0.45rem; }
.prose { max-width: 42rem; margin-top: 2.2rem; }
.prose h2 { font-size: 1.7rem; font-weight: 700; line-height: 1.15; margin-top: 3rem; padding-top: 1.1rem; border-top: 1px solid var(--line); }
.prose h2:first-child { margin-top: 0; border-top: 0; padding-top: 0; }
.prose p { margin-top: 1rem; }
.prose ul, .prose ol { margin: 1rem 0 0; padding-left: 1.3rem; display: grid; gap: 0.55rem; }
.prose li::marker { color: var(--lake); }
.prose strong { font-weight: 650; }
.prose .tally-fig { margin-top: 1.8rem; }

/* stages diagram */
.stages-fig { margin: 2rem 0 0; }
.stages { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); border: 1px solid var(--line); }
.stage { padding: 1rem 1rem 1.1rem; display: flex; flex-direction: column; gap: 0.4rem; position: relative; min-width: 0; }
.stage + .stage { border-left: 1px solid var(--line); }
.stage .mono { color: inherit; opacity: 0.85; }
.stage b { font-family: var(--font-display); font-size: 1.1rem; line-height: 1.2; font-weight: 650; }
.stage span.d { font-size: 0.92rem; line-height: 1.45; }
.stage.h { background: var(--est-bg); color: var(--est-fg); }
.stage.v { background: var(--deb-bg); color: var(--deb-fg); }
.stages-fig figcaption { margin-top: 0.6rem; font-size: 0.9rem; color: var(--muted); }

.hypo li { padding-left: 0.2rem; }
.sources { font-size: 0.95rem; line-height: 1.5; }
.sources .note { color: var(--muted); }
.sources li { overflow-wrap: anywhere; }

footer { border-top: 1px solid var(--line); }
footer .wrap { padding-block: 1.4rem 2.4rem; }
footer p { font-size: 0.85rem; color: var(--muted); max-width: 40rem; }

@media (max-width: 760px) {
  .cards, .method-grid { grid-template-columns: minmax(0, 1fr); }
  .card.feature { grid-column: auto; }
  .stages { grid-template-columns: minmax(0, 1fr); }
  .stage + .stage { border-left: 0; border-top: 1px solid var(--line); }
}
@media (prefers-reduced-motion: no-preference) {
  .card.feature h3 { transition: color 0.15s; }
}
</style>

<script>
(function () {
  var lang = 'fr';
  try {
    var s = localStorage.getItem('gi-lang');
    if (s === 'fr' || s === 'en') { lang = s; }
    else if ((navigator.language || '').slice(0, 2) === 'en') { lang = 'en'; }
  } catch (e) {}
  document.documentElement.setAttribute('data-lang', lang);
})();
</script>

</head>
<body>
<header class="bar">
  <div class="wrap">
    <a class="brand" href="#accueil">Le Grand Inconnu</a>
    <div class="langs" role="group" aria-label="Langue / Language">
      <button type="button" id="lang-fr" data-setlang="fr" aria-pressed="true">FR</button>
      <button type="button" id="lang-en" data-setlang="en" aria-pressed="false">EN</button>
    </div>
  </div>
</header>

<main>
<!-- ============ HOME ============ -->
<div class="view on" id="view-accueil">
  <section class="hero wrap">
    <p class="mono"><span lang="fr">Nord-Kivu, République démocratique du Congo</span><span lang="en">North Kivu, Democratic Republic of the Congo</span></p>
    <h1><span lang="fr">Un pays dont l'histoire reste à chercher.</span><span lang="en">A country whose history is still waiting to be found.</span></h1>
    <p class="lede">
      <span lang="fr">Des explorations sur la préhistoire, la nature et le potentiel scientifique de la RDC. Chaque texte sépare ce qui est établi, ce qui est débattu et ce que nous proposons comme hypothèse.</span>
      <span lang="en">Explorations of the prehistory, nature and scientific potential of the DRC. Each text separates what is established, what is debated and what we propose as a hypothesis.</span>
    </p>
    <figure class="tally-fig">
      <svg class="tally" viewBox="0 0 560 94" role="img" aria-label="Soixante entailles en quatre groupes de 11, 21, 19 et 9"></svg>
      <figcaption>
        <span lang="fr">Une série d'entailles de l'os d'Ishango : 60 marques en quatre groupes de 11, 21, 19 et 9. Il y a environ 20&nbsp;000 ans, quelqu'un a gravé cela au bord d'un lac.</span>
        <span lang="en">One series of notches on the Ishango bone: 60 marks in four groups of 11, 21, 19 and 9. About 20,000 years ago, someone carved this beside a lake.</span>
      </figcaption>
    </figure>
  </section>

  <section class="explore wrap">
    <div class="section-head">
      <h2><span lang="fr">Explorations</span><span lang="en">Explorations</span></h2>
      <span class="mono"><span lang="fr">1 publiée</span><span lang="en">1 published</span></span>
    </div>
    <div class="cards">
      <a class="card feature" href="#ishango">
        <span class="mono"><span lang="fr">Préhistoire · Premier jet</span><span lang="en">Prehistory · First draft</span></span>
        <h3><span lang="fr">Ishango et la Semliki</span><span lang="en">Ishango and the Semliki</span></h3>
        <p>
          <span lang="fr">Un os gravé d'environ 20&nbsp;000 ans, des harpons de pêche d'environ 90&nbsp;000 ans, un lac, des volcans et une plage qui s'érode.</span>
          <span lang="en">An engraved bone about 20,000 years old, fishing harpoons about 90,000 years old, a lake, volcanoes and a beach that is wearing away.</span>
        </p>
        <span class="go"><span lang="fr">Lire l'exploration →</span><span lang="en">Read the exploration →</span></span>
      </a>
      <div class="card soon">
        <span class="mono"><span lang="fr">En préparation</span><span lang="en">In preparation</span></span>
        <h3><span lang="fr">Kongo Central et Mayombe</span><span lang="en">Kongo Central and Mayombe</span></h3>
        <p>
          <span lang="fr">Ce que la géologie dit des chances de trouver des fossiles dans l'ouest du pays.</span>
          <span lang="en">What geology says about the chances of finding fossils in the west of the country.</span>
        </p>
      </div>
      <div class="card soon">
        <span class="mono"><span lang="fr">En préparation</span><span lang="en">In preparation</span></span>
        <h3><span lang="fr">Animaux et plantes uniques</span><span lang="en">Unique animals and plants</span></h3>
        <p>
          <span lang="fr">Bonobo, okapi, poissons des grands lacs, plantes encore peu étudiées.</span>
          <span lang="en">Bonobo, okapi, fish of the great lakes, plants still little studied.</span>
        </p>
      </div>
    </div>
  </section>

  <section class="method wrap">
    <div class="section-head">
      <h2><span lang="fr">Comment lire ce site</span><span lang="en">How to read this site</span></h2>
    </div>
    <p class="intro">
      <span lang="fr">Chaque affirmation porte une étiquette, pour que le lecteur sache sur quoi elle s'appuie.</span>
      <span lang="en">Every statement carries a label, so the reader knows what it rests on.</span>
    </p>
    <div class="method-grid">
      <div>
        <span class="tag est"><span lang="fr">Établi</span><span lang="en">Established</span></span>
        <p><span lang="fr">Confirmé par plusieurs sources publiées, par exemple des fouilles et des publications scientifiques.</span><span lang="en">Confirmed by several published sources, such as excavations and scientific papers.</span></p>
      </div>
      <div>
        <span class="tag deb"><span lang="fr">Débattu</span><span lang="en">Debated</span></span>
        <p><span lang="fr">Les chercheurs ne sont pas d'accord, ou la méthode utilisée a des limites connues.</span><span lang="en">Researchers disagree, or the method used has known limits.</span></p>
      </div>
      <div>
        <span class="tag hyp"><span lang="fr">Hypothèse</span><span lang="en">Hypothesis</span></span>
        <p><span lang="fr">Une idée de ce site, construite à partir des sources, mais non démontrée.</span><span lang="en">An idea from this site, built on the sources but not proven.</span></p>
      </div>
    </div>
  </section>
</div>

<!-- ============ ARTICLE: ISHANGO ============ -->
<div class="view" id="view-ishango">
  <article class="article wrap">
    <a class="back" href="#accueil"><span lang="fr">← Toutes les explorations</span><span lang="en">← All explorations</span></a>

    <header class="a-head">
      <p class="mono"><span lang="fr">Exploration · Préhistoire</span><span lang="en">Exploration · Prehistory</span></p>
      <h1><span lang="fr">Ishango et la Semliki</span><span lang="en">Ishango and the Semliki</span></h1>
      <p class="lede">
        <span lang="fr">Des pêcheurs vivaient au bord d'un lac et d'une rivière, sur un terrain secoué par des volcans et par des changements de climat. Pourquoi s'installaient-ils, partaient-ils, revenaient-ils ?</span>
        <span lang="en">Fishers lived beside a lake and a river, on ground shaken by volcanoes and climate change. Why did they settle, leave and come back?</span>
      </p>
      <p class="meta mono"><span lang="fr">Premier jet · 7 novembre 2026</span><span lang="en">First draft · 7 November 2026</span></p>
      <div class="legend">
        <span class="item"><span class="tag est"><span lang="fr">Établi</span><span lang="en">Established</span></span><span lang="fr">sources concordantes</span><span lang="en">sources agree</span></span>
        <span class="item"><span class="tag deb"><span lang="fr">Débattu</span><span lang="en">Debated</span></span><span lang="fr">avis partagés</span><span lang="en">views differ</span></span>
        <span class="item"><span class="tag hyp"><span lang="fr">Hypothèse</span><span lang="en">Hypothesis</span></span><span lang="fr">notre déduction</span><span lang="en">our inference</span></span>
      </div>
    </header>

    <div class="prose">

      <!-- 1 -->
      <h2><span lang="fr">Un pays dont l'histoire n'a pas encore été cherchée</span><span lang="en">A country whose history has not yet been searched for</span></h2>
      <p lang="fr">La RDC passe pour un pays pauvre en traces de la préhistoire, mais la vallée de la Semliki dit le contraire : deux sites voisins, Ishango et Katanda, ont livré des objets de pêche et de comptage parmi les plus anciens d'Afrique.</p>
      <p lang="en">The DRC is often seen as poor in prehistoric traces, yet the Semliki valley says otherwise: two neighbouring sites, Ishango and Katanda, have produced fishing and counting objects among the oldest in Africa.</p>
      <p lang="fr">Ce texte réunit ce que les sources établissent sur ces deux sites, ce qui reste débattu, et ce que nous proposons comme hypothèses. Les hypothèses sont les nôtres : elles ne sont pas prouvées.</p>
      <p lang="en">This text gathers what the sources establish about these two sites, what remains debated, and what we propose as hypotheses. The hypotheses are ours: they are not proven.</p>

      <!-- 2 -->
      <h2><span lang="fr">Ishango : ce qui est établi</span><span lang="en">Ishango: what is established</span></h2>
      <p lang="fr"><span class="tag est">Établi</span> Ishango est un site de pêcheurs au bord du lac Édouard, à la sortie de la Semliki, dans le parc national des Virunga.</p>
      <p lang="en"><span class="tag est">Established</span> Ishango is a fishing site on the shore of Lake Edward, where the Semliki River leaves the lake, inside Virunga National Park.</p>
      <ul lang="fr">
        <li>Le site a été repéré en 1935 par le zoologue Hubert Damas, puis fouillé en 1950 par le géologue belge Jean de Heinzelin.</li>
        <li>Les fouilles ont montré des traces de poteaux plantés dans le sol : les restes d'anciennes cabanes.</li>
        <li>On y a trouvé des harpons en os, des pointes barbelées, des outils en quartz et des restes de poissons, d'hippopotames, de buffles et d'antilopes.</li>
        <li>Le premier village a été enseveli par une éruption volcanique. Le champ volcanique de Katwe se trouve tout près.</li>
        <li>Les os ont survécu parce que les cendres volcaniques les ont fossilisés très vite, avant qu'ils ne se dégradent. Ishango est donc un cas de conservation rare, dû au volcan.</li>
        <li>Les restes humains d'Ishango appartiennent à <em>Homo sapiens</em>.</li>
      </ul>
      <ul lang="en">
        <li>The site was spotted in 1935 by the zoologist Hubert Damas, then excavated in 1950 by the Belgian geologist Jean de Heinzelin.</li>
        <li>The excavations revealed traces of posts driven into the ground: the remains of former huts.</li>
        <li>Finds include bone harpoons, barbed points, quartz tools and remains of fish, hippopotamus, buffalo and ant
