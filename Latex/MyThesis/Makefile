################################################################################
###                                                                          ###
###      PhD Thesis LaTeX TEMPLATE at Genome BioInformatics Laboratory       ###
###                                                                          ###
###      --- PhD Makefile: use make and forget about dependencies ---        ###
###                                                                          ###
################################################################################
###                                                                          ###
###      CopyLeft 2004 and beyond, by Josep F. Abril - jabril@imim.es        ###
###                                                                          ###
###    This thesis template has been adapted from Sergi Castellano and       ###
###    Genis Parra templates (2004),  which, in turn, largerly derived       ###
###    from Robert Castelo and Sergio Mendoza PhD thesis templates (2002).   ###
###                                                                          ###
###                   Under GNU/GPL copyleft license                         ###
###                                                                          ###
###              Questions and suggestions are WELCOMED !!!                  ###
###                  FEEL FREE TO USE AND IMPROVE IT !!!                     ###
###                                                                          ###
################################################################################
###
###  $Id$
###

########################
###    Disclaimer    ###
################################################################################
##     It compiles your thesis but it does NOT write it... ;^P                ##
################################################################################

# SECONDS = $(shell date +'%s') # now being run within the mkheader target

### MAKE VARS

.PHONY     : clean cleanall forceall
.DEFAULT   : pdf
.PRECIOUS  : %.tex %.bib %.bbl %.tpt \
             %.toc %.lot %.lof %.ind %.ist %.glo %.act %.wlt \
             %.png %.jpg %.gif %.eps %.ps  %.pdf \
             %.tgz %.gz  %.zip \
             README
             # %.rc  %.gff %.gb  %.fa  %.R  .bash_VARS
.SECONDARY : %.aux %.out %.log %.blg %.dvi %.s.ps \
             %.ilg %.idx %.glg %.gls %.alg %.acn %.wlg %.wln  
.SUFFIXES  :


### COMMANDS

    DATE = $(shell date)
    USER = $(shell whoami)

       V = -v

      LS = $(firstword $(shell which ls     ))
      LL = $(LS) -1
      RM = $(firstword $(shell which rm     )) $(V)
      RD = $(firstword $(shell which rmdir  )) $(V)
      CP = $(firstword $(shell which cp     )) $(V)
      MV = $(firstword $(shell which mv     )) $(V)
      LN = $(firstword $(shell which ln     )) $(V)
      MD = $(firstword $(shell which mkdir  )) $(V)
     CHM = $(firstword $(shell which chmod  )) $(V) -c
     CHO = $(firstword $(shell which chown  )) $(V) -c

    TTAR = $(firstword $(shell which tar    )) $(V) -ztf
    CTAR = $(firstword $(shell which tar    )) $(V) -zcf
    GZIP = $(firstword $(shell which gzip   )) $(V) --best --force

   LATEX = $(firstword $(shell which latex     ))
PDFLATEX = $(firstword $(shell which pdflatex  ))
  BIBTEX = $(firstword $(shell which bibtex    ))
 MKINDEX = $(firstword $(shell which makeindex ))
THUMBPDF = $(firstword $(shell which thumbpdf  ))
   DVIPS = $(firstword $(shell which dvips     )) # -D 600 -t a4
   PSNUP = $(firstword $(shell which psnup     )) -pa4 -Pa4 -d -2 -m0.25cm
  TANGLE = $(LBIN)/no tangle
   WEAVE = $(LBIN)/no weave
    CPIF = $(firstword $(shell which cpif  ))
   TOUCH = $(firstword $(shell which touch ))

    GAWK = $(firstword $(shell which gawk))
   GAWKV = $(shell $(GAWK) --version | \
             $(GAWK) '$$0 ~ /^GNU Awk/ { print $$0; }')
    BASH = $(firstword $(shell which bash))
   BASHV = $(shell $(BASH) --version | \
             $(GAWK) '$$0 ~ /^GNU bash/ { print $$0; }')
    PERL = $(firstword $(shell which perl))
   PERLV = $(shell $(PERL) --version | \
             $(GAWK) '$$0 ~ /^This/ { \
                        gsub(/^This is perl,[ \t]+/,"",$$0); \
                        print $$0; \
                      }')


### LOCAL PATHS

# this will serve as directory root and main LaTeX file
     MAIN   = thesis
    COVER   = cover
    INTRO   = introduction
 GENOMICS   = genomics
 ALGORITHMS = algorithms
