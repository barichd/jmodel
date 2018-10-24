# Jmol/JSmol projects

Note: JSmol is a new version of Jmol that can run without Java.  Jmol and JSmol are essentially the same program, and these names are sometimes used interchangeably.

From Biomolecules at Kenyon 

Report corrections or questions to Daniel Barich. 

## Edit project using BlueGriffon.

1. Open the run dialog, either by choosing Start -> Run or by holding down the Windows logo key and pressing R.  Then type the following address:

```
\\parana.kenyon.edu\bio-tutorials
```

   NOTE: On a Mac computer the slashes go in the opposite orientation. 

2. When the folder opens make a copy of the 'jsmol template' folder.  One way to do so is to right-click on it, click 'copy', left-click within the same folder window (e.g. within the bio-tutorial folder), and click 'paste'. A copy of the folder, called something like "jsmol - template- (Copy) ", should appear. 

3. Rename it immediately with your own molecule name.  Keep filenames short, and avoid empty spaces; use underscores instead. 

The Model consists of:

* index.htm: This file contains both the JavaScript code to display the molecule and the text, which you will need to change to your own names, molecule, references, etc.
* 3gap.pdb: This is the molecule that is loaded when the tutorial is first opened.
* 1cgp.pdb: This file contains the DNA complex that is loaded later in the tutorial.

