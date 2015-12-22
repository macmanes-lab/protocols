# RNATagSeq


@(General Genomics)[TagSeq, Protocol, Slack]

05 November 2015
This protocol is for RNA sequencing (RNASeq) library preparation using the RNATagSeq method of Shishkin, et al. (2015). Simultaneous generation of many RNA-seq libraries in a single reaction. Nature Methods, 12(4), 323–325. http://doi.org/10.1038/nmeth.3313 (Broad institute).




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


# MAIN PROTOCOL


### 1.. Check RNA quality by running on the Agilent Bioanalyzer

- Place 0.5-5 ug of total RNA in a tube. For large numbers of samples, the input per sample could be reduced as to not exceed the maximum input of RiboZero (5ug) at step 5. Since about 25% of the input remains prior to adaptor ligation, less than 20ug total RNA per pool (end of step 4) is recommended. For smaller number of samples, higher input is recommended to ensure sufficient material remains after rRNA depletion.
- Increase the volume to 30uL with Nuclease free water
- Add 2uL of SUPERase-IN (20U/uL)
- Final total volume = 32uL (25ng/uL)
- Continue to next step or freeze at -80C until ready to process samples

**PAUSE POINT**

### 2.. Fragment RNA using 2x FastAP buffer

  - Add 8 uL of 10X FastAP buffer to 32 uL RNA from step 1 (up to 1 ug) and mix well.
  - Incubate on preheated thermal cycler for 3 min at 92°C.
  - Place on cold block on ice.

**MUST CONTINUE**


### 3.. Digest DNA and repair RNA: Combination DNase/FastAP treatment

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

**MUST CONTINUE**

### 4.. Cleanup (2x SPRI) to remove enzymes and reaction buffer

  - Add 2.0x reaction volume of Agencourt RNAClean XP beads (160 uL) and capture RNA on beads:
  - Incubate at room temperature, on HULA MIXER for 15min to bind RNA
  - Place on magnet for 5min, until solution is clear
  - Pipette out and discard clear solution
  - Add 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette off supernatant.
  - Repeat 80% EtOH wash. Let air dry for 5min
  - Elute off beads with 24 uL nuclease free water
  - Take 5 uL of each sample and proceed to 1st ligation
  - QC: Save 1.2 uL from remaining RNA before addition of SUPERase-IN
  - Run 16 random samplings on Tapestation RNA High Sensitivity tape to check the fragmentation profile of each batch of 32
  - Add 1uL SUPERase-IN (20U/uL) to the remaining material and store at -80°C. This can be used as backup if it is necessary to repeat process

**PAUSE POINT**

### 5.. Ligate 3’ barcoded Adaptor: First Ligation (ssRNA/ssDNA)

  - Add 1 uL of barcoded RNATag adaptor (100 pmole = 1 uL of 100 uM) to 5 uL of dephosphorylated RNA
  - Heat at 70°C for 2 min, place in cold block on ice

### 6.. Set up First Ligation master mix below NOTE:

  - All reagents except enzymes (-20°C ) should be stored at -80°C in single use aliquots and brought to room temp just before use
  - Make up mix at room temp so the reagents don’t start precipitating when combined (if DMSO is added directly into cold buffer it will precipitate)
  - Pipette very slowly for accurate aspiration of PEG (very viscous)

   | Reagent (for Ligation master)	| 1 rxn	| 8 rxns
   |-------------------------------| -------| ---------
   | 10× T4 RNA Ligase Buffer	| 2 uL	| 18 uL| 
   | DMSO (100%)	| 1.8 uL	| 14.9 uL| 
   | ATP (100 mM)	| 0.2 uL	| 1.7 uL| 
   | PEG 8000 (50%)	| 8 uL	| 68 uL| 
   | RNase inhibitor, Murine (40U/uL)	| 0.3 uL	| 2.5 uL| 
   | RNA: up to 250ng	| 5 uL	| | 
   | Total	| 12.3 uL	| 105 uL| 

  - Mix really well by extensive vortexing tube since the solution is very viscous, then spin down briefly in microfuge
  - Add 12.3 uL of ligation master mix to each tube/well containing 6 uL denatured RNA + adaptor.
  - Add 1.8 uL of T4 RNA Ligase 1 (30,000U/mL) to each tube/well. 20.1 uL reaction volume total.
  - Mix well many times; mix by flicking since the solution is very viscous
  - Incubate at 22°C (room temp) for 1 hour 30 minutes.

