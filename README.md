# DDI Alliance Training Working Group

Open training materials produced by the [DDI Alliance](https://ddialliance.org) **Training Working Group (TWG)**. The repository hosts self-paced microlearning courses (MOOCs) about the Data Documentation Initiative (DDI) metadata standards. The courses are published as static web pages through GitHub Pages.

**Live site:** <https://ddialliance.github.io/Training-Working-Group/>

---

## Courses

| # | Course | Standard | Audience | Links |
|---|--------|----------|----------|-------|
| 1 | **Improving Health Research Visibility through Metadata:** a microlearning approach using the DDI Codebook standard | DDI Codebook | Health researchers, data managers, data professionals | [Course](https://ddialliance.github.io/Training-Working-Group/moocs/1.Improving%20Health%20Research%20Visibility%20through%20Metadata/) · [Final quiz](https://ddialliance.github.io/Training-Working-Group/moocs/1.Improving%20Health%20Research%20Visibility%20through%20Metadata/final-quiz/) |

### 1. Improving Health Research Visibility through Metadata

This course shows how metadata turns raw health research data into resources that others can discover, understand and reuse. It covers the FAIR principles (Findable, Accessible, Interoperable, Reusable), explains the difference between ordinary documentation and machine-readable metadata, and walks through a practical workflow using the DDI Codebook standard.

**Modules**

1. **Metadata foundations**
   - 1.1 What is metadata, and why does it matter? *(video)*
   - 1.2 Why health data needs a metadata standard *(video)*
   - 1.3–1.4 Key concepts: data vs. metadata, FAIR, structured vs. free-text metadata, plus a knowledge check
   - 1.5 Transcripts and references
2. **Applying DDI Codebook**
   - 2.1 Concept map: the metadata visibility chain (study → DDI metadata → XML/JSON export → NADA catalogue → discovery and reuse)
   - 2.2 From invisible to visible: how metadata changes research discovery *(video)*
   - 2.3 Creating structured metadata with the Metadata Editor *(video demo and practice resources)*
   - 2.4 Publishing metadata on the NADA catalogue *(video demo and practice resources)*
   - 2.5 Knowledge check
3. **Putting it into practice**
   - 3.1 Recommendations for institutions: a collaborative culture, standard SOPs, starting early, publishing and sharing
   - 3.2 Knowledge check
   - 3.3 Resources and repositories: DDI training materials, the CODATA/DDI webinar, Metadata Editor, NADA, and the MEIRU data repository
4. **Final quiz.** Five questions that cover all three modules. Learners who complete it receive a course completion summary.

**Contributors:** DDI Training Working Group; Dominic Nzundah (MEIRU)

---

## Repository structure

```
Training-Working-Group/
├── README.md                          # This file
└── moocs/
    └── <n>.<Course title>/            # One folder per course, numbered in release order
        ├── README.md                  # Course summary and public link
        ├── index.html                 # Course content (self-contained H5P export)
        ├── <content-id>/images/       # Images referenced by index.html
        └── final-quiz/
            └── index.html             # Final assessment (self-contained H5P export)
```

## Technical notes

- **Format.** The courses are standalone [H5P](https://h5p.org) exports. The main course uses `H5P.CoursePresentation` and the final quiz uses `H5P.QuestionSet`. Each `index.html` bundles the H5P runtime, styles and content, so no build step or server-side component is needed.
- **Hosting.** GitHub Pages serves the files directly from this repository.
- **External media.** Videos are embedded from YouTube, and the video transcripts are linked on Google Drive. Learners need an internet connection to watch them.
- **Progress tracking.** H5P emits xAPI statements, but no LRS is set up in this deployment, so the browser does not store progress or scores between sessions.
- **File size.** Each `index.html` is about 2.5 MB because the whole H5P runtime is inlined.

### Viewing locally

```bash
git clone https://github.com/ddialliance/Training-Working-Group.git
cd Training-Working-Group
python3 -m http.server 8000
# then open http://localhost:8000/moocs/
```

Opening `index.html` straight from disk (`file://`) usually works too. Some embedded media may not load that way, so a local server is the safer option.

---

## Adding a new course

1. Build the course in H5P (for example on H5P.com or Lumi), then export it as a standalone HTML package.
2. Create a folder named `moocs/<next-number>.<Course title>/`.
3. Put the exported `index.html` and its asset folders inside it. If the course has a separate assessment, put it in a subfolder such as `final-quiz/`.
4. Add a short `README.md` to the course folder with the course title, a one-paragraph summary and the GitHub Pages link.
5. Add a row to the **Courses** table above.
6. Check that every link in the course points to the published GitHub Pages URL and not to a local or authoring-tool URL.

> Folder names containing spaces produce URLs with `%20`. Future courses may be easier to link to with a short, hyphenated folder name (for example `moocs/2-ddi-lifecycle-intro/`).

## Contributing

Corrections, translations and new course proposals are welcome. Please open an issue or pull request, or contact the DDI Alliance Training Working Group through the [DDI Alliance website](https://ddialliance.org).

## Related resources

- [DDI Alliance](https://ddialliance.org)
- [DDI training materials](https://ddialliance.org/training)
- [Metadata Editor](https://worldbank.github.io/metadata-editor-docs/), a multi-standard open-source metadata editor
- [NADA](https://nada.ihsn.org), a microdata cataloguing tool

## License

This repository does not include a license file yet. Until the Working Group adds one, please contact the DDI Alliance before reusing or adapting these materials.