GENEFINDING = genefinding
       META = meta
      MMETA = mmeta
	   MISC = miscellanea

          # where to find each set of files
     WORK = .
     CONF = $(WORK)/conf
 SECTIONS = $(WORK)/sections
   TABLES = $(WORK)/tables
   PAPERS = $(WORK)/papers
    PSDIR = $(WORK)/ps
   BUILDS = $(WORK)/docbuilds

TEXINPUTS = $(WORK)//:$(shell echo $$TEXINPUTS)


### thesis.tex dependencies

 HEADERIST = $(addprefix $(CONF)/, header.ist )

     logos = $(addprefix $(PSDIR)/, crg fimim grib imim \
                                    isciii mcyt prbb upf upc_dept )

    papers = $(addprefix $(PAPERS)/, 2006_PLOS      \
                                     2006_NAR       \
                                     2004_EMBO      \
									 2003_PNAS      \
									 2000_GenRes    \
									 2005_Baxevanis \
									 2002_Baxevanis)

    covers = $(addsuffix _cover, $(papers))

   posters = $(addprefix $(PSDIR)/, 2000_GenRes_poster  \
                                    2000_Science_poster \
                                    2001_Science_poster \
                                    2002_Science_poster )

       png = $(addprefix $(PSDIR)/, cell                 \
                                    proteinp             \
                                    gcode                \
                                    chromo1              \
                                    chromo2              \
                                    chromo3              \
                                    gcompo1              \
                                    gcompo2              \
                                    gbgrowth             \
                                    gbentry1             \
                                    gbentry2             \
                                    gbentry3             \
                                    gbrowsers1           \
                                    gbrowsers2           \
                                    snp1                 \
                                    snp2                 \
                                    homology             \
                                    nw                   \
                                    dp                   \
                                    hir1                 \
                                    hir2                 \
                                    hir3                 \
                                    fasta                \
                                    enzyme1              \
                                    enzyme2              \
                                    enzyme3              \
                                    enzyme4              \
                                    map                  \
                                    prev                 \
                                    dp3                  \
                                    dp4                  \
                                    mI                   \
                                    iprofile             \
                                    iprofiletwo          \
                                    Llist                \
                                    Rlist                \
                                    blast                \
									genestruct           \
									alts1                \
                                    alts2                \
									trans                \
									nucleos1             \
									nucleos2             \
									signals              \
	                                exons                \
									genes                \
									sitealn              \
									seqlogo              \
									cusage               \
									gff2aplot1			 \
									gff2aplot2			 \
									gff2aplot3			 \
									phylo1               \
									phylo2               \
									pwm        		     \
									geneid1				 \
									geneid2				 \
									verde				 \
									rojo				 \
									ratio				 \
									modules              \
									hgenome              \
									dummy                \
									sparsem1             \
									sparsem2             \
									sparsem3             \
									access               \
									abs                  \
									pspla                \
									testregionsS         \
									testpromoter         \
                                    cisred               \
									gumbel1              \
									gumbel2              \
									pwmsnew              \
									qmat1                \
									qmat2                \
									bitT                 \
									CSHL_2005            \
									CSHL_2004            \
									dmapping             \
									oneline              \
									extended			 \
									progressive          \
									mmads                \
								    scases				 \
									noncol               \
									areas                \
									ncparam              \
									testregions          \
									a00					 \
									MMP13				 \
									mememma              \
									chronogram           \
									posterloc1           \
									posterloc2           \
									posterloc3           \
									ttr                  \
									gumbelloc1           \
									gumbelloc2           \
									ttrc                 \
									3dcube               \
									lipman0				 \
									lipman1				 \
									clustalwproc         \
                                    signature_eblanco    \
                                    signature_rguigo     )

   texfigs = $(addprefix $(TABLES)/,  gsizes          \
                                      code1           \
                                      code2           \
									  accuracy        \
									  maccuracy       \
									  maccuracy2      \
									  testregions     \
									  testpromoter    \
									  ttr             \
                                      qvalue          \
                                      qvalue2         \
									  qcolls          \
									  testregionsM)

# WARNING: Do not use wildcards here (as a safety measure),
# those files are removed when making clean, cleanaux or cleanall
    tmpfiles = $(addprefix $(WORK)/$(MAIN), .dvi ) \
              $(addprefix $(WORK)/$(COVER), .dvi )
    auxfiles = $(addprefix $(WORK)/$(MAIN), .toc .lot .lof .tpt \
                                            .bbl .ind .gls .acn .wln .ist .mtc*) \
              $(addprefix $(WORK)/$(COVER), .toc .lot .lof .tpt \
                                            .bbl .ind .gls .acn .wln .ist )
 preauxfiles = $(addprefix $(WORK)/$(MAIN),      .idx .glo .act .wlt ) \
               $(addprefix $(WORK)/$(COVER),     .idx .glo .act .wlt )
    logfiles = $(addprefix $(WORK)/$(MAIN), .blg .ilg .glg .alg .wlg \
                                            .log .aux .out           ) \
              $(addprefix $(WORK)/$(COVER), .blg .ilg .glg .alg .wlg \
                                            .log .aux .out           )

