# RNATagSeq


@(General Genomics)[TagSeq, Protocol, Slack]

05 November 2015
This protocol is for RNA sequencing (RNASeq) library preparation using the RNATagSeq method of Shishkin, et al. (2015). Simultaneous generation of many RNA-seq libraries in a single reaction. Nature Methods, 12(4), 323–325. http://doi.org/10.1038/nmeth.3313 (Broad institute).
This document is adapted from the Drummond lab: http://drummondlab.org/protocols/protocol/rnatagseq-library-prep/

**(Protocol Overview)**
--

## Day 1

#### Step 1. Check RNA quality
You should start the protocol with approximately 400ng (nano grams) total RNA per sample (according to Shishkin et al 2015) 
OR 20ug (micro grams) total from across all samples (according to Drummond et al 2015)
Make sure the RNA is of high quality. ![pic](http://i.imgur.com/srDKeKE.jpg)
#### Step 2. Fragment RNA
#### Step 3. Digest DNA and repair RNA
#### Step 4. Cleanup (Using RNA Clean XP Beads UNTIL PCR enrichment test Day 3)
SAFE STOPPING POINT!!!  If you are stopping here for the day, then add 2 uL of SUPERase (instead of 1 uL). 
#### Step 5. QC point. You should have  500-800pg/uL (per Tapestation) and a Tapestation trace like this.  
I DO NOT KNOW THAT THESE TARGET QUANTITIES ARE CORRECT!
![enter image description here](http://i.imgur.com/TSAyIFO.jpg)

## Day 2

#### Step 6. Ligate 3’ barcoded Adaptor
#### Step 7. Pool barcoded RNA with Zymo
#### Step 8. QC point. You should have 20 ng/uL (per Qubit) and a Tapestation trace like this.  
I DO NOT KNOW THAT THESE TARGET QUANTITIES ARE CORRECT!![Imgur](http://i.imgur.com/XiObeks.jpg)
#### Step 9. PolyA pulldown
#### Step 10. QC Point. Much of the RNA will be lost. Please check quantities to confirm sufficient material to proceed.
#### Step 11. First Strand cDNA
#### Step 12. Degrade RNA
#### Step 13. 1st Strand Cleanup
#### Step 14. Ligate 3’ Universal Adaptor (overnight ligation at 22 degrees Celcius in PCR machine)
THIS IS NOT A SAFE STOPPING POINT FOR LONGER THAN AN OVERNIGHT INCUBATION.

## Day 3

#### Step 15. Cleanup (Last Step Still Using RNA Clean XP Beads)
#### Step 16. Test PCR (Using Ampure XP Beads beginning here and for the remainder of the protocol)
#### Step 17. Cleanup
#### Step 18. QC Point. Chose between your three cycle settings based upon which pcr product looks optimal.  You should have X ng/uL and a Tapestation trace like this.
#### Step 15. Real PCR
#### Step 16. Cleanup
#### Step 17. Final Cleanup
#### Step 18. DNA Tapestation QC Point. You should have X ng/uL and a Tapestation trace like this.

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

**Protocol Differences**

****AL & LK note that we have been drying for 10 minutes (according to Shishkin) but Drummond recommends 2 minutes.

****AL & LK note that we have been using 70% ETOH (according to Shiskin) but Drummond recommends 80%.

****AL and LK note that we have been eluting with 12 uL water during Day 1 Step 4 (according to Shishkin) but Drummond elutes with 24 uL.  Drummond is effectively diluting their sample in half (because they proceed with 5 uL, which is the same as Shishkin).


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


#### 1) Check RNA quality by running on the Agilent Bioanalyzer: 1 hour

- Place 0.5-5 ug of total RNA in a tube. For large numbers of samples, the input per sample could be reduced as to not exceed the maximum input of RiboZero (5ug) at step 5. Since about 25% of the input remains prior to adaptor ligation, less than 20ug total RNA per pool (end of step 4) is recommended. For smaller number of samples, higher input is recommended to ensure sufficient material remains after rRNA depletion.
- Increase the volume to 30uL with Nuclease free water
- Add 2uL of SUPERase-IN (20U/uL)
- Final total volume = 32uL (25ng/uL)
- Continue to next step or freeze at -80C until ready to process samples

***AL & LK originally input 400 ng total of each sample (for 8 samples: therefore 3.2 ug total RNA) in 15 uL of Water and added 1 uL SUPERase, for a final volume of 16 uL of each sample.  It appears as if this protocal (following Shishkin) yields not enough RNA.

***AL & LK CURRENTLY trialing 2.5 ug total of each sample (for 8 samples: therefore 20 ug total RNA) in 15 uL of Water and added 1 uL of SUPERase, for a final volume of 16 uL of each sample. This is more in keeping with amounts of RNA recommended by Drummond.

**PAUSE POINT**

#### 2) Fragment RNA using 2x FastAP buffer: 5 minutes

  - Add 8 uL of 10X FastAP buffer to 32 uL RNA from step 1 (up to 1 ug) and mix well.
  - Incubate on preheated thermal cycler for 3 min at 92°C.
  - Place on cold block on ice.

***AL & LK used half these amounts (according to Shishkin): 4 uL of FastAP buffer to 16 uL of RNA from step 1.
**MUST CONTINUE**


#### 3) Digest DNA and repair RNA: Combination DNase/FastAP treatment : 15 minute prep + 30 min incubation = 45 minutes total

  - Make a DNase/FastAP master mix, 40uL per sample:

   | Reagent (for 2X FastAP master)	| Amount	| For 8rxn| 
   | ------------------------------ |-----------| ------ | 
   | nuclease-free water	| 10 uL	| 85uL |
   | RNase Inhibitor, Murine (40U/uL)	| 2 uL	| 17uL| 
   | TURBO DNase (2U/uL)	| 8 uL	| 65uL| 
   | FastAP (1U/uL)	| 20 uL	| 165uL| 
   | Total	| 40 uL	| | 

  - Mix well
  - Aliquot 40 uL into each tube/well with the 40uL of fragmented RNA from step 1.
  - Mix well
  - Incubate on preheated thermal cycler for 30 min at 37°C

****AT THIS TIME, PUT ALL LIGATION REAGENTS AT ROOM TEMPERATURE AND PUT RNA TAPESTATION (Normal Sensitivity) AT ROOM TEMP

***AL & LK used half of these amounts (according to Shishkin): yielding 20 uL of RNA and 20 uL of master mix.

**MUST CONTINUE**

#### 4) Cleanup (2x SPRI) to remove enzymes and reaction buffer: 1 hour

***AL & LK added 40 ul of water (as per Shishkin), bringing reaction volume up to 80 uL before begining the cleanup.

  - Add 2.0x reaction volume of Agencourt RNAClean XP beads (160 uL) and capture RNA on beads:
  - Incubate at room temperature, on HULA MIXER for 15min to bind RNA
  - Place on magnet for 5min, until solution is clear
  - Pipette out and discard clear solution
  - Add 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette off supernatant.
  - Repeat 80% EtOH wash. Let air dry for 5min  ***Drummond Notes said 2 minutes, Shishkin says 10 min. Inconsistant?????
  - Elute off beads with 24 uL nuclease free water

****AL & LK eluted off beads with 12 uL of nuclease free water.

  
&nbsp;
&nbsp;

#### 5A) Proceed : 5 minutes

  - Take 5 uL of each sample and proceed to 1st ligation IF NOT STOPPING FOR THE DAY


#### 5B) QC: 40 minutes

  - QC: Save 1.2 uL from remaining RNA before addition of SUPERase-IN
  - Run 8 random samples on Qubit and another 8 on Tapestation RNA High Sensitivity tape to check the fragmentation profile.
  - Add 1uL SUPERase-IN (20U/uL) to the remaining material and store at -80°C. This can be used as backup if it is necessary to repeat process.  OR Add 2 uL to the sample if stopping for the day or multiple days. 

****If only running 8 samples total, do all on Tapestation and Qubit

**PAUSE POINT**

#### 6A) Ligate 3’ barcoded Adaptor: First Ligation (ssRNA/ssDNA): 10 minutes

  - Add 1 uL of barcoded RNATag adaptor (100 pmole = 1 uL of 100 uM) to 5 uL of dephosphorylated RNA
  - Heat at 70°C for 2 min, place in cold block on ice

#### 6B) Set up First Ligation master mix below NOTE:  30 minutes + 1 hour 30 minute incubation = 2 hours

  - All reagents except enzymes (-20°C ) should be stored at -80°C in single use aliquots and brought to room temp just before use
  - Make up mix at room temp so the reagents don’t start precipitating when combined (if DMSO is added directly into cold buffer it will precipitate)
  - Pipette very slowly for accurate aspiration of PEG (very viscous)

   | Reagent (for Ligation master)	| 1 rxn	| 10 rxns
   |-------------------------------| -------| ---------
   | 10× T4 RNA Ligase Buffer	| 2 uL	| 20 uL| 
   | DMSO (100%)	| 1.8 uL	|  18 uL| 
   | ATP (100 mM)	| 0.2 uL	| 2 uL| 
   | PEG 8000 (50%)	| 8 uL	| 80 uL| 
   | RNase inhibitor, Murine (40U/uL)	| 0.3 uL	| 3 uL| 
   | T4 RNA Ligase 1 (30,000 U/mL)	| 1.8 uL	| 18 uL|
   | MasterMix Total	| 14.1 uL	| 141 uL| 

  - Mix really well by extensive vortexing tube since the solution is very viscous, then spin down briefly in microfuge
  - Add 14.1 uL of ligation master mix to each tube/well containing 6 uL denatured RNA + adaptor (from step 6A) for 20.1 uL reaction volume total.
  - Mix well many times; mix by flicking since the solution is very viscous
  - Incubate at 22°C (room temp), on HULA MIXER, for 1 hour 30 minutes.

**MUST CONTINUE**

&nbsp;
&nbsp;
&nbsp;
&nbsp;

#### 7) Pool barcoded RNA: RLT buffer + Zymo column: 1 hour

  - NOTE: At this point, multiple samples with distinct RNAtag adaptors will be pooled on the same spin column. Do not exceed 5ug RNA per pool, the maximum binding capacity of columns. Attempt to normalize the amounts (using your QC in step 4B) based on the amount of non-ribosomal RNA in each pool, or your other needs.
  - 
***Matt, we do not understand what you are trying to say here regarding normalization and other needs.

-Add 60 uL of RLT buffer to each sample. (You will now have 80 uL total becuase you had 20 uL of product to start with).  
-Add 2 volumes (160 uL) of RNA Binding Buffer to each sample. (You have a total of 240 uL).
-Add an equal volume (240 uL) of 100% Ethanol. (You have a total of 480 uL).
-Pool your samples into one tube and mix.
***If you prefer, you may pool all 8 of your samples into one 14 mL tube (160 uL total pooled sample), and add RLT buffer (480 uL), RNA Binding Buffer (1.28 mL), and 100% ETOH (1.28 mL) in proportional volumes to the pooled samples (for a total final volume of 3.2 mL).
-Add 700 uL of your pooled samples to a single zymo column.  Spin at Room Temperature for 30 seconds at 10,000g.
-Discard the flow-through, keep the column, and add another 700 uL of the pooled samples, then centrifuge for 30 seconds at 10,000g.
-Repeat the previous step until you have spun all of your pooled sample through the zymo column (discarding all the flow through).
-Add 400 uL of RNA Prep Burffer to the column and centrifuge for 30 seconds at 10,000g, then discard the flow-through.
-Add 700 uL of RNA Wash Buffer to the column and centrifuge for 30 seconds at 10,000g, then discard the flow-through.
-Add ANOTHER 400 uL of RNA Wash Buffer to the column and centrifuge for 2 minutes at 10,000g, then discard the flow-through.
-Transfer the zymo column into an RNase-free epindorf tube and add 16 uL of DNase/RNase-free water directly to the column filter and centrifuge for 30 seconds at 10,000g.
-KEEP flow-through in the epindorf tube and add an additional 16 uL of water to the column filter, and centrifuge for 30 seconds at 10,000g. 
-KEEP flow through. You have 32 uL of RNA. Use immidiately or store at -80 degrees Celcius.


#### 8A) Proceed : 5 minutes

  - Take 30 uL of RNA to proceed to PolyA kit IF NOT STOPPING FOR THE DAY


#### 8B) QC: 40 minutes

  - QC: Save 2 uL of RNA for Qubit and Tapestation.
  - Run sample on Qubit Tapestation RNA High Sensitivity tape to check the fragmentation profile.

**PAUSE POINT**

#### 9) Deplete ribosomal RNA with polyA kit. 

  - Will add kit instructions.
  - MAKE SURE TO WASH BEADS BEFORE USE!!!!

#### 10A) Proceed : 5 minutes

  - Take 12 uL of RNA for next step.


#### 10B) QC: 40 minutes

  - QC: Save 2 uL of RNA for Qubit and Tapestation.
  - Run sample on Qubit Tapestation RNA High Sensitivity tape to check the fragmentation profile.

**MUST CONTINUE**

#### 11) Synthesize First Strand cDNA

  - Take 12 uL rRNA depleted RNA (use all the material from Ribo-Zero)
  - Add 2 uL (50 pmoles) of AR2 primer (25 uM) 5’-TAC ACG ACG CTC TTC CGA T-3’
  - Mix well
  - Heat the mixture to 70°C for 2 min and immediately place on cold block on ice

**MUST CONTINUE**

#### 12) Second Strand cDNA synthesis

  - Add in order on ice (the below volums build in a little extra for pipetting errors)

   | Reagent (for RT master)	| 1 rxn	|  
   | --------------------------| -------|  
   | 10× AffinityScript RT Buffer	| 2.2 uL	
   | DTT (0.1M)	| 2.2 uL	| 
   | 25mM dNTP Mix (25mM each)	| 1 uL
   | RNase inhibitor, murine (40U/uL)	| 0.5 uL
   | Total	| 5.2 uL	|


  - Mix well
  - Add 5.2 uL of RT mix to the 14 uL rRNA depleted RNA + AR2 RTprimer on ice
  - Add 0.8 uL of AffinityScript RT Enzyme
  - Mix well and spin for 5 sec
  - Place in preheated (55 °C) incubator or thermocycler. Incubate at 55 °C for 55 minutes.

**MUST CONTINUE**


#### 13) Degrade RNA after reverse transcription

  - NOTE: make fresh working stock solutions of NaOH and Acetic Acid
  - Add 10% reaction vol. of 1M NaOH (2 uL) to each reaction
  - Incubate at 70 °C for 12 minutes
  - Neutralize with 4 uL of 0.5M Acetic Acid; mix well
  - Total volume = 26 uL

**MUST CONTINUE**


#### 14) Cleanup reverse transcription (2x SPRI) to remove enzyme, primers, and reaction buffer

  - Add 14 uL of sterile water to each reaction for a final volume of 40 uL
  - Transfer to new tubes (NaOH may start degrading tubes)
  - Add 2x reaction volume AmpureXP beads (80uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min, remove from magnet.
  - Add 5 uL RNase/DNase free water to beads – KEEP BEADS AND TUBES, do not transfer, do not pause

**MUST CONTINUE**


#### 15) Ligate 3’ Universal Adaptor: Second Ligation (ssDNA/ssDNA) with beads
  - NOTE: 3Tr3 adaptor: 5’-/5Phos/AGA TCG GAA GAG CAC ACG TCT G-/3SpC3/ 3’

  - Add 2 uL (80 pmoles) of 3Tr3 adaptor to cDNA
  - Heat at 75°C for 3 min; Place on cold block on ice
  - Make ligation reaction master mix (can be prepared ahead of time, at RT):

  - 2nd Ligation Master Mix:
  - Mix in order (the below volums build in a little extra for pipetting errors)

   | Reagent (for Ligation 2 master)	| 1 rxn	
   | -----------------------------------| ------
   | 10× T4 RNA Ligase Buffer	| 2.2 uL
   | DMSO (100%)	| 1 uL
   | ATP (100 mM)	| 0.3 uL
   | PEG 8000 (50%)	| 8.9 uL
   | T4 RNA Ligase 1 (30,000U/mL)	| 1.7 uL
   | Total	| 13.0 uL

  - Mix really well by extensive vortexing tube since the solution is very viscous
  - Spin down briefly in microfuge
  - Swirl the 7uL cDNA/beads/water with pipet tip, THEN add 13 uL ligation 2 master mix.
  - Mix well by pipetting up and down 20x or cap tubes and flick several times; solution is viscous
  - Quick spin (low speed centrifuge, to get everything to bottom of tube)
  - Incubate overnight at 22 °C

**MUST CONTINUE**

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

#### 16) Cleanup (2x SPRI) to remove adaptors

  - Add 2x reaction volume SPRI beads (80uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute DNA by adding 30 uL RNase/DNase free water, transfer to new tube.
  - **2nd Cleanup (1.5x SPRI) to remove the remaining adaptors**

  - Add 1.5x reaction volume SPRI beads (45 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min 
  - Elute DNA by adding 25 uL RNase/DNase free water, transfer to new tube.

**PAUSE POINT**

#### 17) Test PCR Amplification to determine final cycle number
  - NOTE: P5 primer: P5_RNATag, 5’-AAT GAT ACG GCG ACC ACC GAG ATC TAC ACT CTT TCC CTA CAC GAC GCT CTT CCG ATC T-3’

  - Set up a test PCR using 5 uL of ss cDNA sample and 9-12 cycles of PCR (based on experience with pool of 16 reactions, each starting with ~400ng total RNA)
  - Include a negative control (water) for each primer set
  - Make PCR Master Mix (4 rxns=2 libraries, +ve ctrl, -ve ctrl):

  - Add in order:

   | Reagent (for PCR master mix)	| 1 rxn	| 
   | -------------------------------| 
   | Water, PCR-clean	| 15.4 uL	| 
   | 10X AccuPrime Buffer	| 2.5 uL	| 
   | P5_RNATag, 12.5 uM)	| 1 uL	| L
   | P7 index primer | 1uL | 
   | AccuPrime HiFi Taq | .1uL 
   | cDNA from step 14 | 5uL
   | Total	| 20 uL	| 74 uL

  - Mix well
  - Aliquot 20 uL / sample into PCR tubes
  - Add 5 uL of ss cDNA from step 11, or water (for negative control)
  - Mix well and aliquot 8 ul into each of 3 tubes

&nbsp;
&nbsp;
&nbsp;


Place each in a thermal cycler with cycling conditions:

  - start: 98°C, 3min
  - cycle: 9, 12, 15 cycles (for test PCR) 98°C, 30sec; 55°C, 30sec; 70°C, 30sec
  - end: 70°C, 2min; 4°C, hold

**MUST CONTINUE**


#### 15) Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - increase reaction to 40uL with sterile water
  - Add 1.5x reaction volume SPRI beads (60 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 10 uL 1x low TE (10 mM Tris, 0.1M EDTA)
  - QC test PCR amplification on Agilent DNA HS chip

  - **NOTE:** Based on test results change the cycle number, if necessary, and set up more reactions to provide enough material to send for sequencing. Library should have smooth profile 200-500nt long; visible single bands, or a “shoulder” of larger products, indicate PCR artefacts.


**PAUSE POINT**


#### 16) PCR for Sequencing library

  - Choose the optimal PCR cycle # based on Bioanalyzer QC of test (step 15).
  - Include a negative control (water) for each primer set
  - Make PCR Master Mix (3 rxns=2 libraries, half size +ve ctrl, half size -ve ctrl):

  - Add in order:


   | Reagent (for PCR master mix)	| 1 rxn	| 3 rxns
   | -------------------------------| ------| ------
   | Water, PCR-clean	| 28.6 uL	| 57.2 uL
   | 10X Pfu Ultra II Buffer	| 5 uL	| 10 uL
   | dNTP mix (10mM each)	| 1.4 uL	| 2.8 uL
   | P5 primer (P5_RNATag, | 12.5 uM)	| 2 uL	| 4 uL
   | Total	| 37 uL	| 74 uL

  - Mix well
  - Aliquot 37 uL / sample into PCR tubes
  - Add 2 uL of appropriate P7 index primer to each well
  - Add 10 uL of ss cDNA from step 11, or water (for negative control)
  - Add 1 uL of Pfu Ultra II Polymerase.

  - Mix well and aliquot 10 ul into each of 5 wells of a strip tube (amplification is apparently more robust in smaller volumes).

&nbsp;
&nbsp;
&nbsp;
&nbsp;

Place each in a thermal cycler with the cycling conditions:

  - start: 98°C, 3min  
  - cycle: # determined from test PCR 98°C, 30sec; 55°C, 30sec; 70°C, 30sec
  - end: 70°C, 2min; 4°C, hold

**MUST CONTINUE**


#### 17) Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - Pool PCR reaction (50 uL)
  - Add 1.5x reaction volume SPRI beads (75 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 50 uL water and transfer to new tubes.
  - Final Cleanup (0.8x SPRI) to remove remaining PCR primers:

#### 18) Second Round Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - Add 0.8x reaction volume SPRI beads (40 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 25 uL 1x low TE (10 mM Tris, 0.1M EDTA)

#### 19) Check quantity/quality on Tapestation.

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
MacManes Lab is not currently using, though maybe we should?

- Tag33FAM
   - 5’ - /5Phos/AG AAC GAT TAG ATC GGA AGA GCG TCG TGT A/36-FAM/ - 3’
is a fluorescent positive control oligo for first ligation and sample pooling. Use in place of a barcoded adaptor, for one sample, in first ligation, step 5. Success is indicated if fluorescence appears in 200-500nt smear:
- TagDNA+
   - 5’-TAC ACG ACG CTC TTC CGA TCT TCA GTC AGT ATG TAC GCG TAG CGC AGC GAG CGG CGG GTG GCC ACG TCG CGG CAC ACG CGG ATG GAC AGG ATC GGG CCG GCG GGC AGG AAC TTC TCG TAG AGC ATG GCC TCG GTC ACG TCG GCG TGC AGG TCG CCC ACG TAG AGC GAG GCC AGC GGG TAC CCC GGG CCG CTG GCG TTC AT - 3’
is a 200bp oligo as positive control for 2nd ligation through PCR. Use 1.25uM (0.5uL of 100uM stock) in place of cDNA in control reaction in step 11. Its 3’ end resembles a cDNA product for a library with Tag barcode CTGACTGA (distinct from Tag1-32, Tag33FAM), and the insert is “random” (elephant PABP 1st exon).


---
