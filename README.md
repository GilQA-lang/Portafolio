# Portafolio — Gilkeira Pereira

Sitio web personal de **Gilkeira Pereira**, Quality Engineer con 14+ años de experiencia.

Hospedado en GitHub Pages: `https://gilqa-lang.github.io/Portafolio/` — repo: `github.com/GilQA-lang/Portafolio`
(⚠ la **P** va en mayúscula: GitHub Pages distingue mayúsculas en la ruta, y de ahí dependen las
URL de `og:image` y `og:url` del `index.html`.)

## Estructura

- `index.html` — Sitio completo (HTML + CSS + JS en un solo archivo)
- `caso-de-estudio.html` — Caso de estudio del método (página aparte, enlazada desde el menú y desde
  «Ingeniería propia»). Lleva una **copia del bloque `<style>` de `index.html`** más su propio estilo al final
  (marcado «Caso de estudio»): si cambia el estilo de `index.html`, copiarlo también aquí.
- `Gilkeira_Pereira_CV_2026_v5.pdf` — CV descargable
- `foto-gilkeira.jpg` — Retrato del hero (760×950, 78 KB).
  Fuente original: `D:\MisProyectos\gpereira.-Varios\Foto Perfil Gilkeira Pereira.jpg`
  (3064×4096). Recorte 4:5 desde arriba + resize LANCZOS + JPEG q84 progresivo.
  Para regenerarla, repetir ese tratamiento — no subir el original de 765 KB.

## Publicar en GitHub Pages

1. Crear repo público en GitHub llamado `portafolio` (o el nombre que prefieras).
2. Subir estos archivos al repo.
3. En GitHub → **Settings** → **Pages** → **Source: Deploy from a branch** → **Branch: main / (root)** → Save.
4. En 1-2 minutos estará disponible en la URL indicada.

## Actualizar

Para cambiar contenido, editar `index.html` directamente. Los datos están en HTML plano, fáciles de modificar.

Para actualizar el CV: reemplazar `Gilkeira_Pereira_CV_2026_v5.pdf` con la versión nueva (mantener el mismo nombre) o
actualizar los links: 3 en `index.html` (menú, inicio y contacto) y 1 en `caso-de-estudio.html` (menú).

## Datos de los logros

Las cifras de la sección **Logros** no se editan a ojo: cada una tiene su respaldo documentado
—fórmula, antes/después, período, fuente y quién puede validarla— **fuera de este repositorio**.
**Regla: ninguna cifra entra al sitio sin ese respaldo completo.**

Los mini-gráficos de cada tarjeta se generan solos desde los atributos del HTML:

```html
<div class="viz" data-a="201" data-b="17" data-unit="defectos" data-la="Antes" data-lb="Hoy"></div>
```

`data-a` = antes, `data-b` = hoy.

### Cuando el valor absoluto no es publicable

Algunas cifras son desempeño interno de la empresa y **no van al sitio**: para esas, lo que se
publica es la **relación** y no el valor absoluto. En esos casos el gráfico dibuja la
**proporción** y se le apagan los números — si no, el dato que se sacó del texto queda visible
en la barra **y en el código fuente**, que cualquiera lee con Ctrl+U:

```html
<div class="viz" data-a="100" data-b="40" data-hide-values="1"
     data-alt="Los ciclos de prueba por ítem se redujeron a menos de la mitad."></div>
```

- `data-hide-values="1"` — dibuja las barras sin valores ni tooltips.
- `data-alt` — obligatorio en ese caso: es el texto que leen los lectores de pantalla,
  que si no se quedarían sin la información.
- Los valores pasan a ser **relativos** (100 y 40 = «menos de la mitad»), así el número real
  tampoco aparece en el HTML. El script del final del archivo dibuja las dos barras sobre
una escala común. Para cambiar un número basta editar el atributo — no hay que tocar el SVG.
Las etiquetas (`data-la`/`data-lb`) deben ser **cortas** (~6 caracteres): son un `<text>` de
ancho fijo y una etiqueta larga se superpone con la barra.

El color de las marcas es `#2f9fbb`, elegido con el validador de paleta (banda de luminosidad,
croma y contraste ≥3:1 sobre la tarjeta) — **no es el acento de la UI**, que queda fuera de banda.