### Other files dependencies

$(addprefix $(CONF)/, preamble.tex) : \
                         $(addprefix $(CONF)/, define_booleans.tex \
                                               mythesis.sty        )

$(HEADERIST) :

##################
### MAKE RULES #################################################################
##################

# DO NOT FORGET to have a TAB character at the beginning of every command line!

### MAIN TARGETS

all      : header mkfigs mkdraft mkproof mkpress mkpdf trailer
mkall    : header mkfigs mkdraft mkproof mkpress mkpdf mkps mkpsdraft trailer
press    : header mkfigs mkpress ### mkcover trailer
proof    : header mkfigs mkproof    trailer
pdf      : header mkfigs mkpdf      trailer
ps       : header mkfigs mkps       trailer
draft    : header mkfigs mkdraft    trailer
psdraft  : header mkfigs mkpsdraft  trailer
cover    : header mkfigs mkcover    trailer

backup   : header mkbackup   trailer

clean    : header mkclean    trailer

cleanaux : header mkcleanaux trailer

cleanall : header mkcleanall trailer

force    : header mktouch mkfigs mkdraft mkproof \
                          mkpress mkcover mkpdf trailer
forceall : header mktouch mkfigs mkdraft mkproof \
                          mkpress mkcover mkpdf mkpsdraft mkps trailer

mktouch :
	@touch $(WORK)/$(MAIN).tex


### STORING, CLEANING and FORCING

mkbackup :
	@echo "### Making a BACKUP tarball of the project..." ;
	@cd $(WORK)/..; pwd; \
	 $(CTAR) $(MAIN).tgz $(MAIN);
	@echo "### A new BACKUP tarball of the project is available: $(MAIN).tgz" ;

define saferm
	$(PERL) -ne '@t = map { $$_ unless $$_ eq "" } \
	                  ( split /\s+/o, $$_ ); \
	             print join("\n", @t),"\n";' | \
	  while read thyfile; \
	    do { \
	      if [ "$$thyfile" -a \( -e "$$thyfile" \) ]; \
	        then \
	          $(RM) -f $$thyfile ; \
	      fi ; \
	    } ; \
	  done ;
endef

mkclean    :
	@echo $(logfiles) $(tmpfiles) | $(saferm)

mkcleanaux :
	@echo $(preauxfiles) $(auxfiles) | $(saferm)

mkcleanall :
	@echo $(logfiles) $(tmpfiles) \
	      $(preauxfiles) $(auxfiles) | $(saferm)

mkcover    : $(BUILDS)/$(MAIN).bookcover.pdf

mkpress    : $(BUILDS)/$(MAIN).press.pdf

mkproof    : $(BUILDS)/$(MAIN).proof.pdf

mkdraft    : $(BUILDS)/$(MAIN).draft.pdf

mkpdf      : $(BUILDS)/$(MAIN).pdf

mkps       : $(BUILDS)/$(MAIN).s.ps.gz

mkpsdraft  : $(BUILDS)/$(MAIN).draft.s.ps.gz

mkfigs     : mkeps mkpapers mktexfigs
 
mkeps      : $(addsuffix .eps.gz, $(logos)  ) \
             $(addsuffix .eps.gz, $(posters)) \
             $(addsuffix .eps.gz, $(covers) ) \
             $(addsuffix .eps.gz, $(png)    )
                                # $(jpg)

mkpapers   : $(addsuffix .ps.gz, $(papers))

mktexfigs  : $(addsuffix .ps.gz,  $(texfigs)) \
             $(addsuffix .eps.gz, $(epsfigs))


### THESIS in PDF FORMAT

# Three perl scripts were introduced to fix few issues
# with latex auxiliary files for the main document.
# The first one just ensures that your name gets printed
# in boldface for all the bibliography entries in which it appear.
# The second one removes some extra whitespaces from the glossary file.
# The third one removes some extra whitespaces from the index file,
# so that, we get always unique entries (a problem when indexing items
# from the glossaaaries, for instance). After that, sorting is required.
define bblmarkup
	$(PERL) -npe 'if (/^\\bibitem\[/o) { \
	                  s/(et\~al)/\\textit\{$$1\}/o; \
	              } else { \
	                  s/(J\.\s*F\.[\s\~]*Abril)/\\textbf\{$$1\}/o; \
	              }'