**MUST CONTINUE**

### 7.. Pool barcoded RNA: RLT buffer + Zymo column

  - NOTE: At this point, multiple samples with distinct RNAtag adaptors will be pooled on the same spin column. Do not exceed 5ug RNA per pool, the maximum binding capacity of columns. Attempt to normalize the amounts (using your QC in step 4, or even 1) based on the amount of non-ribosomal RNA in each pool, or your other needs.

  - Add 60 uL of RLT buffer to each sample to inhibit ligase, and mix well (80 uL total)
  - Add 2x reaction vol (160 uL=2x 80 uL) of 1:1 binding buffer: EtOH (100%) to each reaction. 
  - Carefully add reactions to be pooled to a single Zymo column.
  - YOU ARE DOING ZYMO TEST TODAY
  - Wash and spin 1 min 12,000 g, then discard flow-through, once with 400 uL RNA Prep buffer, once with 800 uL RNA Wash buffer, once with 400uL Wash buffer, spin another 1min with no buffer.
  - Elute 2 times with 16 uL nuclease free water for a total volume of 32 uL
  - NOTE: 2 elutions help improve recovery/yield of RNA
  - Save 2 uL for QC-Run on Agilent RNA pico chip to check quantity and fragmentation profile

**PAUSE POINT**

### 8.. Deplete ribosomal RNA with polyA kit. 

  - Will add kit instructions.
  - MAKE SURE TO WASH BEADS BEFORE USE!!!!

**MUST CONTINUE**

### 9.. Synthesize First Strand cDNA

  - Take 12 uL rRNA depleted RNA (use all the material from Ribo-Zero)
  - Add 2 uL (50 pmoles) of AR2 primer (25 uM) 5’-TAC ACG ACG CTC TTC CGA T-3’ AR2, 53% GC, 19bp.
  - Mix well
  - Heat the mixture to 70°C for 2 min and immediately place on cold block on ice

**MUST CONTINUE**

### 10.. Make RT master mix

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


### 11.. Degrade RNA after reverse transcription

  - NOTE: make fresh working stock solutions of NaOH and Acetic Acid
  - Add 10% reaction vol. of 1M NaOH (2 uL) to each reaction
  - Incubate at 70 °C for 12 minutes
  - Neutralize with 4 uL of 0.5M Acetic Acid; mix well
  - Total volume = 26 uL

**MUST CONTINUE**


