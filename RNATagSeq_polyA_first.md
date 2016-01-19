# RNATagSeq_polyA_first


@(RNATagSeq)[TagSeq, Protocol, Slack]

**VERSION Tuesday, January 19, 2016**

***This protocol reflects the notes in the protocol LK and AL were trouble-shooting.***

This protocol is for RNA sequencing (RNASeq) library preparation using the RNATagSeq method of Shishkin, et al. (2015). Simultaneous generation of many RNA-seq libraries in a single reaction. Nature Methods, 12(4), 323–325. http://doi.org/10.1038/nmeth.3313 (Broad institute).

This document is adapted from the Drummond lab: http://drummondlab.org/protocols/protocol/rnatagseq-library-prep/

The signifocant modification here is using polyA purification instead of RiboZero. This means that the order of the protocol needs to be changed, mainly by bringing the polyA module to step 2. This also means that we start with 5ug total RNA, which is the max going into the polyA kit. 

Furthermore, the movement of the PolyA module to the front of the protocol changes the amounts of reagents and samples from the original Shishkin protocol.


**(Notes)**
--

- This is not a protocol where you can cut corners. To save time and anguish, plan thoroughly, work cleanly, QC your samples and intermediate steps.
- Label everything and lay out tubes neurotically to avoid pipette error.
- Observe RNase-free sample prep, for steps 1-8, also neurotically. Clean your workspace and pipettes with 50% Ethanol and RNAse-Zap, use reserved RNase-free pipettes and RNAse-free (non-autoclaved) tips, ensure all tubes and reagents (including water) are RNase-free.
- Avoid DNA contamination, especially from other sequencing libraries for steps 8+. Use filter tips for PCR reactions.
- Points where the in-process libraries may be frozen at -80 C while you pause, are indicated as PAUSE POINT. Don’t take the risk of pausing elsewhere.
- SPRI/XP beads take a bit of skill. “2x SPRI” refers to the ratio of beads to aqueous solution containing nucleic acids (NA); this ratio controls the size of NA retained (see http://core-genomics.blogspot.com/2012/04/how-do-spri-beads-work.html). Be patient; wait for binding and for magnetisation. 
   - Prepare fresh 80% ethanol solution every day or two; the concentration drifts over time due to evaporation (manufacturer recommends 70% EtOH). Some reactions (2nd ligation, step 11) happen on-bead so change the elution step. Manufacturer’s protocol with tweaks is below; practice SPRI extraction on a DNA ladder or RNA ladder and ensure full recovery.
   - Add appropriate ratio of beads to sample in PCR tube, pipette up and down 10x gently.
   - Incubate beads and sample at room temperature for 15min to bind.
   - Place on 96R plate magnet for 5min, until solution is clear
   - Pipette out and discard clear solution (save this for troubleshooting)
   - Wash: Add 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette off clear solution.
   - Repeat 80% EtOH wash, use additional 10uL pipette to remove residual EtOH if necessary.
   - Let air dry for 2min. Apparently, drying too short is bad because residual ethanol interferes with downstream reactions, and too long is bad because beads may crack and/or bind hydrophobically, overly strongly, to your NA.
   - Elute: remove from magnet, pipette 40uL water or low TE buffer onto beads, pipette up and down 10X, replace on magnet and wait 5min (this is easiest with at least 40uL, hellish with 10uL).
   - Unless otherwise specified, take clear liquid to new tube, carefully not disturbing beads.
- Barcoded adaptors are listed in appendix, requiring 5’ Phosphate group (/5Phos/) and 3’ blocking spacer (/3SpC3/). The combination to use should be chosen carefully: plan a spreadsheet listing the sample name, conditions, and which RNAtag adaptor (step 3) and P7 adaptor (step 14/17, PCR after pooling) will be used. In each set of sequencing libraries combined on an Illumina sequencing run, there must be at least 3 distinct nt in all of the initial 4 nt of the sequenced adaptor for the sequencing machine to recognize clusters properly. (e.g. ATTA, GCAC, CAGT work, ATTA, GTAC, CTGT don’t due to the common T.)



##Protocol Overview
## DAY 0
#### Step 0. RNA extraction: ~3 hours for 8 samples

## Day 1

#### Step 1. Check RNA quality : 1 hour
You should start the protocol with approximately 5-10 (10 is better if you can) ug total RNA per sample. Make sure the RNA is of high quality. ![pic](http://i.imgur.com/srDKeKE.jpg)


&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;


#### Step 2. polyA pulldown : 1 hour + 30 min QC
Should have between ~25-50ng of RNA left (0.5% - 1% of input). A 1% return is the maximum yield retrieved by the kit (according to the manufacturer).
 ![polyA](http://i.imgur.com/qZ8MEq3.jpg)
#### Step 3. Fragment RNA : 5 minutes
#### Step 4. Digest DNA and repair RNA : 15 min prep + 30 min INC

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

#### Step 5. Cleanup : 1 hour + 30 min QC
This is an important QC point. You should have  > 2000 pg/uL (per Tapestation) and a Tapestation trace like this:

![post-fragmentation](http://i.imgur.com/HMWpzKy.jpg)


## Day 2

#### Step 6. Ligate 3’ barcoded Adaptor : 40 min prep + 1 1/2 hour INC
#### Step 7. Pool barcoded RNA with Zymo : 45 min + 30 min QC
QC Step: You should have x ng/uL (per Qubit) and a Tapestation trace like this.


WE NEED TO PUT A NEW TRACE HERE

#### Step 8. First Strand cDNA : 10 min
#### Step 9. Second Strand cDNA (reverse transcription step):15 min prep + 55 min Inc
#### Step 10. Degrade RNA : 20 min
#### Step 11. Cleanup : 40 min
#### Step 12. Ligate 3’ Universal Adaptor (overnight ligation): 20 min prep + OVERNIGHT

## Day 3

#### Step 13. Cleanup : 1 hour 45 minutes
#### Step 14. Test PCR : 20 min prep + 1 hour INC
#### Step 15. Cleanup : 45 min + 30 min QC
QC Step: You should have X ng/uL and a Tapestation trace like this.

WE NEED TO PUT A NEW TRACE HERE

#### Step 16. Real PCR : 20 min prep + 1 hour INC
#### Step 17. Cleanup : 45 min
#### Step 18. Final Cleanup : 45 min
#### Step 19. DNA Tapestation : 30 min QC
QC Step: You should have X ng/uL and a Tapestation trace like this.

WE NEED TO PUT A NEW TRACE HERE





&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;


## MAIN PROTOCOL

#### 0) EXTRACT RNA : 8 samples : 3 hours

#### 1) Check RNA quality by running on the Agilent Bioanalyzer: 1 hour

- Place 5-10ug (10 if possible) of total RNA in a tube.
- Increase the volume to 50uL with Nuclease free water
- Add 2 uL of SUPERase-IN (20U/uL) IF NOT Continuing on to POLY A THE SAME DAY (Final total volume = 52uL (100ng/uL)
- Put samples on ice
- Continue to next step or freeze at -80C until ready to process samples

**PAUSE POINT**


#### 2) Deplete ribosomal RNA with polyA kit : 1 hour + 30 min QC

-MAKE SURE TO WASH BEADS BEFORE USE!!!!

**WASH BEADS**

- Aliquot 20 μl of NEBNext Magnetic Oligo d(T)25 Beads into nuclease-free 0.2 ml PCR tube.
- Place beads/buffer on magnet for 2 minutes and discard storage buffer (supernatant).
- Wash the beads two times with 100 μl of RNA Binding Buffer and remove the supernatant.
- Resuspend the beads in 50 μl of RNA Binding Buffer

**First mRNA Purification**

- To the washed beads, add the 50 μl of total RNA sample diulted in H2O from step 8A (100ul total in tube).
- Place the tubes on the thermal cycler and heat the sample at 65°C for 5 minutes and hold at 4°C to denature the RNA and facilitate binding of the poly-A-RNA to the beads
- Remove tubes from the thermal cycler when the temperature reaches 4°C.
- Vortex and place the tubes on HULA MIXER and incubate at room temperature for 10 minutes to allow the RNA to bind to the beads.
- Place tubes on the magnetic rack at room temperature for 2 minutes to separate the poly-A RNA bound to the beads from the solution
- Remove and discard all of the supernatant. Take care not to disturb the beads
- Remove the tubes from the magnetic rack
- Wash the beads twice with 200 μl of Wash Buffer to remove unbound RNA. Pipette the entire volume up and down 6 times to mix thoroughly.
- Place the tubes on the magnetic rack at room temperature for 2 minutes.
- Remove and discard all the supernatant from each of the tubes. Take care not to disturb the beads.
- Remove the tubes from the magnetic rack.
- Spin down sample so beads/RNA collect at the bottom of the tube.
- Add 50 μl of Tris buffer to each of the tubes. Gently pipette the entire volume up and down 6 times to mix thoroughly.
- Place the tubes on the thermal cycler. Close the lid and heat the sample at 80°C for 2 minutes, then hold at 25°C to elute the poly-A RNA from the beads
- Remove the tubes from the thermal cycler when the temperature reaches 25°C

**Second mRNA Purification**

- Add 50 μl of RNA binding buffer to each sample to allow the RNA to bind to the beads. Gently pipette the entire volume up and down 6 times to mix thoroughly.
- Vortex and place the tubes on HULA MIXER and incubate at room temperature for 10 minutes to allow the RNA to bind to the beads.
- Place the tubes on the magnetic stand at room temperature for 2 minutes.
- Remove and discard all of the supernatant from each tube. Take care not to disturb the beads.
- Remove the tubes from the magnetic stand.
- Wash the beads ONCE with 200 μl of Wash Buffer. Gently pipette the entire volume up and down 6 times to mix thoroughly.
- Place tube on magnetic rack for 2 minutes.
- Remove and discard all of the supernatant from each tube. Take care not to disturb the beads.
- Remove the tubes from the magnetic stand.
- Spin down so beads/RNA collect at the bottom of the tube.
- Remove the mRNA from the beads by adding 35 µl of the Tris Buffer and incubating the sample at 80°C for 2 minutes. (NOTE this is a different elution amount than listed in the product manufacturers' protocol)
- Immediately, place the tubes on the magnetic rack
- Collect the purified mRNA by transferring the supernatant to a clean nuclease-free PCR Tube
- QC: Take 2uL for tapestation (RNA High Sensitivity). 

**MUST CONTINUE**

#### 3) Fragment RNA using 2x FastAP buffer : 5 min

  - Add 8 uL of 10X FastAP buffer to 32 uL RNA from step 1 and mix well.
  - Incubate on preheated thermal cycler for 2 1/2 min at 92°C.
  - Place on ice.

**MUST CONTINUE**


#### 4) Digest DNA and repair RNA: Combination DNase/FastAP treatment : 15 min prep + 30 min INC

  - Make a DNase/FastAP master mix, 40uL per sample:

   | Reagent (for 2X FastAP master)	| Amount	| For 8rxn| 
   | ------------------------------ |-----------| ------ | 
   | nuclease-free water	| 10 uL	| 85 uL |
   | RNase Inhibitor, Murine (40U/uL)	| 2 uL	| 17 uL| 
   | TURBO DNase (2U/uL)	| 8 uL	| 68 uL| 
   | FastAP (1U/uL)	| 20 uL	| 170 uL| 
   | Total	| 40 uL	| 340 uL | 

  - Mix well
  - Aliquot 40 uL into each tube/well with the 40uL of fragmented RNA from step 3.
  - Mix well
  - Incubate on preheated thermal cycler for 30 min at 37°C
 
****AT THIS TIME, PUT ALL LIGATION REAGENTS AT ROOM TEMPERATURE ONLY IF PROCEEDING TO LIGATION TODAY

**MUST CONTINUE**

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

#### 5) Cleanup (2x SPRI) to remove enzymes and reaction buffer : 1 hour + 30 min QC

  - Add 2.0x reaction volume of Agencourt RNAClean XP beads (160 uL) and capture RNA on beads:
  - Incubate at room temperature, on HULA MIXER for 15min to bind RNA
  - Place on magnet for 5min, until solution is clear
  - Pipette out and discard clear solution
  - Add 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette out and discard supernatant.
  - Repeat 80% EtOH wash (discard supernatant).
  - Spin down beads to bottom of tubes.
  - Let air dry for 3min
  - Resuspend beads in 8 uL nuclease free water (using the whole sample - not trying to have any in reserve)
  - Place on magnet for 2 minutes, and elute sample from beads, KEEEP supernatant!



#### QC

  - QC: Save 2 uL from remaining RNA before addition of SUPERase-IN
  - Run on HSRNA Tapestation
  - Add 1uL SUPERase-IN (20U/uL) to the sample and store at -80°C if not proceeding to ligation. 

**PAUSE POINT**

#### 6A) Ligate 3’ barcoded Adaptor: First Ligation (ssRNA/ssDNA) : 10 minutes

  - Add 1 uL of barcoded RNATag adaptor (100 pmole = 1 uL of 100 uM) to 5 uL of dephosphorylated RNA
  - Heat at 70°C for 2 min, place in cold block on ice

#### 6B) Set up First Ligation master mix below NOTE: 30 minutes + 1 hour 30 min INC

  - All reagents except enzymes (-20°C ) should be stored at -80°C in single use aliquots and brought to room temp just before use
  - Make up mix at room temp so the reagents don’t start precipitating when combined (if DMSO is added directly into cold buffer it will precipitate)
  - Pipette very slowly for accurate aspiration of PEG (very viscous)

   | Reagent (for Ligation master)	| 1 rxn	| 10 rxns
   |-------------------------------| -------| ---------
   | 10× T4 RNA Ligase Buffer	| 2 uL	| 20 uL| 
   | DMSO (100%)	| 1.8 uL	| 18 uL| 
   | ATP (100 mM)	| 0.2 uL	| 2 uL| 
   | PEG 8000 (50%)	| 8 uL	| 80 uL| 
   | RNase inhibitor, Murine (40U/uL)	| 0.3 uL	| 3 uL 
   | T4 RNA Ligase 1 (30,000 U/mL)	| 1.8 uL	| 18 uL
   | Total	| 14.1 uL	| 141 uL| 

 - make up the MM without the enzyme with all the other reagents at room temperature, and then wait till the last possible minute to add the enzyme to the master mix, right before you use the MM.
  - Mix really well by extensive vortexing tube since the solution is very viscous, then spin down briefly in microfuge
  - Add 14.1 uL of ligation master mix to each tube/well containing 6 uL denatured RNA + adaptor (for a 20.1 uL total reaction volumne).
  - Mix well many times; mix by flicking since the solution is very viscous
  - Incubate at 22°C (room temp), on HULA MIXER, for 1 hour 30 minutes.



**MUST CONTINUE**


#### 7) Pool barcoded RNA:  RNAClean XP Beads

  - NOTE: At this point, multiple samples with distinct RNAtag adaptors will be pooled into a single tube (1.7 mL eppendorf tube)
  - Pool all 8 samples into a single tube (160 uL total for 8 samples)
  - Add 2.0x reaction volume of Agencourt RNAClean XP beads (320 uL) and capture RNA on beads:
  - Incubate at room temperature, on HULA MIXER for 15min to bind RNA
  - Place on magnet for 5min, until solution is clear
  - Pipette out and discard clear solution
  - Remove from magnet, add 200uL fresh 80% EtOH, and completely resuspend beads. 
  - Place on magnet for 3 minutes (or until solution is clear), pipette out and discard supernatant.
  - Add another 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette out and discard supernatant.
  - Spin down beads to bottom of tubes.
  - Let air dry for 3min
  - Resuspend beads in 28 uL nuclease free water (using the whole sample - not trying to have any in reserve)
  - Place on magnet for 2 minutes, and elute sample from beads, KEEEP supernatant!

#### QC

  - QC: Save 3 uL from remaining RNA before addition of SUPERase-IN
  - Run on HSRNA Tapestation and HS Qubit
 
**PAUSE POINT** 


#### 8) Synthesize First Strand cDNA : 10 minutes

  - Take 24 uL mRNA (use all the material from previous step) 
  - Add 4 uL (50 pmoles) of AR2 primer (25 uM) 5’-TAC ACG ACG CTC TTC CGA T-3’ 
  - Mix well
  - Heat the mixture to 70°C for 2 min and immediately place on cold block on ice

**MUST CONTINUE**
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

#### 9) Second Strand cDNA synthesis : 15 prep + 55 INC

  - Add in order on ice (the below volumes build in a little extra for pipetting errors)

   | Reagent (for RT master)	| 1 rxn	|  
   | --------------------------| -------|  
   | 10× AffinityScript RT Buffer	| 4.0 uL	
   | DTT (0.1M)	| 4.0 uL	| 
   | 25mM dNTP Mix (25mM each)	| 1.6 uL
   | RNase inhibitor, murine (40U/uL)	| 0.8 uL
   | AffinityScript RT Enzyme	| 1.6 u
   | Total	| 12.0 uL	|

  - Mix well
  - Add 12.0 uL of RT mix to the 28 uL rRNA depleted RNA + AR2 RTprimer on ice
  - Mix well and spin for 5 sec
  - Place in preheated (55 °C) incubator or thermocycler. Incubate at 55 °C for 55 minutes.

**MUST CONTINUE**


#### 10) Degrade RNA after reverse transcription : 20 minutes

  - NOTE: make fresh working stock solutions of NaOH and Acetic Acid
  - Add 10% reaction vol. of 1M NaOH (4 uL) to each reaction
  - Incubate at 70 °C for 12 minutes
  - Neutralize with 8 uL of 0.5M Acetic Acid; mix well
  - Total volume = 52 uL
  
**MUST CONTINUE**



#### 11) Cleanup reverse transcription (2x SPRI) to remove enzyme, primers, and reaction buffer : 40 minutes

**AT this time put Ligation reagents at ROOM TEMP**

  - Add 28 uL of sterile water for a final reaction volume of 80 uL
  - Transfer to new tubes (NaOH may start degrading tubes)
  - Add 2x reaction volume RNAClean XP beads (160uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min, remove from magnet.
  - Add 5 uL RNase/DNase free water to beads 
  – KEEP BEADS AND TUBES, do not transfer, do not pause

**MUST CONTINUE**


#### 12) Ligate 3’ Universal Adaptor: Second Ligation (ssDNA/ssDNA) with beads : 20 min prep + OVERNIGHT
  - NOTE: 3Tr3 adaptor: 5’-/5Phos/AGA TCG GAA GAG CAC ACG TCT G-/3SpC3/ 3’

  - Add 2 uL (80 pmoles) of 3Tr3 adaptor to cDNA
  - Heat at 75°C for 3 min; Place on cold block on ice
  - 2nd Ligation Master Mix (can be prepared ahead of time, at RT): Mix in order

   | Reagent (for Ligation 2 master)	| 1 rxn	
   | -----------------------------------| ------
   | 10× T4 RNA Ligase Buffer	| 2.0 uL
   | DMSO (100%)	| 0.8 uL
   | ATP (100 mM)	| 0.2 uL
   | PEG 8000 (50%)	| 8.5 uL
   | T4 RNA Ligase 1 (30,000U/mL)	| 1.5 uL
   | Total	| 13.0 uL
 
  - Mix really well by extensive vortexing tube since the solution is very viscous
  - Spin down briefly in microfuge
  - Swirl the 7uL cDNA/beads/water with pipet tip, THEN add 13 uL 2nd Ligation Master Mix.
  - Mix well by pipetting up and down 20x or cap tubes and flick several times; solution is viscous
  - Quick spin (low speed centrifuge, to get everything to bottom of tube)
  - Incubate overnight at 22 °C

**THIS IS NOT A LONG TERM STOPPING POINT, JUST AN OVERNIGHT INCUBATION**


**MUST CONTINUE**




#### 13) Cleanup (2x SPRI) to remove adaptors : 1 hour 45 min

  - Increase to 2x reaction volume with water (add 20 uL of water)
  - Add 2x reaction volume Agencourt RNAClean XP beads (80uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute DNA by adding 30 uL RNase/DNase free water, transfer to new tube.

**2nd Cleanup (1.5x SPRI) to remove the remaining adaptors**

  - Add 1.5x reaction volume Agencourt RNAClean XP beads (45 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min 
  - Elute DNA by adding 25 uL RNase/DNase free water, transfer to new tube.

**PAUSE POINT**

#### 14) Test PCR Amplification to determine final cycle number : 20 min prep + 1 hour inc
  - NOTE: P5 primer: P5_RNATag, 5’-AAT GAT ACG GCG ACC ACC GAG ATC TAC ACT CTT TCC CTA CAC GAC GCT CTT CCG ATC T-3’ 
  - NOTE: MacManes Lab has named P5 primer: P5_RNATag as "enrF"
  - Set up a test PCR using 5 uL of ss cDNA sample and 9-12 cycles of PCR 
  - Include a negative control (water) for each primer set
  - Make PCR Master Mix (make additional reaction volume for neg/pos control):

  - Add in order:
 

   | Reagent (for PCR master mix)	| 1 rxn	| 
   | -------------------------------| ---- |
   | Water, PCR-clean	| 15.4 uL	| 
   | 10X AccuPrime Buffer	| 2.5 uL	| 
   | enrF (P5_RNATag, 12.5 uM)	| 1 uL	| L
   | P7enr1 (P7 index primer, 12.5 uM) | 1uL | 
   | AccuPrime HiFi Taq | 0.1uL 
   | Total	| 20 uL	| 

  - Mix well
  - Aliquot 20 uL / sample into PCR tubes
  - Add 5 uL of cDNA, or water (for negative control)
  - Place each of the three PCR tubes at different cycling conditions (negative control was in 12 cycle) 
  



Place each in a thermal cycler with cycling conditions:

  - start: 98°C, 3min
  - cycle: 9, 12, 15 cycles (for test PCR) 98°C, 30sec; 55°C, 30sec; 65°C, 30sec
  - end: °65C, 2min; 4°C, hold



**MUST CONTINUE**


**Please note that the XP bead type is now changing from Agencourt RNAClean XP beads to AMPure XP beads for the remainder of the protocol**


#### 15) Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers: 45 min + 30 min QC

  - increase reaction to 40uL with sterile water
  - Add 1.5x reaction volume AMPpure XP beads (60 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 10 uL 1x low TE (10 mM Tris, 0.1M EDTA)
  - QC test PCR amplification on Tapestation (D1000 Tape)

  - **NOTE:** Based on test results change the cycle number, if necessary, and set up more reactions to provide enough material to send for sequencing. Library should have smooth profile 200-500nt long; visible single bands, or a “shoulder” of larger products, indicate PCR artefacts.


**PAUSE POINT**


#### 16) PCR for Sequencing library : 20  min prep + 1 hour INC

  - Choose the optimal PCR cycle # based on Bioanalyzer QC of test (step 15).
  - Include a negative control (water) for each primer set
  - Make PCR Master Mix (make additional reaction volume for neg/pos control):

  - Add in order:

test


   | Reagent (for PCR master mix)  | 1 rxn |
   | -------------------------------|
   | Water, PCR-clean	| 30.8 uL |
   | 10X AccuPrime PCR Buffer 1	| 5 uL |
   | enrF (12.5 uM)	| 2 uL |
   | p7enr1 (12.5 uM)	| 2 uL |
   | AccuPrime HiFi Taq (5U/uL)	| 0.2 uL |
   | Total	| 40 uL |

  - Mix well
  - Aliquot 40 uL / sample into PCR tubes
  - Add 10 uL of ss cDNA




Place each in a thermal cycler with the cycling conditions:

  - start: 98°C, 3min  
  - cycle: # determined from test PCR 98°C, 30sec; 55°C, 30sec; 65°C, 30sec
  - end: 65°C, 2min; 4°C, hold

**MUST CONTINUE**


#### 17) Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers: 45 minutes

  - Add 1.5x reaction volume AMPure beads (75 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 50 uL water and transfer to new tubes.
  

#### 18) Second Round Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers: 45 minutes

  - Add 0.8x reaction volume AMPure beads (40 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 25 uL 1x low TE (10 mM Tris, 0.1M EDTA)

#### 19) Check quantity/quality on Tapestation (D1000 Tape). 30 minutes


Reagents
---


- Turbo DNase; Ambion/Applied Biosystems, Cat.# AM2239
- FastAP Thermosensitive Alkaline Phosphatase; Thermo Scientific, Cat.# EF0651
- RLT buffer (RNeasy Lysis Buffer); Qiagen, Cat.# 79216 (220mL)
- T4 RNA Ligase 1; 30,000U/mL (0.5mL) Cat.# MO437M and comes with the following:
- ATP(100mM) (make 10uL aliquots and store at -80°C, always use fresh aliquot)
- PEG8000,50% in water
- DMSO (100%); Sigma, Cat.# D8418-50ML for Molecular Biology
- RNase Inhibitor, Murine (40U/uL); NEB, Cat.# M0314S (3,000 units)
- SUPERase-IN 20U/uL (Ambion; AM2694; 2500U)
- AffinityScript Multiple Temperature cDNA Synthesis Kit, 50 reaction; Agilent, Cat.# 200436. includes the
- dNTPs, 10x RT buffer, RNase Block Ribonuclease Inhibitor (40U/uL)
- 10X AffinityScript RT buffer; Agilent, Cat.# 600100-52
- RNA Clean & ConcentratorTM-5 columns; Zymo Research, Cat. #R1015 (50 preps)
- SPRI beads:
- RNAClean XP beads; Agencourt/Beckman, Cat.# A63987 (40mL); (mix well, make 1.5mL and 0.5mL aliquots, store at 4 °C)
    - For steps after cDNA synthesis, can use non-RNA certified, AMPure XP beads Cat.# A63881.

- Sodium hydroxide solution (5M); Sigma-Aldrich, Cat.# 656046
- Glacial acetic acid (17.4M); Sigma-Aldrich, Cat.# ARK2183
- Nuclease free water; Affymetrix Cat.#71786 100 ML or Ambion, Cat.# 4387936
- 1x low TE (10mM Tris pH 8.0, 0.1mM EDTA); Affymetrix Cat.# 75793
- PfuUltra II Fusion HS DNA Polymerase; Agilent Cat.# 600670
- 10X PfuUltra II Reaction Buffer

**Control oligos:** 
--

- Tag33FAM
   - 5’ - /5Phos/AG AAC GAT TAG ATC GGA AGA GCG TCG TGT A/36-FAM/ - 3’
is a fluorescent positive control oligo for first ligation and sample pooling. Use in place of a barcoded adaptor, for one sample, in first ligation, step 5. Success is indicated if fluorescence appears in 200-500nt smear:
- TagDNA+
   - 5’-TAC ACG ACG CTC TTC CGA TCT TCA GTC AGT ATG TAC GCG TAG CGC AGC GAG CGG CGG GTG GCC ACG TCG CGG CAC ACG CGG ATG GAC AGG ATC GGG CCG GCG GGC AGG AAC TTC TCG TAG AGC ATG GCC TCG GTC ACG TCG GCG TGC AGG TCG CCC ACG TAG AGC GAG GCC AGC GGG TAC CCC GGG CCG CTG GCG TTC AT - 3’
is a 200bp oligo as positive control for 2nd ligation through PCR. Use 1.25uM (0.5uL of 100uM stock) in place of cDNA in control reaction in step 11. Its 3’ end resembles a cDNA product for a library with Tag barcode CTGACTGA (distinct from Tag1-32, Tag33FAM), and the insert is “random” (elephant PABP 1st exon).
