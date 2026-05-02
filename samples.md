---
layout: default
title: SyncDPO Samples
---

<div class="post">
  <h2 class="pageTitle">Demo Samples</h2>
  <p>Columns: <b>Base (No Tune)</b> | <b>SFT</b> | <b>SyncDPO</b>.</p>
  <p>For the best experience, use headphones and full-screen playback.</p>
</div>

<h3>Section 1: ambient sound video</h3>
{% assign sound_ids = "2jIv5qBTS88_000009,FYldIv9lGLU_000141,OJqJgotD8D4_000038,vcT8gClKYTs_000013,vabench_2,2015-03-28-18-09-31_denoised_20_30" | split: "," %}
<table border="0">
  <tr><th>Base</th><th>SFT</th><th>SyncDPO</th></tr>
  {% for id in sound_ids %}
  <tr>
    <td><video width="320" controls><source src="./assets/demo_videos/sound/{{ id }}_0_notune.mp4" type="video/mp4"></video></td>
    <td><video width="320" controls><source src="./assets/demo_videos/sound/{{ id }}_1_sft.mp4" type="video/mp4"></video></td>
    <td><video width="320" controls><source src="./assets/demo_videos/sound/{{ id }}_2_dpo.mp4" type="video/mp4"></video></td>
  </tr>
  {% endfor %}
</table>

<h3>Section 2: human speech video</h3>
{% assign speech_ids = "5558295419351329373_00903_00027,5958437336103762271_07633_00078,6264226981540067468_26440_00039,6355556454612448247_27523_00002,6367373198133943465_27584_00020,6371470597064737331_27607_00004" | split: "," %}
{% assign speech_text = "To what you want &lt;and then&gt; go and find that rather than places that we like|William was &lt;burning&gt; and pillaging villages in the area of his landing point|&lt;Posture&gt; and they seem to do it more after some times of|&lt;Because&gt; the whole point of nine eleven is that its the justification for the police state|People are happy to be there and its a good &lt;vibe&gt;|One of the articles here is about the queen &lt;elizabeth&gt;" | split: "|" %}
<table border="0">
  <tr><th>Base</th><th>SFT</th><th>SyncDPO</th></tr>
  {% for id in speech_ids %}
  <tr>
    <td><video width="320" controls><source src="./assets/demo_videos/speech/{{ id }}_0_notune.mp4" type="video/mp4"></video></td>
    <td><video width="320" controls><source src="./assets/demo_videos/speech/{{ id }}_1_sft.mp4" type="video/mp4"></video></td>
    <td><video width="320" controls><source src="./assets/demo_videos/speech/{{ id }}_2_dpo.mp4" type="video/mp4"></video></td>
  </tr>
  <tr><td colspan="3"><b>Transcript:</b> {{ speech_text[forloop.index0] }}</td></tr>
  {% endfor %}
</table>
