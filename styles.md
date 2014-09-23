---
Base:
    default:                 
        metadata:
            numbersections: true
    latex:
        metadata:
            lang      : british
            papersize : a4paper
        preflight:
            - run: tmp_out.py
        # filter:
        #     - run: smallcaps.py
        #     - run: optimise_bib.py
        #       args:
        #           - verbose: true
        #           - bibliography: mds.bib
        # postprocess:
        #     - run: sort
        postflight :
            - run : latexmk.py
            - run : pplatex.py
            - run : open_pdf.py
        cleanup :
            - run : tmp_back.py
            - run : rmlatex.py
                    
Notes:
    latex:
        template:     notes.latex
        metadata:
            fontsize : 12pt
            headings : sans-serif

Mumford:
    latex:
        template : mumford.latex
        metadata :
            fontsize: 12pt

Article:
    latex:
        template : article.latex
        metadata :
            fontsize     : 12pt
            title        : Untitled document
            author       : No author
            affiliation  : No affiliation
            email        : no@email
            published    : "*Draft only. Please do not cite without permission.*"
            biblio-files : /Users/msprevak/Library/texmf/bibtex/bib/mds-bib/refs
            bibliography : Mental-fictionalism.bib
            
Letter:    
    latex:
        template: letter-UoE.latex


CV:    
    latex:
        template: notes.latex
        metadata: 
            fontsize: 12pt
            headings: sans-serif

MSWord:  
    latex:
        template: notes.latex
        metadata: 
            fontsize: 12pt
            headings: sans-serif
...

