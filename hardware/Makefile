PROJ=10004_epic_cape
REV=1.1.1

.PHONY : eagle fab all tidy tidyart tidyall cleanart cleanplace cleanzip cleandirs cleanup clean

all: eagle fab

eagle:
	zip -r	${PROJ}_${REV}.zip \
		${PROJ}.sch \
		${PROJ}.brd \
		${PROJ}.pdf \
		${PROJ}.csv \
		${PROJ}.xlsx \
		Makefile \
		README_PCB.txt \
		LICENSE.txt \

fab:
	zip	${PROJ}_${REV}_fab.zip \
		*.art \
		${PROJ}.mnt \
		${PROJ}.mnb \
		${PROJ}.csv \
		${PROJ}.xlsx \
		NCDRILL.txt \
		${PROJ}.pdf \
		${PROJ}_photoplots.pdf \
		README_PCB.txt \
		LICENSE.txt \

tidy:
	rm -vf	*~ \
		*.*#* \
		Transcode\ Report.txt \

tidyart:
	rm -vf	*.gpi \
		*.dri \

tidyall: tidy tidyart

cleansch:
	rm -vf ${PROJ}.pdf

cleanbom:
	rm -vf	${PROJ}.csv \
		*${PROJ}.xlsx \

cleanart:
	rm -vf	*.art \
		*.gpi \
		${PROJ}_photoplots.pdf \
		NCDRILL.* \

cleanplace:
	rm -vf	*.mnt \
		*.mnb \

cleanzip:
	rm -vf	${PROJ}_${REV}_fab.zip \
		${PROJ}_${REV}.zip \

cleandirs:
	rm -rvf	${PROJ}_${REV}_fab \
		${PROJ}_${REV} \

cleanup: tidyall cleandirs

clean: tidyall cleansch cleanbom cleanart cleanplace cleandirs
