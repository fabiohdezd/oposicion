# Oposición
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Mi oposición · Tecnología</title>
<style>
  :root {
    font-family: system-ui, sans-serif;
    color: #243d36;
    background: #f5f7f6;
  }

  * { box-sizing: border-box; }
  body { margin: 0; }
  main { max-width: 1250px; margin: auto; padding: 28px 20px; }
  h1 { margin-bottom: 8px; font-size: clamp(28px, 5vw, 42px); }
  h2 { margin-top: 0; }
  p { line-height: 1.6; }
  .muted { color: #687c73; }
  .eyebrow { color: #27745b; font-size: 12px; letter-spacing: 2px; }
  button, input, select { font: inherit; }
  button {
    cursor: pointer;
    border: 1px solid #d7e2dc;
    border-radius: 8px;
    padding: 10px 14px;
    background: white;
    color: #294d3e;
  }
  button:hover { background: #edf3ef; }
  button.primary { background: #27745b; color: white; }
  input, select {
    padding: 10px;
    border: 1px solid #cad8cf;
    border-radius: 7px;
    background: white;
    min-width: 0;
  }
  input[type="checkbox"] { accent-color: #27745b; }
  :focus-visible { outline: 3px solid #81b39c; outline-offset: 3px; }
  .summary {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin: 28px 0;
  }
  .stat {
    padding: 20px;
    background: white;
    border: 1px solid #e1e8e3;
    border-radius: 12px;
  }
  .stat strong { display: block; font-size: 30px; margin-bottom: 5px; }
  .stat span { color: #687c73; font-size: 13px; }
  .toolbar { display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0; }
  .toolbar input { flex: 1; min-width: 180px; }
  .legend { display: flex; flex-wrap: wrap; gap: 16px; font-size: 12px; }
  .legend span::before {
    content: "";
    display: inline-block;
    width: 9px;
    height: 9px;
    margin-right: 6px;
    border-radius: 50%;
    background: var(--color);
  }
  .grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 16px;
  }
  .card {
    background: white;
    border: 1px solid #e0e7e2;
    border-top: 5px solid var(--color);
    border-radius: 12px;
    padding: 18px;
    display: flex;
    flex-direction: column;
  }
  .pending { --color: #98a29c; --pale: #f0f2f1; }
  .progress { --color: #b58b3f; --pale: #faf3e6; }
  .done { --color: #438963; --pale: #eaf5ed; }
  .review { --color: #c36e52; --pale: #fceee8; }
  .card-top { display: flex; justify-content: space-between; align-items: center; gap: 8px; }
  .number { font-size: 12px; color: #6b7f73; }
  .badge { font-size: 11px; background: var(--pale); color: var(--color); padding: 5px 8px; border-radius: 5px; }
  .card h3 { font-size: 16px; line-height: 1.5; overflow-wrap: anywhere; }
  .checks { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 16px; }
  .check { padding: 5px 7px; background: #f3f5f3; color: #7d8a80; border-radius: 5px; font-size: 11px; }
  .check.yes { background: #eaf5ed; color: #36784e; }
  .details { display: flex; justify-content: space-between; gap: 8px; font-size: 12px; }
  .warning { color: #a85925; font-size: 12px; }
  .card-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 8px;
    border-top: 1px solid #edf0ed;
    padding-top: 12px;
    margin-top: auto;
    font-size: 11px;
    color: #738478;
  }
  .reading { font-size: 12px; color: #738478; margin-bottom: 16px; }
  .notice { font-size: 12px; color: #687c73; }
  dialog {
    width: min(500px, 94vw);
    border: 1px solid #dce5de;
    border-radius: 14px;
    padding: 26px;
    color: #243d36;
  }
  dialog::backdrop { background: #172c2466; }
  .field { display: flex; flex-direction: column; gap: 7px; margin: 16px 0; font-size: 13px; }
  .checkboxes { display: grid; gap: 14px; margin: 22px 0; }
  .checkboxes label { display: flex; gap: 8px; align-items: center; font-size: 14px; }
  .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .actions { display: flex; justify-content: flex-end; gap: 10px; margin-top: 24px; }
  #message { min-height: 24px; color: #27745b; font-size: 13px; }
  footer { padding-top: 24px; margin-top: 30px; border-top: 1px solid #dce5de; }
  @media (max-width: 900px) { .grid { grid-template-columns: 1fr 1fr; } }
  @media (max-width: 580px) {
    .grid { grid-template-columns: 1fr; }
    .summary { grid-template-columns: 1fr 1fr; }
    .stat { padding: 15px; }
    .toolbar select { flex: 1; }
  }
</style>
</head>
<body>
<main>
  <header>
    <p class="eyebrow">TECNOLOGÍA · SECUNDARIA</p>
    <h1>Mi camino a la plaza</h1>
    <p class="muted">71 temas. Un paso cada día.</p>
  </header>

  <section class="summary" id="summary" aria-label="Resumen"></section>

  <div class="toolbar">
    <input id="search" type="search" placeholder="Buscar tema…" aria-label="Buscar tema">
    <select id="filter" aria-label="Filtrar temas">
      <option value="all">Todos los temas</option>
      <option value="pending">Pendientes</option>
      <option value="progress">En progreso</option>
      <option value="studied">Estudiados</option>
      <option value="review">Por repasar</option>
      <option value="long">Más de 10 páginas</option>
    </select>
    <button id="export">Exportar copia</button>
    <button id="import">Importar copia</button>
    <input id="file" type="file" accept=".json,application/json" hidden>
  </div>

  <div class="legend">
    <span class="pending">Pendiente</span>
    <span class="progress">En progreso</span>
    <span class="done">Al día</span>
    <span class="review">Por repasar</span>
  </div>

  <p class="notice">
    Un tema estudiado necesita repaso tras 7 días sin lectura, o si no tiene fecha registrada.
    El aviso de extensión aparece cuando supera las 10 páginas.
  </p>
  <div id="message" role="status" aria-live="polite"></div>
  <p id="count" class="notice"></p>
  <section id="topics" class="grid" aria-label="Temario"></section>

  <footer class="notice">
    Guardado automático en este navegador. Exporta copias de seguridad:
    los datos no se sincronizan entre dispositivos y se pierden si borras el almacenamiento del sitio.
  </footer>
</main>

<dialog id="editor">
  <form id="form">
    <p class="eyebrow" id="editing-number"></p>
    <h2>Progreso del tema</h2>

    <label class="field">
      Nombre del tema
      <input id="title" required maxlength="250">
    </label>

    <div class="checkboxes">
      <label><input id="updated" type="checkbox"> Tema actualizado</label>
      <label><input id="studied" type="checkbox"> Tema estudiado</label>
      <label><input id="outline" type="checkbox"> Esquema realizado</label>
    </div>

    <div class="form-grid">
      <label class="field">
        Repasos realizados
        <input id="reviews" type="number" min="0" max="9999" step="1" required>
      </label>
      <label class="field">
        Número de páginas
        <input id="pages" type="number" min="0" max="9999" step="1" required>
      </label>
    </div>

    <label class="field">
      Última lectura
      <input id="lastRead" type="date">
    </label>
    <button id="read-today" type="button">Marcar lectura de hoy</button>
    <p class="notice">
      Usa 0 si aún no sabes cuántas páginas tiene.
      Los repasos y la fecha de lectura se registran de forma independiente.
    </p>

    <div class="actions">
      <button id="cancel" type="button">Cancelar</button>
      <button class="primary" type="submit">Guardar cambios</button>
    </div>
  </form>
</dialog>

<script>
"use strict";

/*
  Puedes sustituir estos nombres por los títulos completos.
  Mantén los 71 elementos en el mismo orden.
*/
const TITULOS = Array.from({ length: 71 }, (_, i) => `Tema ${i + 1}`);

const STORAGE_KEY = "orbita-tecnologia-v1";
const $ = id => document.getElementById(id);
const labels = {
  pending: "Pendiente",
  progress: "En progreso",
  done: "Al día",
  review: "Por repasar"
};

let selectedId = null;
let topics = createTopics();

function createTopics() {
  return TITULOS.map((title, i) => ({
    id: i + 1,
    title,
    updated: false,
    studied: false,
    outline: false,
    reviews: 0,
    pages: 0,
    lastRead: ""
  }));
}

function today() {
  const d = new Date();
  return [
    d.getFullYear(),
    String(d.getMonth() + 1).padStart(2, "0"),
    String(d.getDate()).padStart(2, "0")
  ].join("-");
}

function validDate(value) {
  if (value === "") return true;
  if (!/^\d{4}-\d{2}-\d{2}$/.test(value)) return false;
  const d = new Date(value + "T00:00:00Z");
  return !Number.isNaN(d.getTime()) &&
    d.toISOString().slice(0, 10) === value &&
    value <= today();
}

function validate(data) {
  if (!Array.isArray(data) || data.length !== 71) {
    throw new Error("La copia debe contener exactamente 71 temas.");
  }

  return data.map((t, i) => {
    if (!t || t.id !== i + 1 ||
        typeof t.title !== "string" ||
        !t.title.trim() || t.title.length > 250 ||
        !["updated", "studied", "outline"].every(k => typeof t[k] === "boolean") ||
        !["reviews", "pages"].every(k =>
          Number.isInteger(t[k]) && t[k] >= 0 && t[k] <= 9999
        ) ||
        typeof t.lastRead !== "string" ||
        !validDate(t.lastRead)) {
      throw new Error("Hay datos no válidos en uno o varios temas.");
    }

    return {
      id: t.id,
      title: t.title.trim(),
      updated: t.updated,
      studied: t.studied,
      outline: t.outline,
      reviews: t.reviews,
      pages: t.pages,
      lastRead: t.lastRead
    };
  });
}

function notify(text) {
  $("message").textContent = text;
}

function save(next) {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(next));
    topics = next;
    return true;
  } catch {
    notify("No se pudo guardar. Revisa el almacenamiento del navegador y exporta una copia.");
    return false;
  }
}

try {
  const saved = localStorage.getItem(STORAGE_KEY);
  if (saved) topics = validate(JSON.parse(saved));
} catch {
  notify("No se pudieron cargar los datos guardados. Puedes importar una copia de seguridad.");
}

function daysSince(t) {
  if (!t.lastRead) return null;
  return Math.round((
    Date.parse(today() + "T00:00:00Z") -
    Date.parse(t.lastRead + "T00:00:00Z")
  ) / 86400000);
}

function status(t) {
  if (t.studied) {
    const days = daysSince(t);
    return days === null || days >= 7 ? "review" : "done";
  }
  if (t.updated || t.outline || t.reviews > 0 || t.lastRead) return "progress";
  return "pending";
}

function escapeHTML(value) {
  return String(value).replace(/[&<>"']/g, c => ({
    "&": "&amp;", "<": "&lt;", ">": "&gt;",
    '"': "&quot;", "'": "&#39;"
  })[c]);
}

function readingText(t) {
  const days = daysSince(t);
  if (days === null) return "Sin lecturas registradas";
  if (days === 0) return "Última lectura: hoy";
  if (days === 1) return "Última lectura: hace 1 día";
  return `Última lectura: hace ${days} días`;
}

function render() {
  const studied = topics.filter(t => t.studied).length;
  const updated = topics.filter(t => t.updated).length;
  const reviews = topics.reduce((total, t) => total + t.reviews, 0);
  const due = topics.filter(t => status(t) === "review").length;

  $("summary").innerHTML = [
    [`${studied} / 71`, "Temas estudiados"],
    [`${updated} / 71`, "Temas actualizados"],
    [reviews, "Repasos realizados"],
    [due, "Temas por repasar"]
  ].map(([value, label]) =>
    `<div class="stat"><strong>${value}</strong><span>${label}</span></div>`
  ).join("");

  const query = $("search").value.trim().toLocaleLowerCase("es");
  const filter = $("filter").value;

  const visible = topics.filter(t => {
    const matchesText = `${t.id} ${t.title}`.toLocaleLowerCase("es").includes(query);
    const matchesFilter =
      filter === "all" ||
      (filter === "studied" && t.studied) ||
      (filter === "long" && t.pages > 10) ||
      status(t) === filter;
    return matchesText && matchesFilter;
  });

  $("count").textContent = `Mostrando ${visible.length} de 71 temas`;

  $("topics").innerHTML = visible.map(t => `
    <article class="card ${status(t)}">
      <div class="card-top">
        <span class="number">TEMA ${String(t.id).padStart(2, "0")}</span>
        <span class="badge">${labels[status(t)]}</span>
      </div>
      <h3>${escapeHTML(t.title)}</h3>
      <div class="checks">
        ${[
          ["updated", "Actualizado"],
          ["studied", "Estudiado"],
          ["outline", "Esquema"]
        ].map(([key, label]) =>
          `<span class="check ${t[key] ? "yes" : ""}">
            ${t[key] ? "✓" : "○"} ${label}
          </span>`
        ).join("")}
      </div>
      <div class="details">
        <span>${t.reviews} ${t.reviews === 1 ? "repaso" : "repasos"}</span>
        <span>${t.pages ? t.pages + " páginas" : "Páginas sin registrar"}</span>
      </div>
      <p class="warning">${t.pages > 10 ? "⚠ Tema extenso: más de 10 páginas" : ""}</p>
      <p class="reading">${readingText(t)}</p>
      <div class="card-footer">
        <span>Avanza a tu ritmo</span>
        <button data-edit="${t.id}" aria-label="Editar tema ${t.id}">Editar</button>
      </div>
    </article>
  `).join("");

  if (!visible.length) {
    $("topics").innerHTML = "<p>No hay temas con estos filtros.</p>";
  }
}

function openEditor(id) {
  selectedId = id;
  const t = topics.find(t => t.id === id);
  $("editing-number").textContent = `TEMA ${id}`;

  for (const key of ["title", "reviews", "pages", "lastRead"]) {
    $(key).value = t[key];
  }
  for (const key of ["updated", "studied", "outline"]) {
    $(key).checked = t[key];
  }

  $("lastRead").max = today();
  $("editor").showModal();
}

$("topics").addEventListener("click", event => {
  const button = event.target.closest("[data-edit]");
  if (button) openEditor(Number(button.dataset.edit));
});

$("cancel").addEventListener("click", () => $("editor").close());

$("read-today").addEventListener("click", () => {
  $("lastRead").value = today();
});

$("form").addEventListener("submit", event => {
  event.preventDefault();

  const edited = {
    id: selectedId,
    title: $("title").value.trim(),
    updated: $("updated").checked,
    studied: $("studied").checked,
    outline: $("outline").checked,
    reviews: Number($("reviews").value),
    pages: Number($("pages").value),
    lastRead: $("lastRead").value
  };

  try {
    const next = validate(topics.map(t => t.id === selectedId ? edited : t));
    if (save(next)) {
      $("editor").close();
      render();
      notify("Progreso guardado.");
    }
  } catch (error) {
    alert(error.message);
  }
});

$("search").addEventListener("input", render);
$("filter").addEventListener("change", render);

$("export").addEventListener("click", () => {
  const blob = new Blob([JSON.stringify(topics, null, 2)], {
    type: "application/json"
  });
  const url = URL.createObjectURL(blob);
  const link = document.createElement("a");
  link.href = url;
  link.download = `oposicion-tecnologia-${today()}.json`;
  document.body.appendChild(link);
  link.click();
  link.remove();
  setTimeout(() => URL.revokeObjectURL(url), 1000);
});

$("import").addEventListener("click", () => $("file").click());

$("file").addEventListener("change", async event => {
  const file = event.target.files[0];
  if (!file) return;

  try {
    if (file.size > 300000) throw new Error("El archivo es demasiado grande.");
    const data = validate(JSON.parse(await file.text()));

    if (!confirm("Esta copia sustituirá el progreso actual. ¿Continuar?")) return;

    if (save(data)) {
      render();
      notify("Copia importada correctamente.");
    }
  } catch (error) {
    notify(error instanceof SyntaxError
      ? "El archivo no contiene JSON válido."
      : error.message);
  } finally {
    event.target.value = "";
  }
});

window.addEventListener("focus", render);
setInterval(render, 60000);
render();
</script>
</body>
</html>
