# RNATagSeq_polyA_first


@(RNATagSeq)[TagSeq, Protocol, Slack]

**VERSION Monday, January 11, 2016**

***This protocol reflects the notes in the protocol LK and AL were trouble-shooting.***

This protocol is for RNA sequencing (RNASeq) library preparation using the RNATagSeq method of Shishkin, et al. (2015). Simultaneous generation of many RNA-seq libraries in a single reaction. Nature Methods, 12(4), 323–325. http://doi.org/10.1038/nmeth.3313 (Broad institute).

This document is adapted from the Drummond lab: http://drummondlab.org/protocols/protocol/rnatagseq-library-prep/

The signifocant modification here is using polyA purification instead of RiboZero. This means that the order of the protocol needs to be changed, mainly by bringing the polyA module to step 2. This also means that we start with 5ug total RNA, which is the max going into the polyA kit. 

Furthermore, the movement of the PolyA module to the front of the protocol changes the amounts of reagents and samples from the original Shishkin protocol.

**(Protocol Overview)**
--

## Day 1

#### Step 1. Check RNA quality
You should start the protocol with approximately 5ug total RNA per sample. Make sure the RNA is of high quality. ![pic](http://i.imgur.com/srDKeKE.jpg)

&nbsp;
&nbsp;
&nbsp;



#### Step 2. polyA pulldown 
Should have between ~25-50ng of RNA left (0.5% - 1% of input). A 1% return is the maximum yield retrieved by the kit (according to the manufacturer's technicians).
 ![polyA](http://i.imgur.com/qZ8MEq3.jpg)
#### Step 3. Fragment RNA
#### Step 4. Digest DNA and repair RNA
#### Step 5. Cleanup
This is an important QC point. You should have  x pg/uL (per Tapestation) and a Tapestation trace like this:

WE NEED TO PUT A NEW TRACE HERE

&nbsp;
&nbsp;
## Day 2

#### Step 6. Ligate 3’ barcoded Adaptor
#### Step 7. Pool barcoded RNA with Zymo
QC Step: You should have x ng/uL (per Qubit) and a Tapestation trace like this.


WE NEED TO PUT A NEW TRACE HERE

#### Step 8. First Strand cDNA 
#### Step 9. Second Strand cDNA (reverse transcription step)
#### Step 10. Degrade RNA
#### Step 11. Cleanup
#### Step 12. Ligate 3’ Universal Adaptor (overnight ligation)

## Day 3

#### Step 13. Cleanup
#### Step 14. Test PCR
#### Step 15. Cleanup
QC Step: You should have X ng/uL and a Tapestation trace like this.

WE NEED TO PUT A NEW TRACE HERE

#### Step 16. Real PCR
#### Step 17. Cleanup
#### Step 18. Final Cleanup
#### Step 19. DNA Tapestation
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

Protocol Differences

****AL & LK note that we have been drying for 10 minutes (according to Shishkin) but Drummond recommends 2 minutes.  We ARE NOW DRYING FOR 3 minutes!

****AL & LK note that we have been using 70% ETOH (according to Shiskin) but Drummond recommends 80%.

****AL and LK note that we have been eluting with 12 uL water during Day 1 Step 4 (according to Shishkin) but Drummond elutes with 24 uL. Drummond is effectively diluting their sample in half (because they proceed with 5 uL, which is the same as Shishkin).

(Notes)

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


#### 1) Check RNA quality by running on the Agilent Bioanalyzer

- Place 5ug of total RNA in a tube.
- Increase the volume to 50uL with Nuclease free water
- Add 2 uL of SUPERase-IN (20U/uL)
- Final total volume = 52uL (100ng/uL)
- Continue to next step or freeze at -80C until ready to process samples


NOTE PREVIOUS PROTOCOL DIFFERENCES:

***AL & LK originally input 400 ng total of each sample (for 8 samples: therefore 3.2 ug total RNA) in 15 uL of Water and added 1 uL SUPERase, for a final volume of 16 uL of each sample. It appears as if this protocal (following Shishkin) yields not enough RNA.

***AL & LK previously trialed 2.5 ug total of each sample (for 8 samples: therefore 20 ug total RNA) in 15 uL of Water and added 1 uL of SUPERase, for a final volume of 16 uL of each sample. This is more in keeping with amounts of RNA recommended by Drummond.

**PAUSE POINT**


#### 2) Deplete ribosomal RNA with polyA kit. 

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
- Remove the plate from the magnetic rack
- Wash the beads twice with 200 μl of Wash Buffer to remove unbound RNA. Pipette the entire volume up and down 6 times to mix thoroughly.
- Place the tubes on the magnetic rack at room temperature for 2 minutes.
- Remove and discard all the supernatant from each well of the plate using a multichannel pipette. Take care not to disturb the beads.
- Remove the tubes from the magnetic rack.
- Spin down sample so beads/RNA collect at the bottom of the tube.
- Add 50 μl of Tris buffer to each well of the plate. Gently pipette the entire volume up and down 6 times to mix thoroughly.
- Place the tubes on the thermal cycler. Close the lid and heat the sample at 80°C for 2 minutes, then hold at 25°C to elute the poly-A RNA from the beads
- Remove the tubes from the thermal cycler when the temperature reaches 25°C

**Second mRNA Purification**

- Add 50 μl of RNA binding buffer to each sample to allow the RNA to bind to the beads. Gently pipette the entire volume up and down 6 times to mix thoroughly.
- Vortex and place the tubes on HULA MIXER and incubate at room temperature for 10 minutes to allow the RNA to bind to the beads.
- Place the tubes on the magnetic stand at room temperature for 2 minutes.
- Remove and discard all of the supernatant from each tube. Take care not to disturb the beads.
- Remove the tubes from the magnetic stand.
- Wash the beads twice with 200 μl of Wash Buffer. Gently pipette the entire volume up and down 6 times to mix thoroughly.
- Place tube on magnetic rack for 2 minutes.
- Remove and discard all of the supernatant from each tube. Take care not to disturb the beads.
- Remove the tubes from the magnetic stand.
- Spin down so beads/RNA collect at the bottom of the tube.
- Remove the mRNA from the beads by adding 32 µl of the Tris Buffer and incubating the sample at 80°C for 2 minutes. 
- NOTE this is a different elution amount than listed in the product manufacturers' protocol!!
- Immediately, place the tubes on the magnetic rack
- Collect the purified mRNA by transferring the supernatant to a clean nuclease-free PCR Tube
- QC: Take 1uL for tapestation. 

**MUST CONTINUE**

#### 3) Fragment RNA using 2x FastAP buffer

  - Add 8 uL of 10X FastAP buffer to 32 uL RNA from step 1 (up to 1 ug) and mix well.
  - Incubate on preheated thermal cycler for 3 min at 92°C.
  - Place on cold block on ice.
  
PLEASE NOTE: AL & LK used half these amounts (according to Shishkin): 4 uL of FastAP buffer to 16 uL of RNA from step 1.

**MUST CONTINUE**


#### 4) Digest DNA and repair RNA: Combination DNase/FastAP treatment

PLEASE NOTE AL & LK used half of these amounts (according to Shishkin): yielding 20 uL of RNA and 20 uL of master mix.


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
 
****AT THIS TIME, PUT ALL LIGATION REAGENTS AT ROOM TEMPERATURE 

**MUST CONTINUE**

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

#### 5) Cleanup (2x SPRI) to remove enzymes and reaction buffer


PLEASE NOTE AL & LK added 40 ul of water (as per Shishkin), bringing reaction volume up to 80 uL before begining the cleanup.

  - Add 2.0x reaction volume of Agencourt RNAClean XP beads (160 uL) and capture RNA on beads:
  - Incubate at room temperature, on HULA MIXER for 15min to bind RNA
  - Place on magnet for 5min, until solution is clear
  - Pipette out and discard clear solution
  - Add 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette off supernatant.
  - Repeat 80% EtOH wash. Let air dry for 5min
  - Elute off beads with 7 uL nuclease free water if you are not trying to have any in reserve, which is what we are doing now

PLEASE NOTE that Drummond says elute off beads with 24 uL of nuclease free water

PLEASE NOTE AL & LK originally eluted off beads with 12 uL of nuclease free water.
     


#### 5A) Proceed

  - Take 5 uL of each sample and proceed to 1st ligation


#### 5B) QC

  - QC: Save 1.2 uL from remaining RNA before addition of SUPERase-IN
  - Run 8 random samplings on Qubit and another 8 on Tapestation RNA High Sensitivity tape to check the fragmentation profile.
  - **If only running 8 samples total, do all on Tapestation and Qubit
  - Add 1uL SUPERase-IN (20U/uL) to the remaining material and store at -80°C. This can be used as backup if it is necessary to repeat process

**PAUSE POINT**

#### 6A) Ligate 3’ barcoded Adaptor: First Ligation (ssRNA/ssDNA)

  - Add 1 uL of barcoded RNATag adaptor (100 pmole = 1 uL of 100 uM) to 5 uL of dephosphorylated RNA
  - Heat at 70°C for 2 min, place in cold block on ice

#### 6B) Set up First Ligation master mix below NOTE:

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

***NOTE LK and AL add the T4 RNA Ligase 1 buffer to the MM (not as a separate step, so this protocol has been modified so that it is added as part of the MM, not added afterwards. HOWEVER, the enzyme cannot be added to the MM until right before it is added to the RNA.  So make up the MM without the enzyme with all the other reagents at room temperature, and then wait till the last possible minute to add the enzyme to the master mix, right before you use the MM.

  - Mix really well by extensive vortexing tube since the solution is very viscous, then spin down briefly in microfuge
  - Add 14.1 uL of ligation master mix to each tube/well containing 6 uL denatured RNA + adaptor (for a 20.1 uL total reaction volumne).
  - Mix well many times; mix by flicking since the solution is very viscous
  - Incubate at 22°C (room temp), on HULA MIXER, for 1 hour 30 minutes.



**MUST CONTINUE**


#### 7) Pool barcoded RNA: RLT buffer + Zymo column

  - NOTE: At this point, multiple samples with distinct RNAtag adaptors will be pooled on the same spin column. Do not exceed 5ug RNA per pool, the maximum binding capacity of columns. 
  - **Attempt to normalize** the amounts (using your Qubit-QC in step 5B) based on the amount of non-ribsomal RNA in each pool, or your other needs.

NOTE that LK and AL have never normalized these amounts based upon previous QC

- DO NOT ADD RLT lysis buffer!!! (We have been told not to by ZYMO technicians)
- Pool all 8 samples into one tube (160 uL total)
- **Add 2 volumes (320uL) of RNA Binding Buffer to each sample, and vortex. (You will have a total of 480 uL liquid).**
- **Add an equal volume (480 uL) of 100% Ethanol and votex. (You have a total of 960 uL of liquid).**
- PLEASE NOTE AL and LK have tried multiple permutations of this (with different quantities), and we think these amounts work.
- Add a maximum of 700 uL of your pooled samples to a single zymo column. Spin at Room Temperature for 30 seconds at 10,000g.
- Therefore add 480 uL twice!
- Discard the flow-through, keep the column, and add another maximum of 700 uL of the pooled samples, then centrifuge for 30 seconds at 10,000g.
- Repeat the previous step until you have spun all of your pooled sample through the single zymo column (discarding all the flow-through).
- Add 400 uL of RNA Prep Buffer to the column and centrifuge for 30 seconds at 10,000g, then discard the flow-through.
- Add 700 uL of RNA Wash Buffer to the column and centrifuge for 30 seconds at 10,000g, then discard the flow-through.
- Add ANOTHER 400 uL of RNA Wash Buffer to the column and centrifuge for 2 minutes at 10,000g, then discard the flow-through.
- Transfer the zymo column into an RNase-free epindorf tube (cut off the cap) and add 13 uL of DNase/RNase-free water directly to the column filter and centrifuge for 30 seconds at 10,000g.
- KEEP flow-through in the epindorf tube and add an additional 13 uL of water to the column filter, and centrifuge for 30 seconds at 10,000g.
- KEEP flow through. You have ~26 uL of RNA. 
- QC on tape station with 2 uL sample
- Use immediately or store at -80 degrees Celcius.

PLEASE NOTE AL and LK previously did two elutions of 16 uL for a total of 32 uL final volume RNA, which they then added 20 ul of H2O to bring the total volume to ~50 uL for the PolyA step (which was the next step in the previous protocol). 

However, because the next step in this PolyA first protocol requires only a 12 uL elution for the first strand synthesis, this zymo elution has to be done now with only 13 uL per elution so that you have ~26 total (which will allow you 2 uL for the TapeStation and ~24 uL for the next step, which is excellent because you then have double what you need for the next step, so we will do twice as much mastermix and use all the sample). 

**PAUSE POINT** 


#### 8) Synthesize First Strand cDNA

  - Take 24 uL mRNA (use all the material from previous step) 
  - (Was originally 12 uL mRNA, but we doubled it)
  - Add 4 (50 pmoles) of AR2 primer (25 uM) 5’-TAC ACG ACG CTC TTC CGA T-3’ 
  - (Was originally 2 uL AR2 primer, but we doubled it)
  - Mix well
  - Heat the mixture to 70°C for 2 min and immediately place on cold block on ice

**MUST CONTINUE**

#### 9) Second Strand cDNA synthesis (This is called Reverse Transcription in SHISHKIN)

  - Add in order on ice (the below volumes build in a little extra for pipetting errors)

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

PLEASE NOTE AL and LK used a slightly different MM recipe (as per SHISHKIN), see below:

   | Reagent (for RT master)	| 1 rxn	|  
   | --------------------------| -------|  
   | 10× AffinityScript RT Buffer	| 2.0 uL	
   | DTT (0.1M)	| 2.0 uL	| 
   | 25mM dNTP Mix (25mM each)	| 0.8 uL
   | RNase inhibitor, murine (40U/uL)	| 0.4 uL
   | AffinityScript RT Enzyme	| 0.8 u
   | Total	| 6.0 uL	|


  - Mix well
  - Add 6.0 uL of RT mix to the 14 uL rRNA depleted RNA + AR2 RTprimer on ice
  - Mix well and spin for 5 sec
  - Place in preheated (55 °C) incubator or thermocycler. Incubate at 55 °C for 55 minutes.

**HOWEVER, We doubled the recipe, to reflect twice as much mRNA from Zymo and twice as much First strand cDNA, see below for doubled recipe:**

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


#### 10) Degrade RNA after reverse transcription

  - NOTE: make fresh working stock solutions of NaOH and Acetic Acid
  - Add 10% reaction vol. of 1M NaOH (4 uL) to each reaction
  - (was previously 2 ul, but we doubled it)
  - Incubate at 70 °C for 12 minutes
  - Neutralize with 8 uL of 0.5M Acetic Acid; mix well
  - (was previously 4 ul, but we doubled it)
  - Total volume = 52 uL
  - (was previously Total volume = 26 uL, but we doubled everything)
  
**MUST CONTINUE**

&nbsp;
&nbsp;
&nbsp;

#### 11) Cleanup reverse transcription (2x SPRI) to remove enzyme, primers, and reaction buffer

**AT this time put Ligation reagents at ROOM TEMP**

  - Add 28 uL of sterile water for a final reaction volume of 80 uL
  - (We previously added 14 uL of sterile water to each reaction for a final volume of 40 uL, but that was before we doubled everything)
  - Transfer to new tubes (NaOH may start degrading tubes)
  - Add 2x reaction volume RNACLEAN XP beads (160uL) to the sample in new tubes, and mix up/down 10x
  - (We previously added 80 uL RNACLEAN XP beads, before we doubled)
  - (Drummond said use AMPURE beads, but this is wrong. USE RNA clean beads)
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min, remove from magnet.
  - Add 5 uL RNase/DNase free water to beads 
  – KEEP BEADS AND TUBES, do not transfer, do not pause

**MUST CONTINUE**


#### 12) Ligate 3’ Universal Adaptor: Second Ligation (ssDNA/ssDNA) with beads
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


PLEASE NOTE LK AND AL did a different MM (as per SHISHKIN), see below:

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
  - Swirl the 7uL cDNA/beads/water with pipet tip, THEN add 13 uL ligation 2 master mix.
  - Mix well by pipetting up and down 20x or cap tubes and flick several times; solution is viscous
  - Quick spin (low speed centrifuge, to get everything to bottom of tube)
  - Incubate overnight at 22 °C

**THIS IS NOT A LONG TERM STOPPING POINT, JUST AN OVERNIGHT INCUBATION**


**MUST CONTINUE**

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;


#### 13) Cleanup (2x SPRI) to remove adaptors

***AL and LK increased to 2x reaction volume with water (added 20 UL of water), we think they just didn't list this step, but they must have done it!!

  - Add 2x reaction volume Agencourt RNAClean XP beads (80uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute DNA by adding 30 uL RNase/DNase free water, transfer to new tube.
  - **2nd Cleanup (1.5x SPRI) to remove the remaining adaptors**


(AL and LK used a different quantity (25 ul x 1.5 = 37.5 uL) but DISREGARD now)


  - Add 1.5x reaction volume Agencourt RNAClean XP beads (45 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min 
  - Elute DNA by adding 25 uL RNase/DNase free water, transfer to new tube.

**PAUSE POINT**

#### 14) Test PCR Amplification to determine final cycle number
  - NOTE: P5 primer: P5_RNATag, 5’-AAT GAT ACG GCG ACC ACC GAG ATC TAC ACT CTT TCC CTA CAC GAC GCT CTT CCG ATC T-3’

  - Set up a test PCR using 5 uL of ss cDNA sample and 9-12 cycles of PCR (based on experience with pool of 16 reactions, each starting with ~400ng total RNA)
  - Include a negative control (water) for each primer set
  - Make PCR Master Mix (4 rxns=2 libraries, +ve ctrl, -ve ctrl):

  - Add in order:

   | Reagent (for PCR master mix)	| 1 rxn	| 
   | -------------------------------| 
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
  
**LK and AL did the protocl the above way (as per Shishkin). This was accomplished differently by Drummond in order to waste less sample. We should evalute what is more appropriate by revisiting the Drummond Protocol. However, once we figure out our cycle number, we will probably use that in the future and not need to test each time we do the protocol.**
&nbsp;
&nbsp;
&nbsp;


Place each in a thermal cycler with cycling conditions:

  - start: 98°C, 3min
  - cycle: 9, 12, 15 cycles (for test PCR) 98°C, 30sec; 55°C, 30sec; 70°C, 30sec
  - end: 70°C, 2min; 4°C, hold

****LK and AL used 65 degrees instead of 70 degrees for the cycling steps. Which is more appropriate?

**MUST CONTINUE**


**Please note that the XP bead type is now changing from Agencourt RNAClean XP beads to AMPure XP beads for the remainder of the protocol**

edits stopped here
_____________________________________________________________

#### 15) Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - increase reaction to 40uL with sterile water
  - (PLEASE NOTE LK & AL did not add any water at this point, Shishkin says to increase to 25uL with water, but we already had 25 uL)
  - Add 1.5x reaction volume AMPpure XP beads (60 uL) to the sample in new tubes, and mix up/down 10x
  - (PLEASE NOTE LK and & AL added only 37.5 uL of beads at this step as per Shishkin)
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


PLEASE NOTE LK and AL did their MM differently (as per Shishkin), see below:

   | Reagent (for PCR master mix)  | 1 rxn
   | Water, PCR-clean	| 30.8 uL
   | 10X AccuPrime PCR Buffer 1	| 5 uL
   | enrF (12.5 uM)	| 2 uL
   | p7enr1 (12.5 uM)	| 2 uL
   | AccuPrime HiFi Taq (5U/uL)	| 0.2 uL
   | Total	| 40 uL

  - Mix well
  - Aliquot 40 uL / sample into PCR tubes
  - Add 10 uL of ss cDNA


&nbsp;
&nbsp;
&nbsp;
&nbsp;

Place each in a thermal cycler with the cycling conditions:

  - start: 98°C, 3min  
  - cycle: # determined from test PCR 98°C, 30sec; 55°C, 30sec; 70°C, 30sec
  - end: 70°C, 2min; 4°C, hold

PLEASE NOTE LK and AL used 65 degrees instead of 70 degrees for the cycling steps. Which is more appropriate?

**MUST CONTINUE**


#### 17) Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - Pool PCR reaction (50 uL) ***THIS MAKES NO SENSE!!! 
  - Add 1.5x reaction volume SPRI beads (75 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature, on HULA MIXER for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 50 uL water and transfer to new tubes.
  - ***Shishkin says elute with 25 uL of water instead!
  


#### 18) Second Round Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - Add 0.8x reaction volume SPRI beads (40 uL) to the sample in new tubes, and mix up/down 10x
  - ***Shishkin says use a 0.7x (17.5 uL) AMPure beads
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