endef
define glosscleanup
	$(PERL) -ne 's/(\\[^\\\s]+)\s+\{/$$1\{/og; \
	             print $$_,"\n";'
endef
define idxcleanup
	$(PERL) -ne 's/\s+/ /og; s/\s\{/\{/og; \
	             print $$_,"\n";'
endef
define pdflatexing
	mythesis=$(WORK)/$(MAIN); \
	intro=$(SECTIONS)/$(INTRO); \
	genomics=$(SECTIONS)/$(GENOMICS); \
	algorithms=$(SECTIONS)/$(ALGORITHMS); \
	genefinding=$(SECTIONS)/$(GENEFINDING); \
	meta=$(SECTIONS)/$(META); \
	mmeta=$(SECTIONS)/$(MMETA); \
	misc=$(SECTIONS)/$(MISC); \
	echo "### ...PDF-LaTeXing" ; \
	$(PDFLATEX) $$mythesis.tex; \
	echo "### ...BibTeXing chapters + PDF-LaTeXing" ; \
	$(BIBTEX) $$intro ; \
	$(BIBTEX) $$genomics ; \
	$(BIBTEX) $$algorithms ; \
	$(BIBTEX) $$genefinding ; \
	$(BIBTEX) $$meta ; \
	$(BIBTEX) $$mmeta ; \
	$(BIBTEX) $$misc ; \
	$(PDFLATEX) $$mythesis.tex; \
	echo "### ...Building Glossaries" ; \
	$(MKINDEX) -s $$mythesis.ist -t $$mythesis.glg \
	                             -o $$mythesis.gls $$mythesis.glo ; \
	$(MKINDEX) -s $$mythesis.ist -t $$mythesis.alg \
	                             -o $$mythesis.acn $$mythesis.act ; \
	$(MKINDEX) -s $$mythesis.ist -t $$mythesis.wlg \
	                             -o $$mythesis.wln $$mythesis.wlt ; \
	$(glosscleanup) $$mythesis.gls > $$mythesis.gls.tmp; \
	$(MV) $$mythesis.gls.tmp $$mythesis.gls; \
	$(glosscleanup) $$mythesis.wln > $$mythesis.wln.tmp; \
	$(MV) $$mythesis.wln.tmp $$mythesis.wln; \
	$(PDFLATEX) $$mythesis.tex; \
	echo "### ...Building Index" ; \
	$(idxcleanup) $$mythesis.idx | sort > $$mythesis.idx.tmp; \
	$(MV) $$mythesis.idx.tmp $$mythesis.idx; \
	$(MKINDEX) -s $(HEADERIST) $$mythesis.idx; \
	$(PDFLATEX) $$mythesis.tex; \
	$(idxcleanup) $$mythesis.idx | sort > $$mythesis.idx.tmp; \
	$(MV) $$mythesis.idx.tmp $$mythesis.idx; \
	$(MKINDEX) -s $(HEADERIST) $$mythesis.idx; \
	$(PDFLATEX) $$mythesis.tex; \
	$(PDFLATEX) $$mythesis.tex; \
	echo "### ...Building Thumbnails" ; \
	$(THUMBPDF) $$mythesis; \
	$(PDFLATEX) $$mythesis.tex; \
	echo "### ...PDF-LaTeXing (second round check)" ; \
	if [ `egrep -c undefined $$mythesis.log` -gt 0 ]; \
		then \
			echo "### ...BibTeXing chapters + PDF-LaTeXing" ; \
			$(BIBTEX) $$intro ; \
			$(BIBTEX) $$genomics; \
			$(BIBTEX) $$algorithms; \
			$(BIBTEX) $$genefinding ; \
			$(BIBTEX) $$meta ; \
			$(BIBTEX) $$mmeta ; \
			$(BIBTEX) $$misc ; \
			$(PDFLATEX) $$mythesis.tex; \
		fi; \
	if [ `egrep -c Rerun $$mythesis.log` -gt 0 ]; \
		then \
			echo "### ...PDF-LaTeXing (when Rerun found)" ; \
			$(PDFLATEX) $$mythesis; \
		fi; \
	$(MV) $$mythesis.pdf $(@);
