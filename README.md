# Geneious wrapper plugin for Nextclade

[Geneious](https://www.geneious.com) wrapper plugin to run [Nextclade](https://clades.nextstrain.org/) for clade assignment, mutations calling and quality checks of SARS-CoV-2 genomes. The plugin accesses Nextclade’s latest data set used to assign clades to SARS-CoV-2 sequencing data. 

- Input: SARS-CoV-2 genome sequence(s). To run on multiple sequences, first create a sequence list in Geneious.
- Output: .txt report which is imported into Geneious

## System requirements
- Geneious 2021.1.1 or later (for older versions it may be possible to install the plugin from source)
- Python 3

## Mac or linux
1. Download `nextclade_linux_mac_x.x.gplugin`
2. In Geneious, go to 'Tools' --> 'Plugins' --> 'Install plugin from a gplugin file' and select the gplugin file and click 'Install'. The plugin should now appear under the 'Tools' menu.
3. When running the plugin the user will be prompted to enter the path to the folder where Nextclade is installed on the computer and the path to the folder where Nextclade’s output files should be located.

## Windows
1. Download `nextclade_windows_x.x.gplugin`
2. In Geneious, go to 'Tools' --> 'Plugins' --> 'Install plugin from a gplugin file' and select the gplugin file and click 'Install'. The plugin should now appear under the 'Tools' menu.
3. When running the plugin the user will be prompted to enter the path to the folder where Nextclade is installed on the computer and the path to the folder where Nextclade’s output files should be located.

---

## Installation from source

First install the [Geneious Wrapper Plugin Creator](https://www.geneious.com/api-developers/).

### Create wrapper plugin in Geneious
1. Go to 'File' --> 'Create/Edit Wrapper Plugin..'. Press '+New'
2. Step 1:
    - Fill in 'Plugin Name:' and 'Menu/Button Text:' of your choice.
    - 'Plugin Type:' select 'General Operation'.
    - 'Bundled Program Files (optional)'
   	 - Linux/mac: add the `nextclade_linux_mac.py` script under 'Linux' or 'Mac OSX' respectively.
   	 - Windows: add the `nextclade_win.bat` script under 'Windows' and the `nextclade_win.py` script under 'Additional Bundled Files'.
3. Step 2:
    - 'Sequence Type:' select 'Nucleotide only'.
    - 'Document Type:' select 'Unanaligned Sequences (1+)'.
    - 'Command Line'
   	    - Windows: '[inputFileNames] nextclade [otherOptions]'
   	    - Linux/Mac: '[inputFileNames] nextclade [otherOptions]’
    - Under 'Output' 'File Name:' fill in 'nextclade' and select 'Format:' 'Text file (plain)'
4. Step 3:
    Press 'Add' to add two user options (in this order):   
    - 'Command Line Switch': pathToNextclade, 'Option Label': Nextclade path  
    - 'Command Line Switch': pathToOutput, 'Option Label': Path for output files  
    Both 'Command Line Switch' and 'Option Label' should be filled in, but can be modified.


