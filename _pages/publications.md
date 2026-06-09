---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

{% if page.author and site.data.authors[page.author] %}
  {% assign author = site.data.authors[page.author] %}{% else %}{% assign author = site.author %}
{% endif %}
{% if author.googlescholar %}
You can also find my publications on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

<p>* indcates co-first author, # indicates co-corresponding author.</p> 

<!-- bibtex-js -->
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/pcooksey/bibtex-js@1.0.0/src/bibtex_js.js"></script>
<bibtex src="../files/mypubs.bib"></bibtex>

<style>
/* ---- Publications List ---- */
#bibtex_display{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,sans-serif;max-width:800px;margin:0 auto}
.bibtex_template{display:none!important}

/* year group */
.pub-year-group{margin-bottom:2.4rem}
.pub-year-label{font-size:14px;font-weight:500;color:#185FA5;letter-spacing:.04em;
  padding-bottom:5px;border-bottom:2px solid #378ADD;margin-bottom:14px;display:inline-block;min-width:52px}

/* entry row */
.pub-entry{display:flex;gap:14px;padding:13px 0;border-bottom:.5px solid rgba(0,0,0,.09);align-items:flex-start}
.pub-entry:last-child{border-bottom:none}

/* left badge */
.pub-badge{flex-shrink:0;width:56px;text-align:center;padding-top:3px}
.pub-badge-inner{font-size:9.5px;font-weight:500;padding:3px 5px;border-radius:4px;
  display:inline-block;line-height:1.45;letter-spacing:.04em;white-space:nowrap}
.badge-conf  {background:#E6F1FB;color:#185FA5}
.badge-jour  {background:#EAF3DE;color:#3B6D11}
.badge-workshop{background:#EEEDFE;color:#3C3489}
.badge-preprint{background:#FAEEDA;color:#854F0B}

/* right body */
.pub-body{flex:1;min-width:0}
.pub-title{font-size:14.5px;font-weight:500;color:#1a1a1a;line-height:1.42;margin-bottom:4px}
.pub-authors{font-size:13px;color:#555;margin-bottom:3px;line-height:1.55}
.pub-authors .me{font-weight:600;color:#1a1a1a;text-decoration:underline;text-underline-offset:2px;text-decoration-color:#378ADD}
.pub-authors .co-first{font-size:10.5px;vertical-align:super;color:#993C1D;margin-left:1px;line-height:1}
.pub-authors .co-corresp{font-size:10.5px;vertical-align:super;color:#185FA5;margin-left:1px;line-height:1}
.pub-venue{font-size:12.5px;color:#444;margin-bottom:8px;line-height:1.4}
.pub-venue em{color:#185FA5;font-style:normal;font-weight:500}

/* link buttons */
.pub-links{display:flex;flex-wrap:wrap;gap:5px;align-items:center}
.pl{font-size:11px;padding:2px 8px;border-radius:4px;border:.5px solid;text-decoration:none;
  cursor:pointer;background:white;display:inline-flex;align-items:center;transition:background .12s}
.pl:hover{opacity:.85}
.pl-pdf  {color:#993C1D;border-color:#D85A30}.pl-pdf:hover {background:#FAECE7}
.pl-arx  {color:#534AB7;border-color:#7F77DD}.pl-arx:hover {background:#EEEDFE}
.pl-code {color:#0F6E56;border-color:#1D9E75}.pl-code:hover{background:#E1F5EE}
.pl-poster{color:#185FA5;border-color:#378ADD}.pl-poster:hover{background:#E6F1FB}
.pl-doi  {color:#5F5E5A;border-color:#888780}.pl-doi:hover {background:#F1EFE8}
.pl-bib  {color:#5F5E5A;border-color:#888780;cursor:pointer}.pl-bib:hover{background:#F1EFE8}

/* expandable sections */
.pub-bib-raw{display:none;margin-top:8px;padding:10px 13px;border-radius:6px;
  background:#f5f4ef;font-family:"SFMono-Regular",Consolas,"Liberation Mono",Menlo,monospace;
  font-size:11px;color:#444;white-space:pre-wrap;line-height:1.55;overflow-x:auto}
.pub-bib-raw.open{display:block}
</style>

<div id="bibtex_display">
  <div class="bibtex_template">
    <div class="pub-entry">
      <div class="pub-badge">
        <span class="pub-badge-inner" data-venue-badge></span>
      </div>
      <div class="pub-body">
        <div class="pub-title"><span class="title"></span></div>
        <div class="pub-authors"><span class="author" data-highlight-author></span></div>
        <div class="pub-venue">
          <span class="if booktitle">In <em><span class="booktitle"></span></em>, <span class="year"></span>.</span>
          <span class="if journal"><em><span class="journal"></span></em>, <span class="year"></span>.</span>
          <span class="if howpublished"><span class="howpublished"></span>, <span class="year"></span>.</span>
        </div>
        <div class="pub-links">
          <span class="if url_Paper"><a class="bibtexVar pl pl-pdf" href="+url_Paper+" extra="url_Paper" target="_blank">Paper</a></span>
          <span class="if url_arXiv"><a class="bibtexVar pl pl-arx" href="+url_arXiv+" extra="url_arXiv" target="_blank">arXiv</a></span>
          <span class="if url_Code"><a class="bibtexVar pl pl-code" href="+url_Code+" extra="url_Code" target="_blank">Code</a></span>
          <span class="if url_Poster"><a class="bibtexVar pl pl-poster" href="+url_Poster+" extra="url_Poster" target="_blank">Poster</a></span>
          <span class="if doi"><a class="bibtexVar pl pl-doi" href="https://doi.org/+doi+" extra="doi" target="_blank">DOI</a></span>
          <a class="pl pl-bib" href="#" onclick="this.closest('.pub-body').querySelector('.pub-bib-raw').classList.toggle('open');return false">BibTeX</a>
        </div>
        <div class="pub-bib-raw"><span class="bibtexraw noread"></span></div>
      </div>
    </div>
  </div>
</div>

<script>
(function(){
  var MY_NAME = 'Jiaying Lu';

  // Workshop / short-paper venues (lowercase match)
  var WORKSHOP_VENUES = [
    'odrum','relm','ai4ed','okn','scisocllm','bionlp','workshop',
    'spring symposium','healthday','poster','undergraduate consortium','short paper'
  ];

  function isWorkshop(booktitle, series) {
    var hay = (booktitle + ' ' + series).toLowerCase();
    return WORKSHOP_VENUES.some(function(w){ return hay.indexOf(w) !== -1; });
  }

  // Extract abbreviation from Series like "(SIGIR)" → "SIGIR"
  function extractBadge(entry) {
    var series = (entry.querySelector('.if Series .Series, .if series .series, span.Series, span.series') || {}).textContent || '';
    var m = series.match(/\(([^)]+)\)/);
    if (m) return { text: m[1], type: '' };

    // fallback: guess from booktitle / journal
    var bt = (entry.querySelector('.booktitle') || {}).textContent || '';
    var jn = (entry.querySelector('.journal') || {}).textContent || '';

    if (jn.indexOf('IEEE Transactions') !== -1) return { text: 'TKDE', type: 'jour' };
    if (jn.indexOf('Nature') !== -1)           return { text: 'NatComm', type: 'jour' };
    if (jn.indexOf('ACM Computing') !== -1)    return { text: 'CSUR', type: 'jour' };
    if (jn.indexOf('BMJ') !== -1)              return { text: 'BMJ', type: 'jour' };
    if (jn.indexOf('JAMDA') !== -1)            return { text: 'JAMDA', type: 'jour' };
    if (jn.indexOf('Journal of Biomedical') !== -1) return { text: 'JBI', type: 'jour' };

    if (isWorkshop(bt, series)) return { text: 'Workshop', type: 'workshop' };

    // misc / preprint
    var hp = (entry.querySelector('.howpublished') || {}).textContent || '';
    if (hp.indexOf('arXiv') !== -1) return { text: 'arXiv', type: 'preprint' };

    return { text: 'Paper', type: 'conf' };
  }

  function badgeClass(entry, info) {
    // article → jour, misc → preprint, inproceedings → conf/workshop
    var isArticle = entry.querySelector('.if journal');
    var isMisc = entry.querySelector('.if howpublished');
    if (isMisc && isMisc.offsetParent !== null) return 'badge-preprint';
    if (info.type === 'jour') return 'badge-jour';
    if (info.type === 'workshop') return 'badge-workshop';
    if (isArticle && isArticle.offsetParent !== null) return 'badge-jour';
    if (isWorkshop(
      (entry.querySelector('.booktitle')||{}).textContent||'',
      ''
    )) return 'badge-workshop';
    return 'badge-conf';
  }

  function highlightAuthor(text) {
    // highlight "Jiaying Lu" with * and # markers
    var re = new RegExp(MY_NAME.replace(/\s+/g,'\\s+'), 'gi');
    return text.replace(re, function(match){
      return '<span class="me">' + match + '</span>';
    })
    // move * and # outside the name span as superscript markers
    .replace(/<span class="me">([^<]*?)([*#]+)<\/span>/g, function(_, name, marks){
      var out = '<span class="me">' + name + '</span>';
      for (var i = 0; i < marks.length; i++) {
        if (marks[i] === '*') out += '<span class="co-first">*</span>';
        if (marks[i] === '#') out += '<span class="co-corresp">#</span>';
      }
      return out;
    })
    .replace(/<\/span><span class="co-/g, '</span> <span class="co-');
  }

  function processEntries() {
    var entries = document.querySelectorAll('#bibtex_display .pub-entry');
    if (!entries.length) return;

    // 1) Badge + author highlight per entry
    entries.forEach(function(el){
      // badge
      var info = extractBadge(el);
      var badgeEl = el.querySelector('[data-venue-badge]');
      if (badgeEl) {
        badgeEl.textContent = info.text;
        badgeEl.className = 'pub-badge-inner ' + badgeClass(el, info);
      }
      // author highlight
      var authorEl = el.querySelector('[data-highlight-author]');
      if (authorEl) authorEl.innerHTML = highlightAuthor(authorEl.textContent);
    });

    // 2) Group by year
    var groups = {};
    entries.forEach(function(el){
      var yEl = el.querySelector('.year');
      var year = yEl ? yEl.textContent.trim() : 'Unknown';
      if (!groups[year]) groups[year] = [];
      groups[year].push(el);
    });

    var container = document.getElementById('bibtex_display');
    // keep template hidden
    var template = container.querySelector('.bibtex_template');
    container.innerHTML = '';
    if (template) container.appendChild(template);

    var years = Object.keys(groups).sort(function(a,b){ return parseInt(b) - parseInt(a); });
    years.forEach(function(year){
      var grp = document.createElement('div');
      grp.className = 'pub-year-group';
      var label = document.createElement('div');
      label.className = 'pub-year-label';
      label.textContent = year;
      grp.appendChild(label);
      groups[year].forEach(function(e){ grp.appendChild(e); });
      container.appendChild(grp);
    });
  }

  // bibtex-js renders asynchronously — poll until entries appear
  var tries = 0;
  var timer = setInterval(function(){
    tries++;
    if (document.querySelectorAll('#bibtex_display .pub-entry').length > 0) {
      clearInterval(timer);
      processEntries();
    }
    if (tries > 80) clearInterval(timer); // ~16s timeout
  }, 200);
})();
</script>