endef

  PDFDEPS = $(WORK)/$(MAIN).tex $(WORK)/Makefile $(HEADER_IDX) \
            $(addprefix $(CONF)/, preamble.tex             ) \
            $(wildcard $(addprefix $(CONF)/,     *.sty    )) \
            $(wildcard $(addprefix $(SECTIONS)/, *.bib    )) \
            $(wildcard $(addprefix $(SECTIONS)/, *.tex    )) \
            $(wildcard $(addprefix $(PSDIR)/,    *.jpg    )) \
            $(wildcard $(addprefix $(PSDIR)/,    *.png    )) \
            $(wildcard $(addprefix $(PSDIR)/,    *.ps.gz  )) \
            $(wildcard $(addprefix $(PSDIR)/,    *.eps.gz )) \
            $(wildcard $(addprefix $(FIGURES)/,  *.ps.gz  )) \
            $(wildcard $(addprefix $(FIGURES)/,  *.eps.gz )) \
            $(wildcard $(addprefix $(FIGURES)/,  *.pdf    )) \
            $(wildcard $(addprefix $(TABLES)/,   *.ps.gz  )) \
            $(wildcard $(addprefix $(TABLES)/,   *.eps.gz )) \
            $(wildcard $(addprefix $(TABLES)/,   *.pdf    )) \
            $(wildcard $(addprefix $(PAPERS)/,   *.jpg    )) \
            $(wildcard $(addprefix $(PAPERS)/,   *.pdf    ))
#           $(auxfiles)

$(BUILDS)/$(MAIN).draft.pdf : $(PDFDEPS) $(CONF)/formatting_pdfdraft.tex
	@echo "### RUNNING PDFLATEX on $(@) (DRAFT VERSION)..." ;
	@pushd $(CONF) ; \
	 $(LN) -f ./formatting_pdfdraft.tex ./formatting.tex ; popd ;
	@$(pdflatexing)

$(BUILDS)/$(MAIN).proof.pdf : $(PDFDEPS) $(CONF)/formatting_proof.tex
	@echo "### RUNNING PDFLATEX on $(@) (PRESS PROOF VERSION)..." ;
	@pushd $(CONF) ; \
	 $(LN) -f ./formatting_proof.tex ./formatting.tex ; popd ;
	@$(pdflatexing)

$(BUILDS)/$(MAIN).press.pdf : $(PDFDEPS) $(CONF)/formatting_press.tex
	@echo "### RUNNING PDFLATEX on $(@) (PRESS FINAL VERSION)..." ;
	@pushd $(CONF) ; \
	 $(LN) -f ./formatting_press.tex ./formatting.tex ; popd ;
	@$(pdflatexing)

$(BUILDS)/$(MAIN).pdf : $(PDFDEPS) $(CONF)/formatting_pdf.tex
	@echo "### RUNNING PDFLATEX on $(@) (PDF FINAL VERSION)..." ;
	@pushd $(CONF) ; \
	 $(LN) -f ./formatting_pdf.tex ./formatting.tex ; popd ;
	@$(pdflatexing)

#	for dir in $(DIRS); do { \
#		cd $$dir; \
#		$(MAKE); \
#                cd ..; \
#	} done


### MAKING BOOK COVER

$(BUILDS)/$(MAIN).bookcover.pdf : $(WORK)/$(COVER).tex                      \
                                  $(addprefix $(CONF)/, preamble.tex      ) \
                                  $(wildcard $(addprefix $(CONF)/, *.sty )) \
                                  $(addprefix $(SECTIONS)/, abstract.tex  \
                                                            bookcover.tex \
                                                            bookback.tex  )
	@echo "### RUNNING PDFLATEX on $(@) (PRESS BOOK COVER)..." ; \
	 thycover=$(<:.tex=) ; \
	 $(PDFLATEX) $$thycover.tex; \
	 $(THUMBPDF) $$thycover; \
	 $(PDFLATEX) $$thycover.tex; \
	 $(MV) $$thycover.pdf $(@);


### THESIS in PS FORMAT

