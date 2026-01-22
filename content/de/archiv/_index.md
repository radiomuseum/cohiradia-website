---
title: Archiv
linkTitle: Archiv
type: "archiv"
menu: { main: { weight: 10 } }
---


<table class="table table-striped" id="archiveTable">
  <thead class="table-light">
    <th>Datum/Uhrzeit</th>
    <th>Inhalt</th>
    <th>Band</th>
    <th>Land</th>
  </thead>
  <tbody></tbody>
</table>


<script>
document.addEventListener("DOMContentLoaded", async function() {
  const table = document.getElementById("archiveTable");
  if (!table) return;

  try {
    const response = await fetch("/api/metadata.json");
    const data = await response.json();

    data.forEach(item => {
      
      if(item.type !== "synthetic"){
            
      
      const row = table.insertRow();
      const date = row.insertCell();
      const inhalt = row.insertCell();
      const band = row.insertCell();
      const land = row.insertCell();
      
      const dateObj = new Date(item.startTimestamp);
      const formatted = dateObj.toLocaleString("de-DE", {
        year: "numeric",
        month: "2-digit",
        day: "2-digit",
        hour: "2-digit",
        minute: "2-digit"
        });
      
      date.innerHTML = `<span class="text-muted text-nowrap">${formatted}</span>`;
      inhalt.textContent = item.content;
      band.textContent = item.band;
      
      if(item.city){
        land.textContent = `${item.country} (${item.city})`;
      } else {
        land.textContent = item.country;
      }
      }
      
    });
  } catch (error) {
    console.error("Fehler beim Laden der Daten:", error);
  }
});
</script>