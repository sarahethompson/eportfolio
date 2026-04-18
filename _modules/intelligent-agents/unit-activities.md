---
layout: page
title: Unit Activities
description: Artefacts from unit exercises: KQML/KIF agent dialogue, constituency parse trees, and deep learning forum post
permalink: /modules/intelligent-agents/unit-activities/
---

*Part of the [Intelligent Agents](/eportfolio/modules/intelligent-agents/) module portfolio.*

---

## Unit 6: KQML/KIF Agent Dialogue

**Activity:** Create an agent dialogue using KQML and KIF between two agents (Alice and Bob). Alice is a procurement agent; Bob controls stock levels for a warehouse. The dialogue covers querying available stock of 50-inch televisions and the number of HDMI slots.

**Learning outcomes addressed:** Understanding of motivations for and appropriate use of agent-based computing; understanding of the main agent models in use today and their grounding in AI research.

<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300;1,400&display=swap" rel="stylesheet">
<style>
.kqml-wrap { font-family: 'DM Mono', monospace; font-size: 14px; line-height: 1.65; color: #2d3142; margin: 2rem 0; }
.kqml-wrap :root, .kqml-wrap * { box-sizing: border-box; }
.kq-agents { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 1.5rem; }
.kq-agent { background: #f8f9fc; border: 1px solid #e2e5ef; border-radius: 8px; padding: 1rem 1.25rem; position: relative; overflow: hidden; }
.kq-agent::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px; }
.kq-agent.alice::before { background: #0d7377; }
.kq-agent.bob::before   { background: #b5621e; }
.kq-agent-name { font-size: 1rem; font-weight: 500; margin-bottom: 2px; }
.alice .kq-agent-name { color: #0d7377; }
.bob   .kq-agent-name { color: #b5621e; }
.kq-agent-role { font-size: 11px; color: #6b7280; }
.kq-note { background: #f3f0ff; border: 1px solid #c4b5fd; border-radius: 8px; padding: 1rem 1.25rem; margin-bottom: 1.5rem; }
.kq-note-title { font-size: 11px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: #6d28d9; margin-bottom: 0.4rem; }
.kq-note p { font-size: 12.5px; color: #4b4070; line-height: 1.7; }
.kq-section-label { font-size: 11px; font-weight: 500; letter-spacing: 0.12em; text-transform: uppercase; color: #9ca3af; margin: 2rem 0 1rem; display: flex; align-items: center; gap: 0.75rem; }
.kq-section-label::after { content: ''; flex: 1; height: 1px; background: #e5e7eb; }
.kq-dialogue { display: flex; flex-direction: column; gap: 1.25rem; }
.kq-msg { }
.kq-msg-header { display: flex; align-items: center; gap: 0.6rem; margin-bottom: 0.4rem; flex-wrap: wrap; }
.kq-badge { font-size: 11px; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; padding: 2px 10px; border-radius: 99px; }
.alice .kq-badge { background: #ccfbf1; color: #0d7377; border: 1px solid #0d7377; }
.bob   .kq-badge { background: #fff3e0; color: #b5621e; border: 1px solid #b5621e; }
.kq-perf { font-size: 11px; color: #9ca3af; }
.kq-step { font-size: 11px; color: #d1d5db; margin-left: auto; }
.kq-code { background: #f8f9fc; border: 1px solid #e2e5ef; border-radius: 8px; overflow: hidden; font-size: 12.5px; }
.kq-code-hdr { display: flex; align-items: center; gap: 0.4rem; padding: 0.4rem 1rem; background: #f1f3f9; border-bottom: 1px solid #e2e5ef; font-size: 11px; color: #9ca3af; }
.kq-dot { width: 7px; height: 7px; border-radius: 50%; background: #d1d5db; }
.kq-code pre { padding: 1rem 1.25rem; overflow-x: auto; white-space: pre; margin: 0; background: transparent; color: #374151; }
.kq-annot { margin-top: 0.4rem; padding: 0.6rem 0.9rem; background: #f8f9fc; border-left: 2px solid #e2e5ef; border-radius: 0 6px 6px 0; font-size: 12px; color: #6b7280; }
.kq-divider { display: flex; align-items: center; gap: 0.75rem; color: #d1d5db; font-size: 11px; letter-spacing: 0.08em; }
.kq-divider::before, .kq-divider::after { content: ''; flex: 1; height: 1px; background: #e5e7eb; }
.t-kw    { color: #1d4ed8; font-weight: 500; }
.t-perf  { color: #dc2626; }
.t-param { color: #0d7377; }
.t-kif   { color: #7c3aed; }
.t-str   { color: #1d6e3d; }
.t-num   { color: #b5621e; }
.t-cmt   { color: #9ca3af; font-style: italic; }
.t-sym   { color: #6d28d9; }
.t-pred  { color: #166534; }
.kq-analysis { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-top: 1rem; }
.kq-acard { background: #f8f9fc; border: 1px solid #e2e5ef; border-radius: 8px; padding: 1rem 1.1rem; }
.kq-acard h4 { font-size: 11px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: #6b7280; margin-bottom: 0.6rem; }
.kq-acard ul { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 0.3rem; }
.kq-acard li { font-size: 12px; color: #374151; padding-left: 1rem; position: relative; }
.kq-acard li::before { content: '›'; position: absolute; left: 0; color: #9ca3af; }
.kq-why { background: #f3f0ff; border: 1px solid #c4b5fd; border-radius: 8px; padding: 1rem 1.25rem; margin-top: 1rem; }
.kq-why h4 { font-size: 11px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: #6d28d9; margin-bottom: 0.4rem; }
.kq-why p { font-size: 12.5px; color: #4b4070; line-height: 1.7; }
@media (max-width: 600px) {
  .kq-agents, .kq-analysis { grid-template-columns: 1fr; }
}
</style>

<div class="kqml-wrap">

<div class="kq-agents">
  <div class="kq-agent alice">
    <div class="kq-agent-name">Alice</div>
    <div class="kq-agent-role">Procurement Agent</div>
  </div>
  <div class="kq-agent bob">
    <div class="kq-agent-name">Bob</div>
    <div class="kq-agent-role">Warehouse Stock-Control Agent</div>
  </div>
</div>

<div class="kq-note">
  <div class="kq-note-title">On KIF Expressions</div>
  <p>Knowledge Interchange Format (KIF) is used inside KQML message bodies to represent semantic content. KIF uses Lisp-like prefix notation with first-order logic. Predicates such as <span style="color:#0d7377">available-stock</span> and <span style="color:#0d7377">hdmi-slots</span> are domain-defined; variables are prefixed with <span style="color:#7c3aed">?</span>.</p>
</div>

<div class="kq-section-label">Dialogue Transcript</div>
<div class="kq-dialogue">

  <div class="kq-msg alice">
    <div class="kq-msg-header">
      <span class="kq-badge">Alice</span>
      <span class="kq-perf">performative: ASK-ONE</span>
      <span class="kq-step">01</span>
    </div>
    <div class="kq-code">
      <div class="kq-code-hdr"><div class="kq-dot"></div><div class="kq-dot"></div><span>KQML: Alice → Bob</span></div>
      <pre><span class="t-cmt">; Alice queries Bob for the available stock of 50-inch televisions</span>

(<span class="t-perf">ask-one</span>
  <span class="t-param">:sender</span>    <span class="t-str">Alice</span>
  <span class="t-param">:receiver</span>  <span class="t-str">Bob</span>
  <span class="t-param">:language</span>  <span class="t-str">KIF</span>
  <span class="t-param">:ontology</span>  <span class="t-str">warehouse-inventory-ontology</span>
  <span class="t-param">:reply-with</span> <span class="t-str">query-001</span>
  <span class="t-param">:content</span>
    (<span class="t-pred">available-stock</span>
      (<span class="t-sym">television</span>
        (<span class="t-pred">screen-size</span> <span class="t-num">50</span> <span class="t-sym">inch</span>))
      <span class="t-kif">?quantity</span>))</pre>
    </div>
    <div class="kq-annot">// ASK-ONE requests a single binding for ?quantity: the number of 50" TVs currently in stock.</div>
  </div>

  <div class="kq-divider">network transmission</div>

  <div class="kq-msg bob">
    <div class="kq-msg-header">
      <span class="kq-badge">Bob</span>
      <span class="kq-perf">performative: TELL</span>
      <span class="kq-step">02</span>
    </div>
    <div class="kq-code">
      <div class="kq-code-hdr"><div class="kq-dot"></div><div class="kq-dot"></div><span>KQML: Bob → Alice</span></div>
      <pre><span class="t-cmt">; Bob responds with the current stock level for 50-inch televisions</span>

(<span class="t-perf">tell</span>
  <span class="t-param">:sender</span>    <span class="t-str">Bob</span>
  <span class="t-param">:receiver</span>  <span class="t-str">Alice</span>
  <span class="t-param">:language</span>  <span class="t-str">KIF</span>
  <span class="t-param">:ontology</span>  <span class="t-str">warehouse-inventory-ontology</span>
  <span class="t-param">:in-reply-to</span> <span class="t-str">query-001</span>
  <span class="t-param">:content</span>
    (<span class="t-pred">available-stock</span>
      (<span class="t-sym">television</span>
        (<span class="t-pred">screen-size</span> <span class="t-num">50</span> <span class="t-sym">inch</span>))
      <span class="t-num">34</span>))</pre>
    </div>
    <div class="kq-annot">// TELL asserts a ground fact: 34 units of 50-inch televisions are available. ?quantity is bound to 34.</div>
  </div>

  <div class="kq-divider">second query initiated</div>

  <div class="kq-msg alice">
    <div class="kq-msg-header">
      <span class="kq-badge">Alice</span>
      <span class="kq-perf">performative: ASK-ONE</span>
      <span class="kq-step">03</span>
    </div>
    <div class="kq-code">
      <div class="kq-code-hdr"><div class="kq-dot"></div><div class="kq-dot"></div><span>KQML: Alice → Bob</span></div>
      <pre><span class="t-cmt">; Alice follows up, querying the number of HDMI slots on the 50-inch televisions</span>

(<span class="t-perf">ask-one</span>
  <span class="t-param">:sender</span>    <span class="t-str">Alice</span>
  <span class="t-param">:receiver</span>  <span class="t-str">Bob</span>
  <span class="t-param">:language</span>  <span class="t-str">KIF</span>
  <span class="t-param">:ontology</span>  <span class="t-str">warehouse-inventory-ontology</span>
  <span class="t-param">:reply-with</span> <span class="t-str">query-002</span>
  <span class="t-param">:content</span>
    (<span class="t-pred">has-feature</span>
      (<span class="t-sym">television</span>
        (<span class="t-pred">screen-size</span> <span class="t-num">50</span> <span class="t-sym">inch</span>))
      (<span class="t-sym">hdmi-slots</span> <span class="t-kif">?slots</span>)))</pre>
    </div>
    <div class="kq-annot">// Alice uses has-feature with compound term (hdmi-slots ?slots) to query port count. Same television identified by screen-size descriptor used in query-001.</div>
  </div>

  <div class="kq-divider">network transmission</div>

  <div class="kq-msg bob">
    <div class="kq-msg-header">
      <span class="kq-badge">Bob</span>
      <span class="kq-perf">performative: TELL</span>
      <span class="kq-step">04</span>
    </div>
    <div class="kq-code">
      <div class="kq-code-hdr"><div class="kq-dot"></div><div class="kq-dot"></div><span>KQML: Bob → Alice</span></div>
      <pre><span class="t-cmt">; Bob responds with the HDMI slot count for the stocked 50-inch television model</span>

(<span class="t-perf">tell</span>
  <span class="t-param">:sender</span>    <span class="t-str">Bob</span>
  <span class="t-param">:receiver</span>  <span class="t-str">Alice</span>
  <span class="t-param">:language</span>  <span class="t-str">KIF</span>
  <span class="t-param">:ontology</span>  <span class="t-str">warehouse-inventory-ontology</span>
  <span class="t-param">:in-reply-to</span> <span class="t-str">query-002</span>
  <span class="t-param">:content</span>
    (<span class="t-pred">has-feature</span>
      (<span class="t-sym">television</span>
        (<span class="t-pred">screen-size</span> <span class="t-num">50</span> <span class="t-sym">inch</span>))
      (<span class="t-sym">hdmi-slots</span> <span class="t-num">3</span>)))</pre>
    </div>
    <div class="kq-annot">// Bob asserts the stocked 50-inch model has 3 HDMI slots. ?slots is bound to 3. Dialogue is logically complete.</div>
  </div>

</div>

<div class="kq-section-label">Analysis</div>
<div class="kq-analysis">
  <div class="kq-acard">
    <h4>KQML Performatives Used</h4>
    <ul>
      <li><span style="color:#0d7377">ask-one</span>: requests a single answer binding</li>
      <li><span style="color:#b5621e">tell</span>: asserts a ground fact as true</li>
      <li><span style="color:#6b7280">reply-with / in-reply-to</span>: correlate request–response pairs</li>
    </ul>
  </div>
  <div class="kq-acard">
    <h4>Message Parameters</h4>
    <ul>
      <li><span style="color:#0d7377">:sender / :receiver</span>: agent identity</li>
      <li><span style="color:#0d7377">:language</span>: content language (KIF)</li>
      <li><span style="color:#0d7377">:ontology</span>: shared knowledge model</li>
      <li><span style="color:#0d7377">:content</span>: semantic payload</li>
    </ul>
  </div>
  <div class="kq-acard">
    <h4>KIF Constructs Used</h4>
    <ul>
      <li><span style="color:#7c3aed">?quantity / ?slots</span>: logical variables</li>
      <li><span style="color:#7c3aed">available-stock</span>: domain predicate</li>
      <li><span style="color:#7c3aed">has-feature</span>: property predicate</li>
      <li><span style="color:#7c3aed">television / hdmi-slots</span>: term constructors</li>
    </ul>
  </div>
  <div class="kq-acard">
    <h4>Dialogue Properties</h4>
    <ul>
      <li>Two independent query–response pairs</li>
      <li>Shared ontology ensures semantic alignment</li>
      <li>Stateless: each message is self-contained</li>
      <li>Extensible: further queries follow the same pattern</li>
    </ul>
  </div>
</div>

<div class="kq-why">
  <h4>Why ASK-ONE, not ASK-ALL?</h4>
  <p>ASK-ONE is appropriate here because the ontology models each screen-size category as a single typed entity with a unique stock figure. There is only one binding for ?quantity (and ?slots) that satisfies the predicate. ASK-ALL would be used if Alice needed all television models matching a partial description, for example all screen sizes above 40 inches.</p>
</div>

</div>

---

## Unit 8: Constituency Parse Trees

**Activity:** Create constituency-based parse trees for three phrases: *The government raised interest rates*, *The internet gives everyone a voice*, and *The man saw the dog with the telescope*.

**Learning outcomes addressed:** Knowledge and skills required to develop, deploy and evaluate the tools and techniques of intelligent systems; understanding of contemporary research issues in intelligent agent systems.

<style>
.pt-wrap { font-family: 'JetBrains Mono', 'DM Mono', monospace; font-size: 13px; line-height: 1.6; color: #2d3142; margin: 2rem 0; }
.pt-meta { font-size: 10px; letter-spacing: .18em; text-transform: uppercase; color: #dc2626; margin-bottom: 1rem; display: flex; align-items: center; gap: .6rem; }
.pt-meta::before { content: ''; width: 20px; height: 1px; background: #dc2626; }
.pt-key { display: flex; flex-wrap: wrap; gap: .4rem 1.2rem; margin-bottom: 2rem; padding: .9rem 1rem; background: #f8f9fc; border: 1px solid #e2e5ef; border-radius: 6px; }
.pt-ki { display: flex; align-items: center; gap: .4rem; font-size: 10.5px; color: #6b7280; }
.pt-kd { width: 26px; height: 18px; border-radius: 3px; display: flex; align-items: center; justify-content: center; font-size: 9.5px; font-weight: 500; }
.pt-section { margin-bottom: 2.5rem; }
.pt-th { display: flex; align-items: baseline; flex-wrap: wrap; gap: .75rem; margin-bottom: .9rem; }
.pt-tn { font-size: 10px; color: #dc2626; letter-spacing: .15em; text-transform: uppercase; }
.pt-sent { font-size: 1rem; color: #111827; font-style: italic; }
.pt-card { background: #f8f9fc; border: 1px solid #e2e5ef; border-radius: 8px; overflow: hidden; }
.pt-card-hdr { display: flex; align-items: center; gap: .4rem; padding: .45rem .9rem; background: #f1f3f9; border-bottom: 1px solid #e2e5ef; font-size: 10px; color: #9ca3af; }
.pt-dot { width: 7px; height: 7px; border-radius: 50%; background: #d1d5db; }
.pt-tree-wrap { padding: 1.5rem 1rem; width: 100%; }
.pt-tree-wrap svg { width: 100%; height: auto; display: block; }
.pt-annot { padding: .8rem 1rem; background: #f1f3f9; border-top: 1px solid #e2e5ef; font-size: 11px; color: #6b7280; line-height: 1.7; }
.pt-annot strong { color: #374151; }
.pt-amb { padding: .65rem 1rem; background: #f5f3ff; border-top: 1px solid #e2e5ef; font-size: 10px; color: #7c3aed; }
.pt-split { display: grid; grid-template-columns: 1fr 1fr; border-top: 1px solid #e2e5ef; }
.pt-sp { padding: 1.2rem .75rem; width: 100%; }
.pt-sp svg { width: 100%; height: auto; display: block; }
.pt-sp:first-child { border-right: 1px solid #e2e5ef; }
.pt-split-labels { display: grid; grid-template-columns: 1fr 1fr; border-top: 1px solid #e2e5ef; }
.pt-sl { padding: .6rem .9rem; font-size: 10px; color: #6b7280; background: #f1f3f9; }
.pt-sl:first-child { border-right: 1px solid #e2e5ef; }
.pt-sl strong { display: block; color: #374151; margin-bottom: 2px; }
.pt-rules { margin-top: 2rem; padding: 1.25rem; background: #f8f9fc; border: 1px solid #e2e5ef; border-radius: 8px; }
.pt-rules-title { font-size: 10px; letter-spacing: .15em; text-transform: uppercase; color: #9ca3af; margin-bottom: 1rem; }
.pt-rules-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: .35rem; }
.pt-rule { font-size: 11px; color: #6b7280; }
.pt-rule .lhs { color: #0d7377; } .pt-rule .arr { color: #d1d5db; margin: 0 .3rem; } .pt-rule .rhs { color: #374151; } .pt-rule .cmt { color: #9ca3af; font-size: 9.5px; margin-left: .4rem; }
@media (max-width: 560px) {
  .pt-split, .pt-split-labels { grid-template-columns: 1fr; }
  .pt-sp:first-child { border-right: none; border-bottom: 1px solid #e2e5ef; }
  .pt-sl:first-child { border-right: none; border-bottom: 1px solid #e2e5ef; }
}
</style>

<div class="pt-wrap">
<div class="pt-meta">IA_PCOM7E · Intelligent Agents · Unit 8 · e-Portfolio Activity</div>

<div class="pt-key">
  <div class="pt-ki"><div class="pt-kd" style="background:#fef2f2;color:#dc2626;border:1px solid #dc2626">S</div>Sentence</div>
  <div class="pt-ki"><div class="pt-kd" style="background:#f0fdfa;color:#0d7377;border:1px solid #0d7377">NP</div>Noun Phrase</div>
  <div class="pt-ki"><div class="pt-kd" style="background:#fff7ed;color:#b5621e;border:1px solid #b5621e">VP</div>Verb Phrase</div>
  <div class="pt-ki"><div class="pt-kd" style="background:#f5f3ff;color:#7c3aed;border:1px solid #7c3aed">PP</div>Prepositional Phrase</div>
  <div class="pt-ki"><div class="pt-kd" style="background:#f0fdf4;color:#166534;border:1px solid #166534">V</div>Verb</div>
  <div class="pt-ki"><div class="pt-kd" style="background:#eff6ff;color:#1d4ed8;border:1px solid #1d4ed8">N</div>Noun</div>
  <div class="pt-ki"><div class="pt-kd" style="background:#fdf4ff;color:#86198f;border:1px solid #86198f">DT</div>Determiner</div>
  <div class="pt-ki"><div class="pt-kd" style="background:#f8f9fc;color:#6b7280;border:1px solid #9ca3af">P</div>Preposition</div>
</div>

<!-- SENTENCE 1 -->
<div class="pt-section">
  <div class="pt-th"><span class="pt-tn">Sentence 01</span><span class="pt-sent">"The government raised interest rates."</span></div>
  <div class="pt-card">
    <div class="pt-card-hdr"><div class="pt-dot"></div><div class="pt-dot"></div><div class="pt-dot"></div><span style="margin-left:4px">Constituency Parse Tree</span></div>
    <div class="pt-tree-wrap">
      <svg viewBox="0 0 500 275" xmlns="http://www.w3.org/2000/svg">
        <rect x="232" y="10" width="36" height="22" rx="4" fill="#fef2f2" stroke="#dc2626" stroke-width="1"/><text x="250" y="25" text-anchor="middle" fill="#dc2626" font-size="12" font-weight="500" font-family="monospace">S</text>
        <rect x="82" y="70" width="36" height="22" rx="4" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="100" y="85" text-anchor="middle" fill="#0d7377" font-size="12" font-weight="500" font-family="monospace">NP</text>
        <rect x="352" y="70" width="36" height="22" rx="4" fill="#fff7ed" stroke="#b5621e" stroke-width="1"/><text x="370" y="85" text-anchor="middle" fill="#b5621e" font-size="12" font-weight="500" font-family="monospace">VP</text>
        <rect x="22" y="145" width="36" height="22" rx="4" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="40" y="160" text-anchor="middle" fill="#86198f" font-size="12" font-weight="500" font-family="monospace">DT</text>
        <rect x="142" y="145" width="28" height="22" rx="4" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="156" y="160" text-anchor="middle" fill="#1d4ed8" font-size="12" font-weight="500" font-family="monospace">N</text>
        <rect x="262" y="145" width="28" height="22" rx="4" fill="#f0fdf4" stroke="#166534" stroke-width="1"/><text x="276" y="160" text-anchor="middle" fill="#166534" font-size="12" font-weight="500" font-family="monospace">V</text>
        <rect x="392" y="145" width="36" height="22" rx="4" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="410" y="160" text-anchor="middle" fill="#0d7377" font-size="12" font-weight="500" font-family="monospace">NP</text>
        <rect x="342" y="212" width="28" height="22" rx="4" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="356" y="227" text-anchor="middle" fill="#1d4ed8" font-size="12" font-weight="500" font-family="monospace">N</text>
        <rect x="452" y="212" width="28" height="22" rx="4" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="466" y="227" text-anchor="middle" fill="#1d4ed8" font-size="12" font-weight="500" font-family="monospace">N</text>
        <line x1="250" y1="32" x2="100" y2="70" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="250" y1="32" x2="370" y2="70" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="100" y1="92" x2="40" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="100" y1="92" x2="156" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="370" y1="92" x2="276" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="370" y1="92" x2="410" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="410" y1="167" x2="356" y2="212" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="410" y1="167" x2="466" y2="212" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="40" y1="167" x2="40" y2="255" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="156" y1="167" x2="156" y2="255" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="276" y1="167" x2="276" y2="255" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="356" y1="234" x2="356" y2="255" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="466" y1="234" x2="466" y2="255" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <text x="40" y="268" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">The</text>
        <text x="156" y="268" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">government</text>
        <text x="276" y="268" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">raised</text>
        <text x="356" y="268" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">interest</text>
        <text x="466" y="268" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">rates</text>
      </svg>
    </div>
    <div class="pt-annot"><strong>S → NP VP</strong> | <strong>NP → DT N</strong> ("The government") | <strong>VP → V NP</strong> | <strong>NP → N N</strong> ("interest rates", noun-noun compound, no determiner required)</div>
  </div>
</div>

<!-- SENTENCE 2 -->
<div class="pt-section">
  <div class="pt-th"><span class="pt-tn">Sentence 02</span><span class="pt-sent">"The internet gives everyone a voice."</span></div>
  <div class="pt-card">
    <div class="pt-card-hdr"><div class="pt-dot"></div><div class="pt-dot"></div><div class="pt-dot"></div><span style="margin-left:4px">Constituency Parse Tree: Ditransitive Verb</span></div>
    <div class="pt-tree-wrap">
      <svg viewBox="0 0 560 295" xmlns="http://www.w3.org/2000/svg">
        <rect x="262" y="10" width="36" height="22" rx="4" fill="#fef2f2" stroke="#dc2626" stroke-width="1"/><text x="280" y="25" text-anchor="middle" fill="#dc2626" font-size="12" font-weight="500" font-family="monospace">S</text>
        <rect x="82" y="70" width="36" height="22" rx="4" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="100" y="85" text-anchor="middle" fill="#0d7377" font-size="12" font-weight="500" font-family="monospace">NP</text>
        <rect x="392" y="70" width="36" height="22" rx="4" fill="#fff7ed" stroke="#b5621e" stroke-width="1"/><text x="410" y="85" text-anchor="middle" fill="#b5621e" font-size="12" font-weight="500" font-family="monospace">VP</text>
        <rect x="22" y="145" width="36" height="22" rx="4" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="40" y="160" text-anchor="middle" fill="#86198f" font-size="12" font-weight="500" font-family="monospace">DT</text>
        <rect x="142" y="145" width="28" height="22" rx="4" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="156" y="160" text-anchor="middle" fill="#1d4ed8" font-size="12" font-weight="500" font-family="monospace">N</text>
        <rect x="282" y="145" width="28" height="22" rx="4" fill="#f0fdf4" stroke="#166534" stroke-width="1"/><text x="296" y="160" text-anchor="middle" fill="#166534" font-size="12" font-weight="500" font-family="monospace">V</text>
        <rect x="362" y="145" width="36" height="22" rx="4" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="380" y="160" text-anchor="middle" fill="#0d7377" font-size="12" font-weight="500" font-family="monospace">NP</text>
        <rect x="472" y="145" width="36" height="22" rx="4" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="490" y="160" text-anchor="middle" fill="#0d7377" font-size="12" font-weight="500" font-family="monospace">NP</text>
        <rect x="352" y="212" width="28" height="22" rx="4" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="366" y="227" text-anchor="middle" fill="#1d4ed8" font-size="12" font-weight="500" font-family="monospace">N</text>
        <rect x="452" y="212" width="36" height="22" rx="4" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="470" y="227" text-anchor="middle" fill="#86198f" font-size="12" font-weight="500" font-family="monospace">DT</text>
        <rect x="504" y="212" width="28" height="22" rx="4" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="518" y="227" text-anchor="middle" fill="#1d4ed8" font-size="12" font-weight="500" font-family="monospace">N</text>
        <line x1="280" y1="32" x2="100" y2="70" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="280" y1="32" x2="410" y2="70" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="100" y1="92" x2="40" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="100" y1="92" x2="156" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="410" y1="92" x2="296" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="410" y1="92" x2="380" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="410" y1="92" x2="490" y2="145" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="380" y1="167" x2="366" y2="212" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="490" y1="167" x2="470" y2="212" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="490" y1="167" x2="518" y2="212" stroke="#9ca3af" stroke-width="1.5"/>
        <line x1="40" y1="167" x2="40" y2="275" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="156" y1="167" x2="156" y2="275" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="296" y1="167" x2="296" y2="275" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="366" y1="234" x2="366" y2="275" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="470" y1="234" x2="470" y2="275" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <line x1="518" y1="234" x2="518" y2="275" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
        <text x="40" y="288" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">The</text>
        <text x="156" y="288" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">internet</text>
        <text x="296" y="288" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">gives</text>
        <text x="366" y="288" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">everyone</text>
        <text x="470" y="288" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">a</text>
        <text x="518" y="288" text-anchor="middle" fill="#374151" font-size="11" font-family="monospace">voice</text>
      </svg>
    </div>
    <div class="pt-annot"><strong>S → NP VP</strong> | <strong>NP → DT N</strong> ("The internet") | <strong>VP → V NP NP</strong> (ditransitive) | <strong>NP → N</strong> ("everyone") | <strong>NP → DT N</strong> ("a voice"): "gives" takes both an indirect and direct object.</div>
  </div>
</div>

<!-- SENTENCE 3 -->
<div class="pt-section">
  <div class="pt-th"><span class="pt-tn">Sentence 03</span><span class="pt-sent">"The man saw the dog with the telescope."</span></div>
  <div class="pt-card">
    <div class="pt-card-hdr"><div class="pt-dot"></div><div class="pt-dot"></div><div class="pt-dot"></div><span style="margin-left:4px">Structural Ambiguity: Two Valid Parse Trees</span></div>
    <div class="pt-amb">⚠ "with the telescope" can attach to VP or NP, producing two different readings.</div>
    <div class="pt-split">
      <div class="pt-sp">
        <svg viewBox="0 0 340 380" xmlns="http://www.w3.org/2000/svg">
          <rect x="142" y="8" width="36" height="20" rx="3" fill="#fef2f2" stroke="#dc2626" stroke-width="1"/><text x="160" y="22" text-anchor="middle" fill="#dc2626" font-size="11" font-weight="500" font-family="monospace">S</text>
          <rect x="52" y="58" width="36" height="20" rx="3" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="70" y="72" text-anchor="middle" fill="#0d7377" font-size="11" font-weight="500" font-family="monospace">NP</text>
          <rect x="212" y="58" width="36" height="20" rx="3" fill="#fff7ed" stroke="#b5621e" stroke-width="1"/><text x="230" y="72" text-anchor="middle" fill="#b5621e" font-size="11" font-weight="500" font-family="monospace">VP</text>
          <rect x="8" y="118" width="34" height="20" rx="3" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="25" y="132" text-anchor="middle" fill="#86198f" font-size="10" font-weight="500" font-family="monospace">DT</text>
          <rect x="92" y="118" width="24" height="20" rx="3" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="104" y="132" text-anchor="middle" fill="#1d4ed8" font-size="10" font-weight="500" font-family="monospace">N</text>
          <rect x="152" y="118" width="24" height="20" rx="3" fill="#f0fdf4" stroke="#166534" stroke-width="1"/><text x="164" y="132" text-anchor="middle" fill="#166534" font-size="10" font-weight="500" font-family="monospace">V</text>
          <rect x="196" y="118" width="36" height="20" rx="3" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="214" y="132" text-anchor="middle" fill="#0d7377" font-size="11" font-weight="500" font-family="monospace">NP</text>
          <rect x="268" y="118" width="30" height="20" rx="3" fill="#f5f3ff" stroke="#7c3aed" stroke-width="1"/><text x="283" y="132" text-anchor="middle" fill="#7c3aed" font-size="11" font-weight="500" font-family="monospace">PP</text>
          <rect x="168" y="182" width="34" height="20" rx="3" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="185" y="196" text-anchor="middle" fill="#86198f" font-size="10" font-weight="500" font-family="monospace">DT</text>
          <rect x="222" y="182" width="24" height="20" rx="3" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="234" y="196" text-anchor="middle" fill="#1d4ed8" font-size="10" font-weight="500" font-family="monospace">N</text>
          <rect x="254" y="182" width="24" height="20" rx="3" fill="#f8f9fc" stroke="#9ca3af" stroke-width="1"/><text x="266" y="196" text-anchor="middle" fill="#6b7280" font-size="10" font-weight="500" font-family="monospace">P</text>
          <rect x="288" y="182" width="36" height="20" rx="3" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="306" y="196" text-anchor="middle" fill="#0d7377" font-size="11" font-weight="500" font-family="monospace">NP</text>
          <rect x="270" y="244" width="34" height="20" rx="3" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="287" y="258" text-anchor="middle" fill="#86198f" font-size="10" font-weight="500" font-family="monospace">DT</text>
          <rect x="312" y="244" width="24" height="20" rx="3" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="324" y="258" text-anchor="middle" fill="#1d4ed8" font-size="10" font-weight="500" font-family="monospace">N</text>
          <line x1="160" y1="28" x2="70" y2="58" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="160" y1="28" x2="230" y2="58" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="70" y1="78" x2="25" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="70" y1="78" x2="104" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="230" y1="78" x2="164" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="230" y1="78" x2="214" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="230" y1="78" x2="283" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="214" y1="138" x2="185" y2="182" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="214" y1="138" x2="234" y2="182" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="283" y1="138" x2="266" y2="182" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="283" y1="138" x2="306" y2="182" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="306" y1="202" x2="287" y2="244" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="306" y1="202" x2="324" y2="244" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="25" y1="138" x2="25" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="104" y1="138" x2="104" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="164" y1="138" x2="164" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="185" y1="202" x2="185" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="234" y1="202" x2="234" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="266" y1="202" x2="266" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="287" y1="264" x2="287" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="324" y1="264" x2="324" y2="348" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <text x="25" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">The</text>
          <text x="104" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">man</text>
          <text x="164" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">saw</text>
          <text x="185" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">the</text>
          <text x="234" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">dog</text>
          <text x="266" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">with</text>
          <text x="287" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">the</text>
          <text x="324" y="360" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">telescope</text>
        </svg>
      </div>
      <div class="pt-sp">
        <svg viewBox="0 0 340 410" xmlns="http://www.w3.org/2000/svg">
          <rect x="142" y="8" width="36" height="20" rx="3" fill="#fef2f2" stroke="#dc2626" stroke-width="1"/><text x="160" y="22" text-anchor="middle" fill="#dc2626" font-size="11" font-weight="500" font-family="monospace">S</text>
          <rect x="52" y="58" width="36" height="20" rx="3" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="70" y="72" text-anchor="middle" fill="#0d7377" font-size="11" font-weight="500" font-family="monospace">NP</text>
          <rect x="222" y="58" width="36" height="20" rx="3" fill="#fff7ed" stroke="#b5621e" stroke-width="1"/><text x="240" y="72" text-anchor="middle" fill="#b5621e" font-size="11" font-weight="500" font-family="monospace">VP</text>
          <rect x="8" y="118" width="34" height="20" rx="3" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="25" y="132" text-anchor="middle" fill="#86198f" font-size="10" font-weight="500" font-family="monospace">DT</text>
          <rect x="92" y="118" width="24" height="20" rx="3" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="104" y="132" text-anchor="middle" fill="#1d4ed8" font-size="10" font-weight="500" font-family="monospace">N</text>
          <rect x="162" y="118" width="24" height="20" rx="3" fill="#f0fdf4" stroke="#166534" stroke-width="1"/><text x="174" y="132" text-anchor="middle" fill="#166534" font-size="10" font-weight="500" font-family="monospace">V</text>
          <rect x="218" y="118" width="36" height="20" rx="3" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="236" y="132" text-anchor="middle" fill="#0d7377" font-size="11" font-weight="500" font-family="monospace">NP</text>
          <rect x="170" y="182" width="34" height="20" rx="3" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="187" y="196" text-anchor="middle" fill="#86198f" font-size="10" font-weight="500" font-family="monospace">DT</text>
          <rect x="220" y="182" width="24" height="20" rx="3" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="232" y="196" text-anchor="middle" fill="#1d4ed8" font-size="10" font-weight="500" font-family="monospace">N</text>
          <rect x="270" y="182" width="30" height="20" rx="3" fill="#f5f3ff" stroke="#7c3aed" stroke-width="1"/><text x="285" y="196" text-anchor="middle" fill="#7c3aed" font-size="11" font-weight="500" font-family="monospace">PP</text>
          <rect x="244" y="246" width="24" height="20" rx="3" fill="#f8f9fc" stroke="#9ca3af" stroke-width="1"/><text x="256" y="260" text-anchor="middle" fill="#6b7280" font-size="10" font-weight="500" font-family="monospace">P</text>
          <rect x="280" y="246" width="36" height="20" rx="3" fill="#f0fdfa" stroke="#0d7377" stroke-width="1"/><text x="298" y="260" text-anchor="middle" fill="#0d7377" font-size="11" font-weight="500" font-family="monospace">NP</text>
          <rect x="262" y="308" width="34" height="20" rx="3" fill="#fdf4ff" stroke="#86198f" stroke-width="1"/><text x="279" y="322" text-anchor="middle" fill="#86198f" font-size="10" font-weight="500" font-family="monospace">DT</text>
          <rect x="304" y="308" width="24" height="20" rx="3" fill="#eff6ff" stroke="#1d4ed8" stroke-width="1"/><text x="316" y="322" text-anchor="middle" fill="#1d4ed8" font-size="10" font-weight="500" font-family="monospace">N</text>
          <line x1="160" y1="28" x2="70" y2="58" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="160" y1="28" x2="240" y2="58" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="70" y1="78" x2="25" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="70" y1="78" x2="104" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="240" y1="78" x2="174" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="240" y1="78" x2="236" y2="118" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="236" y1="138" x2="187" y2="182" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="236" y1="138" x2="232" y2="182" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="236" y1="138" x2="285" y2="182" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="285" y1="202" x2="256" y2="246" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="285" y1="202" x2="298" y2="246" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="298" y1="266" x2="279" y2="308" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="298" y1="266" x2="316" y2="308" stroke="#9ca3af" stroke-width="1.5"/>
          <line x1="25" y1="138" x2="25" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="104" y1="138" x2="104" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="174" y1="138" x2="174" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="187" y1="202" x2="187" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="232" y1="202" x2="232" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="256" y1="266" x2="256" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="279" y1="328" x2="279" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <line x1="316" y1="328" x2="316" y2="385" stroke="#e5e7eb" stroke-width="1" stroke-dasharray="3,2"/>
          <text x="25" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">The</text>
          <text x="104" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">man</text>
          <text x="174" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">saw</text>
          <text x="187" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">the</text>
          <text x="232" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">dog</text>
          <text x="256" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">with</text>
          <text x="279" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">the</text>
          <text x="316" y="397" text-anchor="middle" fill="#374151" font-size="9" font-family="monospace">telescope</text>
        </svg>
      </div>
    </div>
    <div class="pt-split-labels">
      <div class="pt-sl"><strong>Reading A: PP attaches to VP</strong>VP → V NP PP · The man used a telescope to see the dog.</div>
      <div class="pt-sl"><strong>Reading B: PP attaches to NP</strong>NP → DT N PP · The man saw the dog that had a telescope.</div>
    </div>
    <div class="pt-annot"><strong>Attachment ambiguity:</strong> Both trees are grammatically valid under the same CFG rules. Probabilistic parsers trained on annotated treebanks assign Reading A a higher probability in most contexts, as PP-to-VP attachment is statistically more common in English. NLP systems cannot rely on grammar rules alone to resolve this.</div>
  </div>
</div>

<div class="pt-rules">
  <div class="pt-rules-title">Context-Free Grammar Rules Applied</div>
  <div class="pt-rules-grid">
    <div class="pt-rule"><span class="lhs">S</span><span class="arr">→</span><span class="rhs">NP VP</span><span class="cmt">// all three sentences</span></div>
    <div class="pt-rule"><span class="lhs">NP</span><span class="arr">→</span><span class="rhs">DT N</span><span class="cmt">// "The government", "a voice"</span></div>
    <div class="pt-rule"><span class="lhs">NP</span><span class="arr">→</span><span class="rhs">N N</span><span class="cmt">// "interest rates"</span></div>
    <div class="pt-rule"><span class="lhs">NP</span><span class="arr">→</span><span class="rhs">N</span><span class="cmt">// "everyone"</span></div>
    <div class="pt-rule"><span class="lhs">NP</span><span class="arr">→</span><span class="rhs">DT N PP</span><span class="cmt">// Reading B only</span></div>
    <div class="pt-rule"><span class="lhs">VP</span><span class="arr">→</span><span class="rhs">V NP</span><span class="cmt">// "raised interest rates"</span></div>
    <div class="pt-rule"><span class="lhs">VP</span><span class="arr">→</span><span class="rhs">V NP NP</span><span class="cmt">// "gives everyone a voice"</span></div>
    <div class="pt-rule"><span class="lhs">VP</span><span class="arr">→</span><span class="rhs">V NP PP</span><span class="cmt">// Reading A only</span></div>
    <div class="pt-rule"><span class="lhs">PP</span><span class="arr">→</span><span class="rhs">P NP</span><span class="cmt">// "with the telescope"</span></div>
  </div>
</div>
</div>

---

## Unit 10: Deep Learning in Action

**Activity:** Research an application of deep learning with significant societal impact and post to the discussion forum covering an overview, how it works, and socio-technical implications.

**Learning outcomes addressed:** Understanding of motivations for and appropriate use of agent-based computing; understanding of the main agent models in use today.

### Deep Learning in Oncological Radiomics

Radiomics is the large-scale extraction of quantitative features from medical images (CT, MRI, and PET scans), which are then used to build predictive models for tumour characterisation, treatment response, prognosis, and disease staging. Where traditional radiology relies on features visible to the human eye, deep learning-based radiomics extracts high-dimensional patterns imperceptible to clinicians, enabling a richer, more granular analysis of tumour biology from routine imaging data (Liu et al., 2019). Publications in this field have grown dramatically, from just 6 in 2015 to over 1,100 by 2024, reflecting the pace at which this technology is entering clinical practice.

#### How It Works

A deep learning radiomics pipeline typically involves four stages. First, a region of interest (the tumour or surrounding tissue) is segmented from the medical image, either manually by a clinician or automatically using convolutional neural networks (CNNs). Second, hundreds or thousands of quantitative features are extracted, covering shape, texture, intensity, and spatial relationships within the tissue. Third, deep learning models, most commonly CNNs or transformer-based architectures, are trained on these features alongside clinical outcomes such as survival data or treatment response. Finally, the trained model generates predictions for new patients, supporting clinical decision-making (Lambin et al., 2017).

#### Socio-Technical and Ethical Implications

Despite its promise, deep learning radiomics raises significant ethical and practical concerns that must be addressed before widespread clinical adoption.

**Reproducibility and standardisation** is perhaps the most pressing technical-ethical issue. Radiomic features can vary substantially depending on the scanner manufacturer, acquisition protocol, and reconstruction algorithm used, meaning a model trained on data from one institution may perform poorly at another. This has led to the development of quality scoring tools such as the Radiomics Quality Score (RQS) and the METRICS framework proposed by the European Society of Medical Imaging Informatics in 2024. Deploying a model clinically without addressing these issues risks systematically misleading clinicians.

**Bias and demographic equity** present a related concern. Models trained predominantly on data from well-resourced institutions in high-income countries may perform less accurately for patients from underrepresented populations. This risks entrenching existing healthcare inequalities rather than alleviating them (Obermeyer et al., 2019).

**Interpretability and clinical trust** are particularly challenging for deep learning models. Without clear explanations of how models arrive at their predictions, clinicians may be hesitant to incorporate these tools into practice. In high-stakes oncological decisions such as treatment selection or prognosis, a black-box prediction is difficult to justify ethically or legally.

**Data privacy** is a further concern. Radiomics requires large, richly annotated datasets of sensitive medical images, often necessitating data sharing across institutions and national boundaries. Patient consent frameworks for secondary use of imaging data vary significantly across jurisdictions.

**Clinical liability** remains unresolved. If a radiomic model contributes to a misdiagnosis or an incorrect prognosis, the question of who bears responsibility: the clinician, the institution, or the software developer, has no clear legal answer in most healthcare systems.

#### Conclusion

Deep learning radiomics represents one of the most genuinely transformative applications of AI in medicine, with the potential to deliver personalised, non-invasive insights into tumour biology that were previously impossible. However, its societal impact will depend critically on how the research community and regulators address reproducibility, bias, interpretability, and accountability, challenges that are as much ethical and institutional as they are technical.

**References**

Lambin, P. et al. (2017) 'Radiomics: the bridge between medical imaging and personalised medicine', *Nature Reviews Clinical Oncology*, 14(12), pp. 749–762.

Liu, Z. et al. (2019) 'The applications of radiomics in precision diagnosis and treatment of oncology', *Theranostics*, 9(5), pp. 1303–1322.

Obermeyer, Z. et al. (2019) 'Dissecting racial bias in an algorithm used to manage the health of populations', *Science*, 366(6464), pp. 447–453.

Whybra, P. et al. (2024) 'The Image Biomarker Standardization Initiative: standardized convolutional filters for reproducible radiomics', *Radiology*, 310(2), e231319.