define pslatexing
	mythesis=$(WORK)/$(MAIN); \
	echo "### ...LaTeXing" ; \
	$(LATEX) $$mythesis ; \
	if [ `egrep -c undefined $$mythesis.log` -gt 0 ]; \
		then \
			echo "### ...BibTeXing + LaTeXing" ; \
			$(BIBTEX) $$mythesis ; \
			$(bblmarkup) $$mythesis.bbl > $$mythesis.bbl.tmp; \
			$(MV) $$mythesis.bbl.tmp $$mythesis.bbl; \
			$(LATEX)  $$mythesis ; \
		fi ; \
	$(MKINDEX) -s $$mythesis.ist -t $$mythesis.glg \
	                             -o $$mythesis.gls $$mythesis.glo ; \
	$(MKINDEX) -s $$mythesis.ist -t $$mythesis.alg \
	                             -o $$mythesis.acn $$mythesis.act ; \
	$(MKINDEX) -s $$mythesis.ist -t $$mythesis.wlg \
	                             -o $$mythesis.wln $$mythesis.wlt ; \
	$(LATEX) $$mythesis; \
	$(idxcleanup) $$mythesis.idx | sort > $$mythesis.idx.tmp; \
	$(MKINDEX) -s $(HEADER_IDX) $$mythesis.idx; \
	$(LATEX) $$mythesis; \
	$(idxcleanup) $$mythesis.idx | sort > $$mythesis.idx.tmp; \
	$(MKINDEX) -s $(HEADER_IDX) $$mythesis.idx; \
	$(LATEX) $$mythesis; \
	if [ `egrep -c Rerun $$mythesis.log` -gt 0 ]; \
		then \
			echo "### ...LaTeXing (when Rerun found)" ; \
			$(LATEX) $$mythesis ; \
		fi ; \
	$(DVIPS) $$mythesis.dvi -o $$mythesis.ps ; \
	$(MV) $$mythesis.ps $(@) ;
endef

  PSDEPS = $(WORK)/$(MAIN).tex $(WORK)/Makefile $(HEADER_IDX) \
           $(addprefix $(CONF)/, preamble.tex             ) \
           $(wildcard $(addprefix $(CONF)/,     *.sty    )) \
           $(wildcard $(addprefix $(SECTIONS)/, *.bib    )) \
           $(wildcard $(addprefix $(SECTIONS)/, *.tex    )) \
           $(wildcard $(addprefix $(PSDIR)/,    *.ps.gz  )) \
           $(wildcard $(addprefix $(PSDIR)/,    *.eps.gz )) \
           $(wildcard $(addprefix $(FIGURES)/,  *.ps.gz  )) \
           $(wildcard $(addprefix $(FIGURES)/,  *.eps.gz )) \
           $(wildcard $(addprefix $(TABLES)/,   *.ps.gz  )) \
           $(wildcard $(addprefix $(TABLES)/,   *.eps.gz )) \
           $(wildcard $(addprefix $(PAPERS)/,   *.ps.gz  )) \
           $(wildcard $(addprefix $(PAPERS)/,   *.eps.gz ))
#          $(auxfiles)

$(BUILDS)/$(MAIN).draft.ps : $(PSDEPS) $(CONF)/formatting_psdraft.tex
	@echo "### RUNNING LATEX on $(@) (PS DRAFT VERSION)..." ; \
	 pushd $(CONF) ; \
	 $(LN) -f ./formatting_psdraft.tex ./formatting.tex ; popd ;
	@$(pslatexing)

$(BUILDS)/$(MAIN).ps : $(PSDEPS) $(CONF)/formatting_ps.tex
	@echo "### RUNNING LATEX on $(@) (PS FINAL VERSION)..." ; \
	 pushd $(CONF) ; \
	 $(LN) -f ./formatting_ps.tex ./formatting.tex ; popd ;
	@$(pslatexing)

$(addprefix $(BUILDS)/, %.s.ps) : $(addprefix $(BUILDS)/, %.ps)
	@echo "### Running PSNUP on \"$(<)\" -> \"$(@)\"" ; \
	 pushd $(@D) ; pwd ; \
	 psfile=$(<F:.ps=); \
	 $(PSNUP) $$psfile.ps $$psfile.s.ps ; \
	 popd ;

$(addprefix $(BUILDS)/, %.ps.gz) : $(addprefix $(BUILDS)/, %.ps)
	@echo "### Running GZIP on \"$(<)\" -> \"$(@)\"" ; \
	 pushd $(@D) ; pwd ; \
	 $(GZIP) $(<F) ; \
	 popd ;


### LaTeXing functions

define whole_latexing
	echo "### LaTeXing on \"$(<)\" -> \"$(@)\"" ; \
	pushd $(DOCS); pwd; \
	texfile=$(<F); \
	logfile=$(<F:.tex=.log); \
	bibfile=$(<F:.tex=); \
	echo "### ...LaTeXing" ; \
	$(LATEX) $$texfile ; \
	if [ "`grep undefined $$logfile`" != "" ]; \
	  then \
	    echo "### ...BibTeXing + LaTeXing" ; \
	    $(BIBTEX) $$bibfile ; \
	    $(LATEX)  $$texfile ; \
	  fi ; \
	if [ "`grep Rerun $$logfile`" != "" ]; \
	  then \
	    echo "### ...LaTeXing (when Rerun found)" ; \
	    $(LATEX) $$texfile ; \
	  fi ; \
	popd ;
