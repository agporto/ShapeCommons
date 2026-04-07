# ShapeCommons

ShapeCommons is an open repository of community-contributed Statistical Shape Models (SSMs), focused on models generated with [ATLAS](https://github.com/agporto/ATLAS) and reusable by others (including partner initiatives such as [TraitBlender](https://github.com/Imageomics/TraitBlender)).

The goal is to keep contributions open, understandable, and easy to reuse.

---

## Repository structure

Each SSM is stored as one folder at the repository root:

```text
ShapeCommons/
  <ssm_id>/
    README.md
    dense_correspondence.mrk.json
    manifest.json
    sparse_landmarks.mrk.json
    ssm_model.npz
    template_model.ply
    data/
      data_manifest.csv
```

---

## Minimum submission requirements

Inside each `<ssm_id>/` folder, contributors must include:

- `README.md` (follow the template in this file)
- `dense_correspondence.mrk.json`
- `manifest.json`
- `sparse_landmarks.mrk.json`
- `ssm_model.npz`
- `template_model.ply`
- `data/data_manifest.csv`

If one required file is missing, the PR is not ready for review.

---

## Licensing rules (open-only)

- The submitted SSM package must use an open license: `CC0-1.0`, `CC-BY-4.0`, `MIT`, `BSD-2-Clause`, or `BSD-3-Clause`.
- Contributors must declare the SSM package license clearly.
- Only upload files you have legal rights to share.
- Source dataset links/references should be included for provenance.

---

## Metadata rules (simple, essential)

Each contribution must state:

- where the training data came from (institution/repository/publication/DOI/URL),
- what the dataset broadly represents,
- final sample size used for training (`n`),
- basic software context (ATLAS version/commit if known, 3D Slicer version if known).


---

## Naming convention

Preferred folder name format:

```text
<genus>_<species>_<structure_name>_<uberon_optional>_<version>
```

Examples:

- `canis_lupus_cranium_uberon_0003126_v1`
- `canis_lupus_cranium_v1`
- `helix_pomatia_shell_v2`

Rules:

- lowercase, numbers, and underscores only
- no spaces
- short and descriptive names
- use `genus_species` when biological taxonomy applies
- include an Uberon ID when available (encouraged, optional)

---

## Per-SSM README template (required)

Copy this into each SSM folder as `README.md` and fill it in.

```markdown
# <SSM Title>

## 1. Summary
- **SSM ID:** `<folder_name>`
- **Status:** `stable | experimental`
- **Domain:** `<e.g., vertebrate cranial morphology>`
- **Anatomical structure:** `<structure>`

## 2. Contributors
- **Maintainer:** `<name, affiliation, contact>`
- **Contributors:** `<list>`

## 3. Licensing
- **SSM package license:** `<CC0-1.0 | CC-BY-4.0 | MIT | BSD-2-Clause | BSD-3-Clause>`
- **Derivative work note:** `<derived from source dataset/repository>`
- **Redistribution notes:** `<what is redistributed in this SSM package>`

## 4. Dataset provenance
- **Source type:** `<museum collection | published dataset | simulated | mixed>`
- **Source details:** `<institution/repository/DOI/URL>`
- **Access date:** `<YYYY-MM-DD>`
- **Final sample size (n):** `<integer>`
- **Taxonomic/biological scope:** `<scope>`

## 5. Model generation
- **ATLAS version/commit:** `<value or unknown>`
- **3D Slicer version:** `<value or unknown>`
- **Optional notes:** `<anything important not obvious from files>`

## 6. Citation
- **How to cite this SSM:** `<citation text>`
- **Related publications:** `<DOI/links>`
```

---

## What goes in `data/data_manifest.csv`

`data/data_manifest.csv` is a simple manifest of the training specimens used to build the SSM.

Required columns:

- `specimen_id` - unique specimen/sample ID used by contributor
- `source` - institution/repository/publication for that specimen
- `accession_or_record_id` - catalog/accession/record ID (use `na` if unavailable)
- `taxon`
- `anatomical_structure`

Recommended columns:

- `notes`

Example:

```csv
specimen_id,source,accession_or_record_id,taxon,anatomical_structure,notes
sp001,Museum X,MX-123,na,Canis lupus,cranium,adult
sp002,Dataset DOI:10.xxxx/abcd,na,Canis lupus,cranium,juvenile
```

---

## Maintainer review checklist

Each PR is checked for:

- required files present,
- open-license clarity,
- basic provenance metadata present,
- files are readable and point counts are coherent.

Maintainers may request fixes before merge.

---

## What not to upload

- files you do not have rights to redistribute,
- personal or sensitive data,
- models with missing provenance metadata.

---

## Related projects

- ATLAS: [https://github.com/agporto/ATLAS](https://github.com/agporto/ATLAS)
- TraitBlender: [https://github.com/Imageomics/TraitBlender](https://github.com/Imageomics/TraitBlender)
