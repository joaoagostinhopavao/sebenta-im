# Instruções
Primeiro fazer o render:

- em português:
 ```bash
quarto render
```
- em inglês:
  ```bash
  quarto render en/ 
  ```
Para fazer o upload para o github em PT
```bash
git add docs/
git commit -m "Descrição da alteração" 
git push

```
Para fazer o upload para o github em EN

```bash
  git add docs/en/ en/
  git commit -m "Add English chapter 7 — Web Architecture and REST"
  git push
```

Quando se faz o render é também gerada a sebenta PDF em português. Não é gerada em inglês. Para tal teria que se incluir a secçãp pdf: no `_quarto.yml` da pasta `en`.

A sebenta em português é gerada em `docs/Informática-Médica.pdf`

---

## Cap. 11 — Versões Simplificada (HTML) e Estendida (PDF)

O Cap. 11 tem duas versões que são seleccionadas automaticamente pelo Quarto consoante o formato de saída:

| Ficheiro | Conteúdo | Formato |
|---|---|---|
| `capitulos/_cap11-short.qmd` | Versão simplificada — fundamentos e legislação | HTML (site) |
| `capitulos/_cap11-estendido.qmd` | Versão completa — inclui DICOM, FHIR, SMART e ATNA detalhados | PDF |
| `capitulos/cap11.qmd` | Só contém os includes condicionais — **não editar directamente** | — |

O ficheiro `cap11.qmd` selecciona automaticamente qual das versões incluir:

```markdown
::: {.content-visible when-format="html"}
{{< include _cap11-short.qmd >}}
:::

::: {.content-visible when-format="pdf"}
{{< include _cap11-estendido.qmd >}}
:::
```

Um único `quarto render` produz o site HTML com a versão simplificada e o PDF com a versão estendida. Não são necessários comandos adicionais.

Para editar o conteúdo do Cap. 11:
- Conteúdo do site → editar `capitulos/_cap11-short.qmd`
- Conteúdo do PDF → editar `capitulos/_cap11-estendido.qmd`