4. Open a browser and type in the URL of your copy of the model tutorial. It will be of the form:
```
https://internal.kenyon.edu/biology/tutorials/MyMolecule/index.htm. Note: Always open JSmol tutorials using the web address (with https:). The tutorials will not work if you simply drag the filename into the browser.
```
5. Push the button after the first sentence under II. General Structure. What does it do? It shows cartoons and colors the peptide chains. We are doing this step now because later we will be looking at the code for it, but we will have replaced the structure with your own at that point. 
6. Find your structure in RCSB protein data bank. There are often many different structures for the same protein. Make sure you know what you're getting (you can click on the pubmed link to find the paper where this structure was originally reported.) Download the correct pdb as a pdb file (text). The file extension needs to be .pdb 
7. Copy your PDB file into your own model folder. 
Never change the name of the PDB file, as its filename provides the reference for instant access in the Protein Databank. Your PDB file should be at the same level as "3gap.pdb" and "1cgp.pdb".Usually when you initial download the pdb file it goes into a downloads folder. Move into your folder. 
8. Open BlueGriffon (either from the desktop or the Start menu). 
The departmental laptops have BlueGriffon installed. If your PC does not have BlueGriffon, download it here.
9. Open \\parana.kenyon.edu\bio-tutorials\MyMolecule\ index.htm in BlueGriffon,(do this by clicking on open file, then typing \\parana.kenyon.edu\bio-tutorials into the dialog box then clicking on your molecule, then the index file, then open.
10. Click on the Source button near the bottom of the screen.Scroll to the line that starts with var loadScript (should be about line 58).
11. Replace the "pdb" filename in load 3gap.pdb with the name of your own pdb file. **Be sure capitalization is consistent with your own filename.
12. At around lines 109-112 change the name of the molecule and the authors. This can also be changed on the BlueGriffon editor screen instead of in the source code. 
13. Save the tutorial in \\parana.kenyon.edu\bio-tutorials\MyMolecule. Note if the file is saved as an htm or html file.
14. If not already up, open your tutorial in a browser window (https://internal.kenyon.edu/biology/tutorials/MyMolecule/index.htm) to see how your changes affect the page. You will need to wait a moment for your changes to take effect, after which you can press Control + Shift + R to reload the page and override the cache. You can also try refreshing the browser multiple times. Chrome worked as a browser on the departmental laptops. I've also had Firefox work. 
Editing the text and buttons.
1. Find the following code which should start at about line 156:
```html
<script language="JavaScript">
Jmol.jmolButton("select all; labels off; spacefill off; color cpk; wireframe off; ribbons off; cartoons off; backbone on; select protein; backbone off; cartoons on; select *a; color blue; select *b; color magenta;","");
</script> 
```
2. In the code above, blue text indicates code required for every button in the tutorial. Red text is script code, which will vary from one button to the next. The jmolButton command creates a button that, when clicked, will execute the script commands in the first pair of quotes. You'll need to figure out what commands in the list make what effects, and how to tailor them to your own molecule. Be sure to separate these commands with semicolons (;), and do not press Enter between them.  
3. Command list for first button, with explanations
* `select all` - The entire molecule will be affected by subsequent commands.
* `labels off` - Turns off labels (in case another button turned them on).
* `spacefill off` Turns off spacefill.
* `color cpk` - Colors all atoms according to the CPK color scheme. (default)
* `wireframe off` - Turns off wireframe, in order to show other renderings.
* `ribbons off` - Turns off ribbons.
* `cartoons off` - Turns off cartoons.
* `backbone on` - Turns on backbone.
* `select protein` - Only protein atoms will be affected by subsequent commands. 
* `backbone off` - Turns off backbone (so it doesn't interfere with cartoon).
* `cartoons on` - Turns on cartoon rendering 
* `select *a` - Only chain a(*=all of it) will be affected from now on.
* `color blue` - Blue color will be applied (to chain a only).
* `select *b` - Only chain b will be affected.
* `color purple` - Purple will be applied(to chain b).

   Note: Begin each button's list of commands with select all followed by commands to turn on/off each of the possible renderings, as shown in the first eight commands of this example. This way, the reader of your tutorial will not have to click on each and every button in sequence. For ease of readability, after each select command, place the off commands in a group before the on commands, as in the example.

4. Edit the first button by changing "color blue" to "color red." Save file in BlueGriffon.

5. Reload the page, usually by pressing Control + Shift + R (Pressing Control + R may not work due to browser caching).

6. Press the button that you edited in BlueGriffon. What happens?

### Next Button

1. Push the second button.What does it do? 

2. Check it out in BlueGriffon. 

Command list for the second button (excluding the first eight commands, which are the same as above):

* `select protein` - Selects protein atoms
* `backbone off`
* `cartoons on`
* `color blue`
* `select cmp` - Selects cAMP (cyclic monophosphate) [Probably absent in your own pdb].
* `backbone off`
* `wireframe 0.6` - Sets wireframe width to 0.6 angstroms.
* `color lawngreen` 
* `select atomno=1652 or atomno=3325` - Select the atoms numbered 1652 and 3325
* `label cAMP` - Labels selected atoms "cAMP."
* `font label 31` - Set label font to 31 points.
* `select 130-139` - Selects residues 130-139 
* `color red`
* `select 140-209` - Select residues 140-209
* `color yellow`

### New Buttons

You can copy the above text wherever you want a new button. 

### More commands

For a reference of Jmol commands, go to JSmol's Interactive Scripting Documentation. To find out how to create check boxes, radio buttons, etc. using the <script> tag, see the Jmol JavaScript Object documentation.

### Adding reset buttons to your tutorial.

Go to the line (about line 151) which contains the following code:

```html
<script language="JavaScript">ResetProteinButton();</script>
```

This code creates a reset button that, when pressed, will reset the molecule view to its original state.  To insert a reset button anywhere in your tutorial, simply type or copy/paste this code (in the code window, not the design window) wherever you want the button to appear. The model tutorial has a reset button at the top of every numbered section, but this is not essential. If every button resets the appearance of the molecule before adding new effects, then it won't be necessary to reset the molecule. Note also that the model uses a JavaScript function to create a different reset button for the DNA. You can create as many different types of reset buttons as you want by creating JavaScript functions.

### The `moveTo` command.

The easiest way to set the location, orientation, and zoom level of a molecule in JSmol is to use the moveTo command, as follows:

```
moveTo [time in seconds] [rotation axis x y z] [rotation angle] [zoom%] [translate x y]
```

This command moves the molecule [rotation angle] degrees counterclockwise (to the left) about the specified rotation axis, sets the zoom level, and translates the molecule so that [zoom%] if it is visible. Positive values for the transform arguments move the molecule to the right for the x-axis and up for the y-axis, and negative values reverse the direction. The zoom and translate arguments are optional, but everything else is required, and you cannot skip an argument.

Whenever a JSmol molecule is displayed, you can generate a moveTo command that, when executed, will place the molecule in the current position and orientation. Move the mouse over the applet, click the right mouse button, and Select Console.  The console window will open, where you can type commands and execute them to see their effect immediately. Type show orientation and press Shift+Enter. The display at the top of the popup window should display a moveTo command. You can then copy this command to the clipboard (you may first need to click on editor) by selecting it with the mouse and pressing Ctrl+C. Now you can paste the command in a block of script commands in your tutorial. Note that the first number after the word moveTo is the number of seconds the molecule will take to move to the new position. Remember to set this number to 0 if you want the molecule to position itself instantly.

### Troubleshooting

If you run into any problems, please check the [Troubleshooting](http://biology.kenyon.edu/BMB/jmodel/troubleshooting.htm) page before asking for help.