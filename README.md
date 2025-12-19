# (Unofficial) AHFE Conference Latex Template

> AHFE is short for The Applied Human Factors and Ergonomics International (AHFE).

## Motivation

The original template can not compile on Overleaf due to missing `npsaq` style.

```
# In ahfe.cls file, Line 2808
\usepackage{npsaq}
```

The fix for this issue is to comment it out, `% \usepackage{npsaq}`.

## Other Fixes

- Other than the missing style file, there is another major issue is the **citation** format.

    Currently, in the latex template, it using the plain text for the citation `(author, year)`, but the best practice is using the `\cite` command. Besides that, the `REFERENCES` section uses the `\bibitem` command, which makes it hard to maintain, i.e., manually copy and paste plain text and sort them in the Harvard referencing style (unnumbered, alphabetized).

    **Fix**: 

  - Update `documentclass` from 

    `\documentclass[unnumsec,webpdf,modern,small]{ahfe}%`

    to 

        `\documentclass[unnumsec,webpdf,modern,small,namedate]{ahfe}%`

  - Update references section from

    ```
    \begin{thebibliography}{10}\clubpenalty10000\widowpenalty10000

    \bibitem{bib1}Booher, Harold, ed. (2003). Handbook of human systems integration.

    \end{thebibliography}
    ```

    to 

    ```
    \bibliographystyle{agsm}
    \bibliography{ahfe-sample}
    ```

  - Write all references to the `bib` file.

    **NOTE: To match the original reference style '(author, year)', it requires to use the \citep{} command other than the \cite{} command.**

- Figures and tables should also use the `\ref{}` command.

## Missing Style files on Local Environment

Sometimes, the template doesn't work on local environment, such as MikTex on Windows, because of missing `stfloats.sty` and `flushend.sty` files.

In case, these two files are included in the `Revised Template` folder.

## Template Reference

- The original template is located in [Original Template](./Original%20Template/).
- The revised template is located in [Revised Template](./Revised%20Template/).

## Tip

As the current system only accepts the `doc/docx` file, if the pdf is generated from this latex template, use **Adobe Acrobat** to convert it. After that, open the the file with **Word**, and print it as a PDF file. Then, the `doc` file and the `pdf` file match.

> **Word** can do the pdf-doc convertion too, but according to my test, the layout is messed up. 