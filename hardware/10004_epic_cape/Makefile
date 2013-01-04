PROJ=10004_epic_cape
REV=1.1.1
RELEASE_DIR=../release

.PHONY : eagle fab all tidy tidyart tidyall cleanart cleanplace cleanzip cleandirs cleanup clean

all: eagle fab batchpcb

eagle:
	mkdir -p $(RELEASE_DIR)
	zip $(RELEASE_DIR)/$(PROJ)_$(REV).zip \
		$(PROJ).sch \
		$(PROJ).brd \
		$(PROJ).pdf \
		$(PROJ).csv \
		$(PROJ).xlsx \
		Makefile \
		README.txt \
		README_PCB.txt \
		LICENSE.txt \

fab:
	mkdir -p $(RELEASE_DIR)
	zip	$(RELEASE_DIR)/$(PROJ)_$(REV)_fab.zip \
		*.art \
		$(PROJ).mnt \
		$(PROJ).mnb \
		$(PROJ).csv \
		$(PROJ).xlsx \
		NCDRILL.txt \
		$(PROJ).pdf \
		$(PROJ)_photoplots.pdf \
		README_PCB.txt \
		LICENSE.txt \
		viewmaster_colors.txt \

batchpcb:
	mkdir -p $(RELEASE_DIR)
	zip	$(RELEASE_DIR)/$(PROJ)_$(REV)_batchpcb.zip \
		OUTLINE.art \
		L1_TOP.art \
		L2_GND.art \
		L3_PWR.art \
		L4_BOT.art \
		PASTE_TOP.art \
		PASTE_BOT.art \
		SILKSCREEN_TOP.art \
		SILKSCREEN_BOT.art \
		SOLDERMASK_TOP.art \
		SOLDERMASK_BOT.art \
		NCDRILL.txt \

clean: tidyall cleandirs

cleanall: cleanup cleanzip

cleanup: tidyall cleansch cleanbom cleanart cleanplace cleandirs

tidyall: tidy tidyart

tidy:
	rm -vf *~ \
		*.*#* \
		Transcode\ Report.txt \

tidyart:
	rm -vf *.gpi \
		*.dri \

cleansch:
	rm -vf $(PROJ).pdf

cleanbom:
	rm -vf $(PROJ).csv \
		*$(PROJ).xlsx \

cleanart: tidyart
	rm -vf *.art \
		$(PROJ)_photoplots.pdf \
		NCDRILL.* \

cleanplace:
	rm -vf *.mnt \
		*.mnb \

cleanzip:
	rm -vf $(RELEASE_DIR)/$(PROJ)_$(REV).zip \
		$(RELEASE_DIR)/$(PROJ)_$(REV)_fab.zip \
		$(RELEASE_DIR)/$(PROJ)_$(REV)_batchpcb.zip \

cleandirs:
	rm -rvf $(RELEASE_DIR)/$(PROJ)_$(REV) \
		$(RELEASE_DIR)/$(PROJ)_$(REV)_fab \
		$(RELEASE_DIR)/$(PROJ)_$(REV)_batchpcb \
