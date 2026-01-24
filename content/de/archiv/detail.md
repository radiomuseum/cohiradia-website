---
title: Aufnahme
linkTitle: Aufnahme
type: "archiv"
---

<h2 id="detailTitle">Title</h2>
<nav aria-label="breadcrumb">
    <ol class="breadcrumb">
      <li class="breadcrumb-item"><a href="/de/archiv/">Aufnahmen</a></li>
      <li class="breadcrumb-item active" aria-current="page" id="detailBreadcrumb"></li>
    </ol>
</nav>
<hr class="hr hr-blurry">

<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Aufnahme Datum</strong>
    </div>
    <div class="col-md-9" id="detailDate"></div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Dauer</strong>
    </div>
    <div class="col-md-9" id="detailDuration"></div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
        <strong>Aufnahme Ort</strong>
    </div>
    <div class="col-md-9" id="detailLocation"></div>
</div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Band</strong>
    </div>
    <div class="col-md-9" id="detailBand">      
      MW
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Frequenzbereich</strong>
    </div>
    <div class="col-md-9" id="detailFrequency">      
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Bandbreite</strong>
    </div>
    <div class="col-md-9" id="detailBandwidth">
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Aufnahmegerät</strong>
    </div>
    <div class="col-md-9" id="detailDevice">      
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Antenne</strong>
    </div>
    <div class="col-md-9" id="detailAntenna">      
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Bandmittenfrequenz</strong>
    </div>
    <div class="col-md-9" id="detailCenterFrequency">      
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Encoding</strong>
    </div>
    <div class="col-md-9" id="detailEncoding">      
      ci16
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Filter</strong>
    </div>
    <div class="col-md-9" id="detailFilters">      
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Vorverstärker</strong>
    </div>
    <div class="col-md-9" id="detailPreAmp">      
    </div>
  </div>
<div class="row">
    <div class="col-md-3 text-nowrap">      
      <strong>Bemerkungen</strong>
    </div>
    <div class="col-md-9" id="detailRemarks">      
    </div>
  </div>
<div class="row">
    <div class="col-md-3">      
        <strong>Hochgeladen von</strong>
    </div>
    <div class="col-md-9">      
    Walter Barteczek
    </div>
</div>
<div class="row">
    <div class="col-md-3">      
        <strong>License</strong>
    </div>
    <div class="col-md-9">      
        <a href="https://opendatacommons.org/licenses/odbl/" rel="nofollow" target="_blank">Open Data Commons Open Database License (ODbL)</a>
    </div>
</div>
<p>&nbsp;</p>
<div class="row">
    <div class="col-md-3">      
        <strong>Download</strong>
    </div>
    <div class="col-md-9">  
        <a href="" target="_blank" class="btn btn-secondary" id="downloadLink">
            Download (RFCorder, SDRUnoSDR#)
        </a>    
    </div>
</div>

<h2>Radiostationen</h2>

<script>
document.addEventListener("DOMContentLoaded", async function() {

  try {
    const params = new URLSearchParams(window.location.search);
    const id = params.get('id');

    const response = await fetch(`https://cohiradia.radiomuseum.org/api/metadata/${id}`);
    const data = await response.json();

    document.getElementById("downloadLink").href = `https://cohiradia.radiomuseum.org/view/recordings/${id}`;

    document.getElementById("detailTitle").textContent = data.content;
    document.getElementById("detailBreadcrumb").textContent = data.content;
    document.getElementById("detailDate").textContent = data["recording-date"];
    document.getElementById("detailDuration").textContent = `${data["duration"]} Sekunden`;
    document.getElementById("detailLocation").textContent = `${data["location-country"]}, ${data["location-city"]}`;
    document.getElementById("detailBand").textContent = `${data["band"]}`;
    document.getElementById("detailFrequency").textContent = `${data["frequency-low"]} ${data["frequency-unit"]} - ${data["frequency-high"]} ${data["frequency-unit"]}`;
    document.getElementById("detailBandwidth").textContent = `${data["bandwidth"]} ${data["frequency-unit"]}`;
    document.getElementById("detailDevice").textContent = `${data["recording-type"]}`;
    document.getElementById("detailAntenna").textContent = `${data["antenna"]}`;
    document.getElementById("detailCenterFrequency").textContent = `${data["center-frequency"]} ${data["frequency-unit"]}`;
    document.getElementById("detailEncoding").textContent = `${data["encoding"]}`;

    document.getElementById("detailFilters").textContent = `${data["filters"]}`;
    document.getElementById("detailPreAmp").textContent = `${data["preamp-settings"]}`;
    document.getElementById("detailRemarks").textContent = `${data["remark"]}`;
    
  } catch (error) {
    console.error("Could not load data:", error);
  }
});
</script>