endef

### LaTeXing figures and tables

define latexing
	echo "### LaTeXing on \"$(<)\" -> \"$(@)\"" ; \
	pushd $(dir $(<)) ; pwd ; \
	texfile=$(notdir $(<:.tex=)) ; \
	echo "### ...LaTeXing" ; \
	$(LATEX) $$texfile ; \
	if [ `egrep -c Rerun $$texfile.log` -gt 0 ]; \
		then \
			echo "### ...LaTeXing (when Rerun found)" ; \
			$(LATEX) $$texfile ; \
		fi ; \
	popd ;
endef
	# if [ `egrep -c undefined $$texfile.log` -gt 0 ]; \
	#   then \
	#     echo "### ...BibTeXing + LaTeXing" ; \
	#     $(BIBTEX) $$texfile ; \
	#     $(LATEX)  $$texfile ; \
	#   fi ; \

$(addprefix $(FIGURES)/, %.dvi) : $(addprefix $(FIGURES)/, %.tex)
	@$(latexing)
$(addprefix $(TABLES)/,  %.dvi) : $(addprefix $(TABLES)/,  %.tex)
	@$(latexing)

### Making PostScript files for figures and tables

define dvips
	echo "### Running DVIPS on \"$<\" -> \"$@\"" ; \
	pushd $(dir $(<)) ; pwd ; \
	dvifile=$(notdir $(<:.dvi=)) ; \
	$(DVIPS) $$dvifile.dvi -o $$dvifile.ps ; \
	popd ;   # -Z # -E -O 0cm,0cm -T 21cm,29.7cm
endef

$(addprefix $(FIGURES)/, %.ps) : $(addprefix $(FIGURES)/, %.dvi)
	@$(dvips)
$(addprefix $(TABLES)/,  %.ps) : $(addprefix $(TABLES)/,  %.dvi)
	@$(dvips)

### Compressing PS figures and tables

define gzip_ps
	echo "### Running GZIP on \"$<\" -> \"$@\"" ; \
	pushd $(dir $(<)) ; pwd ; \
	psfile=$(notdir $(<:.ps=)) ; \
	egrep '^%%BoundingBox:' $$psfile.ps | head -1 > $$psfile.ps.bb; \
	epstopdf --outfile=$$psfile.pdf $$psfile.ps; \
	$(GZIP) $$psfile.ps; \
	popd ;
endef
define gzip_eps
	echo "### Running GZIP on \"$<\" -> \"$@\"" ; \
	pushd $(dir $(<)) ; pwd ; \
	psfile=$(notdir $(<:.eps=)) ; \
	egrep '^%%BoundingBox:' $$psfile.eps | head -1 > $$psfile.ps.bb; \
	epstopdf --outfile=$$psfile.pdf $$psfile.eps; \
	$(GZIP) $$psfile.eps; \
	popd ;
endef
#	echo "### ...updating $$psfile.ps.gz on $(PSDIR)" ; \
#	$(CPIF) $$psfile.ps.gz $(PSDIR)/ ; \

$(addprefix $(FIGURES)/, %.ps.gz)  : $(addprefix $(FIGURES)/, %.ps)
	@$(gzip_ps)
$(addprefix $(FIGURES)/, %.eps.gz) : $(addprefix $(FIGURES)/, %.eps)
	@$(gzip_eps)

$(addprefix $(TABLES)/,  %.ps.gz)  : $(addprefix $(TABLES)/,  %.ps)
	@$(gzip_ps)
$(addprefix $(TABLES)/,  %.eps.gz) : $(addprefix $(TABLES)/,  %.eps)
	@$(gzip_eps)

$(addprefix $(PSDIR)/,  %.ps.gz)  : $(addprefix $(PSDIR)/,  %.ps)
	@$(gzip_ps)
$(addprefix $(PSDIR)/,  %.eps.gz) : $(addprefix $(PSDIR)/,  %.eps)
	@$(gzip_eps)

### Converting JPGs to EPSs for the PS version 

define convert_jpg
	echo "### Converting \"$<\" -> \"$@\"" ; \
	filename=$(<:.jpg=); \
	convert -verbose $$filename.jpg $$filename.eps; \
	egrep '^%%BoundingBox:' $$filename.eps | head -1 > $$filename.eps.bb; \
	$(GZIP) $$filename.eps;
endef
# $(addprefix $(PSDIR)/, %.eps.gz) : $(addprefix $(PSDIR)/, %.eps)
# 	@echo "### Compressing \"$<\" -> \"$@\"" ; \
# 	 $(GZIP) $<;