### 12.. Cleanup reverse transcription (2x SPRI) to remove enzyme, primers, and reaction buffer

  - Add 14 uL of sterile water to each reaction for a final volume of 40 uL
  - Transfer to new tubes (NaOH may start degrading tubes)
  - Add 2x reaction volume SPRI beads (80uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min, remove from magnet.
  - Add 5 uL RNase/DNase free water to beads – KEEP BEADS AND TUBES, do not transfer, do not pause

**MUST CONTINUE**


### 13.. Ligate 3’ Universal Adaptor: Second Ligation (ssDNA/ssDNA) with beads
  - NOTE: 3Tr3 adaptor: 5’-/5Phos/AGA TCG GAA GAG CAC ACG TCT G-/3SpC3/ 3’, 55% GC, 22bp, 5’-Phos and 3’-C3 spacer (or ddC, or dye).

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


### 14.. Cleanup (2x SPRI) to remove adaptors

  - Add 2x reaction volume SPRI beads (80uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute DNA by adding 30 uL RNase/DNase free water, transfer to new tube.
  - **2nd Cleanup (1.5x SPRI) to remove the remaining adaptors**

  - Add 1.5x reaction volume SPRI beads (45 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min 
  - Elute DNA by adding 25 uL RNase/DNase free water, transfer to new tube.

**PAUSE POINT**

### 15.. TEST PCR Amplification to determine final cycle number
  - NOTE: P5 primer: P5_RNATag, 5’-AAT GAT ACG GCG ACC ACC GAG ATC TAC ACT CTT TCC CTA CAC GAC GCT CTT CCG ATC T-3’, 52% GC, 58bp; standard DNA oligo. Make 100uM stock and 12.5uM working stock.

  - Set up a test PCR using 5 uL of ss cDNA sample and 9-12 cycles of PCR (based on experience with pool of 16 reactions, each starting with ~400ng total RNA)
  - Include a negative control (water) for each primer set
  - Make PCR Master Mix (4 rxns=2 libraries, +ve ctrl, -ve ctrl):

  - Add in order:

   | Reagent (for PCR master mix)	| 1 rxn	| 3 rxns
   | -------------------------------| ------| ------
   | Water, PCR-clean	| 14.3 uL	| 57.2 uL
   | 10X Pfu Ultra II Buffer	| 2.5 uL	| 10 uL
   | dNTP mix (10mM each)	| 0.7 uL	| 2.8 uL
   | P5 primer (P5_RNATag, | 12.5 uM)	| 1 uL	| 4 uL
   | Total	| 18.5 uL	| 74 uL

  - Mix well
  - Aliquot 18.5 uL / sample into PCR tubes
  - Add 1 uL of appropriate P7 index primer to each well
  - Add 5 uL of ss cDNA from step 11, or water (for negative control)
  - Add 0.5 uL of Pfu Ultra II Polymerase.
  - Mix well and aliquot 8 ul into each of 3 tubes

Place each in a thermal cycler with cycling conditions:

  - start: 98°C, 3min
  - cycle: 9, 12, 15 cycles (for test PCR) 98°C, 30sec; 55°C, 30sec; 70°C, 30sec
  - end: 70°C, 2min; 4°C, hold

**MUST CONTINUE**


### 16.. Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - increase reaction to 40uL with sterile water
  - Add 1.5x reaction volume SPRI beads (60 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 10 uL 1x low TE (10 mM Tris, 0.1M EDTA)
  - QC test PCR amplification on Agilent DNA HS chip

  - **NOTE:** Based on test results change the cycle number, if necessary, and set up more reactions to provide enough material to send for sequencing. Library should have smooth profile 200-500nt long; visible single bands, or a “shoulder” of larger products, indicate PCR artefacts.


**PAUSE POINT**


### 17.. PCR for Sequencing library

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

  - Place each in a thermal cycler with the cycling conditions:

    - start: 98°C, 3min  
    - cycle: # determined from test PCR 98°C, 30sec; 55°C, 30sec; 70°C, 30sec
    - end: 70°C, 2min; 4°C, hold

**MUST CONTINUE**


### 18.. Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - Pool PCR reaction (50 uL)
  - Add 1.5x reaction volume SPRI beads (75 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 50 uL water and transfer to new tubes.
  - Final Cleanup (0.8x SPRI) to remove remaining PCR primers:

### 19.. Second Round Cleanup (1.5x SPRI) to remove reaction buffer and PCR primers:

  - Add 0.8x reaction volume SPRI beads (40 uL) to the sample in new tubes, and mix up/down 10x
  - Incubate at room temperature for 15min
  - Place on magnet for 5 min or until solution is clear
  - Pipette out and discard clear solution
  - Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH.
  - Repeat 80% EtOH wash, and let air dry for 3min
  - Elute off beads with 25 uL 1x low TE (10 mM Tris, 0.1M EDTA)

### 20.. Check quantity/quality on Tapestation.


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