$(addprefix $(PAPERS)/, %.eps.gz) : $(addprefix $(PAPERS)/, %.jpg)
	@$(convert_jpg)
$(addprefix $(PSDIR)/, %.eps.gz) : $(addprefix $(PSDIR)/, %.jpg)
	@$(convert_jpg)

### Converting PNGs to EPSs for the PS version 

define convert_png
	echo "### Converting \"$<\" -> \"$@\"" ; \
	filename=$(<:.png=); \
	convert -verbose $$filename.png $$filename.eps; \
	egrep '^%%BoundingBox:' $$filename.eps | head -1 > $$filename.eps.bb; \
	$(GZIP) $$filename.eps;
endef

$(addprefix $(PAPERS)/, %.eps.gz) : $(addprefix $(PAPERS)/, %.png)
	@$(convert_png)
$(addprefix $(PSDIR)/, %.eps.gz) : $(addprefix $(PSDIR)/, %.png)
	@$(convert_png)

### Retrieving the first page from PDFs into PS

define convert_pdf
	echo "### Converting \"$<\" -> \"$@\"" ; \
	filename=$(<:.pdf=); \
	pdftops -f 1 -l 1 -level2 -nocrop -noshrink $$filename.pdf; \
	egrep '^%%BoundingBox:' $$filename.ps | head -1 > $$filename.ps.bb; \
	$(GZIP) $$filename.ps
endef
#	gs -dNOPAUSE -dBATCH -dSAFER -sDEVICE=pswrite \
#	   -dFirstPage=1 -dLastPage=1 -sOutputFile=$$filename.ps $$filename.pdf; \
# NOTE: ----------------------------------------------------------------------
#	pdftops -f 1 -l 1 -level2 -nocrop -noshrink $$filename.pdf; \
# WARNING: pdftops comes with xpdf program, it converts PDF into PS
#         aparently better than ghostscript, but it depends on several
#         libraries and won't compile OK without GCC >= 3.0 (Lesstif libs)
# The above command substitutes the following one (antialias switches not used):
#	 gs -dNOPAUSE -dBATCH -dSAFER -sDEVICE=pswrite \
#	   -dTextAlphaBits=4 -dGraphicsAlphaBits=2 \
#	   -dFirstPage=1 -dLastPage=1 -sOutputFile=$$filename.ps $$filename.pdf; \
# ----------------------------------------------------------------------------

$(addprefix $(PAPERS)/, %.ps.gz) : $(addprefix $(PAPERS)/, %.pdf)
	@$(convert_pdf)

### INFO RULES

info : header getinfo short_trailer

getinfo :
	@echo "### BASH ###  $(BASH)  ###  $(BASHV)";
	@echo "### GAWK ###  $(GAWK)  ###  $(GAWKV)";
	@echo "### PERL ###  $(PERL)  ###  $(PERLV)";

header :
	@echo "###";
	@echo "### RUNNING MAKEFILE";
	@echo "###";
	@echo "### $(DATE) -- $(USER)";
	@echo "###";
	@date +'%s' > $(WORK)/.seconds;
	@echo "$(TEXINPUTS)"

short_trailer :
	@echo "###";
	@echo "### MAKEFILE DONE...";
	@echo "###";

trailer :
	@echo "###"; \
	 logs=$(WORK)/$(MAIN).log; \
	 if [ -e "$$logs" ]; \
	  then \
	   if [ `egrep -c '[Ww]arning: |[Ee]rror' $$logs` -gt 0 ]; \
		then \
		  echo "#==========================================================="; \
		  echo "###   WARNINGS --- Please Check for FINAL Versions..."; \
		  echo "#==========================================================="; \
		  echo "###"; \
		  egrep '\.tex|[Ww]arning:|[Ee]rror' $$logs; \
		  echo "###"; \
		  echo "#==========================================================="; \
	    fi; \
	  fi; \
	 SECONDS=`gawk '{ printf $$1 }' $(WORK)/.seconds`; \
	 NEWSECS=`date +'%s'`; \
	 TOTSECS=`expr $$NEWSECS - $$SECONDS`; \
	 echo "###"; \
	 echo "### This compilation took $$NEWSECS - $$SECONDS = $$TOTSECS seconds."; \
	 echo "###"; \
	 echo "### MAKEFILE DONE..."; \
	 echo "###";

################################################################################
#        1         2         3         4         5         6         7         8
#2345678901234567890123456789012345678901234567890123456789012345678901234567890
################################################################################

##################################### EOF ######################################
