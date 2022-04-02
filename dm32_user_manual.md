:allow-uri-read:
:stylesheet: https://tech.swissmicros.com/User-Manuals/usermanuals.css
:linkcss:
:lang: en
:toc: left
:toclevels: 3
:doctype: book

:version: 1.00

:table-stripes: even
:chapter-label: 
:sectnums:
:sectnumlevels: 4
:source-highlighter: coderay
:icons: font
:experimental:
:imagesdir: img/dm32_user_manual

// Our variables
:incdir:   ./
:platform:   DM32
:pgmname:    DM32
:webdir:     dm32
:fw:         1.52
// Entities of comma and plus chars for use in kbd: macros
:ll: &#44;
:pl: &#43;

:title-page: DM32 User Manual
= DM32 User Manual
SwissMicros GmbH
Copyright © 2021 – {localyear} • v{version} • {docdate} • (FW v{fw})


== About this User Manual

This user manual refers to special features of {platform}. It also gives a general recap about how equations work on the calculator.

Text is formatted after the following conventions:

[cols=".^1,.^3",width="80%"]
|=============================================
| btn:[XEQ]                                             | calculator keys are referenced as a black rectangle with the text as it is printed on their top
| image:orange_btn.svg[Orange Shift,24,24]              | the orange shift-key, also known as left-shift or LS, is referenced by an orange rectangle
| image:blue_btn.svg[Blue Shift,24,24]                  | the blue shift-key, also known as right-shift or RS, is referenced by a blue rectangle
| image:blue_btn.svg[Blue Shift,24,24]  btn:[STO] [EQN] | shifted function calls are depicted entirely, showing the shift button and key top label followed by the shifted-function name as it appears on the calculator face
                                                          between square brackets
| kbd:[INVALID (i)] kbd:[EQN] kbd:[Cn{ll}r]             | on a grey background are shown messages as they appear on the LCD, annunciators and on-screen menu functions to select using the top-row keys
| `/config.txt`                                         | paths and filenames, program listings and equations are shown in monospace fonts on a non-white background
|                                                       | 
|=============================================


== General information

=== Hardware specifications

[options="header",cols="1,2",width="80%"]
|=============================================
|Specification            | Details
| Construction            | Case made from stainless steel, matte black Physical Vapour Deposition (PVD) coated and laser engraved
| Software                | Custom software running on SwissMicros Operating System (DMCP)
| Floating point standard | IEEE 754-2008, 128-bit floating point precision implementation with 128-bit transcendental function support
| ISO conformity          | ISO/IEC TR 24732
| Processor               | Ultra low power ARM Cortex-M4F 80 MHz
| Flash memory            | 32 MBit external flash
| Display type            | Monochromatic ultra high contrast (14:1) transflective memory LCD display
| Display resolution      | 400 × 240 px
| Display active area     | 58.8 × 35.28 mm
| Display dot pitch       | 147 × 147 µm
| Connectivity (PC)       | USB-Micro-B port, connects as USB mass storage device
| Connectivity (IR)       | IR Transmitter compatible with the original HP-82240A/B printer
| Battery type            | 1 × CR2032 lithium coin cell, 3.0 volts^[1]^
| Battery life            | Up to 3 years
| Sound                   | 4 kHz resonance frequency Piezo-electric buzzer
| Size                    | 77 × 144 × 12 mm
| Weight                  | 180 g
| Warranty                | 5 years
|=============================================


NOTE: [1] The battery isn't rechargeable. See <<battery,Changing the battery>> chapter below for battery replacement and further info.

== Equations

=== Equations in a nutshell

The DM32 allows for writing, storing and editing stored equations, which can then be either:

* evaluated
* solved
* integrated

Here is a standard course of action to deal with equations on the DM32:

Go to Equation mode and view the list of stored equations:: Press image:blue_btn.svg[Blue Shift,24,24] btn:[STO] [EQN]. You can browse the equations list by using <<arrows,arrow keys>>. The equation displayed at the
bottom of the display is the one being presently selected.

Write an equation:: Simply start keying in numbers and letters. The equation entry mode is invoked and a new equation is automatically added to the list. When the equation is entirely keyed in, press btn:[ENTER]
and it is stored in the list immediately.

Show an equation’s checksum and length in bytes:: Navigate the list to the desired equation and press image:blue_btn.svg[Blue Shift,24,24] btn:[ENTER] [SHOW]. Note that this requires the equation entry mode to be off.
Mostly useful to make sure manually-entered examples have been copied without mistakes.

Edit an existing equation:: Find the equation from the list and press btn:[←]. This puts the calculator in equation entry mode and turns on the cursor at the right end of the equation. If the equation is larger than the screen can show, the display will be moved to the end of the equation. From here you can add or delete parts of the equation.
NOTE: The cursor can only act from the end of the equation, i.e. it’s not possible to move it to the middle of the equation to insert or delete elements from there.

Delete an equation:: Find the equation from the list and press image:orange_btn.svg[Blue Shift,24,24] btn:[←] [CLEAR]. The equation is immediately deleted. This cannot be undone.

Evaluate an equation:: Find the equation from the list and press btn:[ENTER]. Note that btn:[XEQ] can also be used to evaluate an equation, although it will behave somewhat differently if the
<<eqn_types,type of the equation>> is an _assignment_. See More about <<eqn_evaluate,evaluating equations>> below.

Solve an equation:: Find the equation from the list and press image:blue_btn.svg[Blue Shift,24,24] btn:[7] (SOLVE). The prompt asks for the unknown variable to be solved for.
Press the corresponding letter key (no need to press btn:[RCL] beforehand). The display automatically proceeds and prompts for the values of each known variable in the equation.
For each known variable, key in the desired value and proceed to the next known variable by pressing btn:[R/S]. Solving starts automatically after the last known has been entered. The display shows message kbd:[SOLVING].
When a root has been found, the value and name of the variable being solved for is shown.

Integrate an equation:: TBW


=== Equations in more detail

[[eqn_types]]
==== Equation types

There are three types of equations:

Equality:: Equation contains symbol “=” and the left side of the equation contains more than one variable. Example:
----
A + B² = C³
----
Assignment:: Equation contains symbol “=” and the left side of the equation contains only one variable. Example:
----
A = W × L
----
Expression:: Equation contains no “=” symbol. Example:
----
√W + 4
----

Equations evaluate differently according to their type, but it can be typically said that solving for an unknown variable requires equality- or assignment-type equations, whereas integration uses
expression-type equations.

[[eqn_view]]
==== Viewing/selecting equations

Put the calculator in equation mode with image:blue_btn.svg[Blue Shift,24,24] btn:[STO] (EQN). Annunciator kbd:[EQN] appears at the top of the display to indicate the present mode.
The list shows all stored equations, with the one at the bottom of the display being the one currently selected.

Browse stored equations using the <<arrows,arrow keys>>. The list begins with the kbd:[EQN LIST TOP] marker, which is the only message showing if no equation is presently stored.
The equations list _wraps around_, i.e. browsing up past the kbd:[EQN LIST TOP] marker jumps to the end of the list and, conversely, browsing down past the last equation in the list jumps back
to the kbd:[EQN LIST TOP] marker.

Only the first 12 characters of an equation are shown. If an equation is too long to be displayed in its entirety, special annunciators appear at the bottom of the display, enabling the use of keys btn:[F1]
and btn:[F6] to move the display to the left and right, respectively (TBC).

==== Writing equations

To write an equation, the calculator must be out of any special mode (i.e. have the stack displayed). Press image:blue_btn.svg[Blue Shift,24,24] btn:[STO] (EQN) and start writing the equation. The current display line is replaced by the
new equation being written without modifying the other equations in any way. Errors can be corrected by pressing btn:[←]. Equation entry is terminated by pressing btn:[ENTER]. The equation is immediately saved into the equations
list, directly after the one that was displayed before entering the new one. Pressing btn:[C] also saves the equation into the list but also exits equation mode.

Equations may contain variables, numbers, functions and parentheses. The length of an equation is limited only by available memory.

===== Variables in equations

Any calculator variable can be entered into an equation, as many times as necessary. To enter a variable, press btn:[RCL] _[variable]_ or btn:[STO] _[variable]_. When btn:[RCL] or btn:[STO] is pressed, annunciator kbd:[A..Z]
is lit to indicate that the next key press will invoke a letter. While the annunciator is lit, pressing image:orange_btn.svg[Orange Shift,24,24] will switch the keypad to lowercase, turning the annunciator to kbd:[a..z] TBC.

===== Numbers in equations

Any valid number can be entered in an equation, there are 2 conditions:

- fractions can't be used
- numbers have to be in base 10

To write negative numbers, key in the digits first and then press btn:[+/-].

===== Functions in equations

The general format of expression for equations is algebraic.

Infix functions:: are placed between the arguments. That is, the equivalent of RPN's kbd:[5 2 {pl}] must be written kbd:[5 {pl} 2].
Prefix functions:: can have one or two arguments:
One argument::: Key in the function, for instance btn:[COS]. The calculator insterts the prefix kbd:[COS(] and expects the argument. To terminate argument entry, close the function parenthesis
with image:blue_btn.svg[Blue Shift,24,24] btn:[E] [)].
Two arguments::: Method is the same as above, and to separate arguments, use btn:[R/S] [SPACE]. For example, to insert an expression using the combinatorial _Cn,r_
function
** press image:blue_btn.svg[Blue Shift,24,24] btn:[e^x^] [PROB] kbd:[Cn{ll}r],
** enter the first argument (total number of items),
** separate the two arguments with btn:[R/S] [SPACE],
** enter the second argument (number of items in combination),
** terminate arguments entry with image:blue_btn.svg[Blue Shift,24,24] btn:[E] [)].

Here is a table of all functions available for equations:

[options="header",cols="1,1,1,1",width="80%"]
|===
|infix functions
|prefix functions
|
|statistical and other

|
|1-argument
|2-argument
|

|+ – × ÷ ^
|LN LOG EXP ALOG SQ SQRT INV IP FP RND ABS x! SIN COS TAN ASIN ACOS ATAN SINH COSH TANH ASINH ACOSH ATANH →DEG →RAD →HR →HMS →KG →LB →°C →°F →CM →IN →L →GAL
|%CHG XROOT Cn,r Pn,r
|all means, sums and standard deviations

RANDOM π 

|
|
|
|
|===


==== Editing equations

TBW

==== Deleting equations

TBW

[[eqn_evaluate]]
==== Evaluating equations

To evaluate an equation, there are two options:

* pressing btn:[XEQ] will always return the value of the equation; to achive this for equality- and assignment-type equations, XEQ transforms the equation into an expression by replacing
the "=" (equal) sign with a "–" (minus) symbol and evaluates that expression;
* pressing btn:[ENTER] acts the same way except for assignment-type equations, for which it does two things
** return the value of the expression on the right side of the equal sign only,
** store this value in the variable.

[options="header",cols="1,^2,^2,^2",width="80%"]
|===
|equation type
|example
|result with btn:[ENTER]
|result with btn:[XEQ]

|equality
|A + B² = C³
2.+|A + B² – C³

|assignment
|A = W × L
|W × L (result stored in var A)
|A – W × L

|expression
|√W + 4
2.+|√W + 4

|
|
|
|
|===

When the calculator prompts for the value of each variable in the equation, for each prompt:

* if the value is correct, press btn:[R/S] right away
* otherwise, key in the desired value and terminate with key btn:[R/S]

The result is returned to the x-register (register LASTx is left untouched).

==== Solving equations

To solve an equation:

* <<eqn_view,select it>> from the list,
* press image:blue_btn.svg[Blue Shift,24,24] btn:[7] [SOLVE],
* the display prompts for the unknown variable with message kbd:[SOLVE _],
* press the letter key for the unknown variable,
* the calculator then prompts for every known variable in the equation:
** if the value for the variable is correct, proceed to the next by pressing btn:[R/S],
** if not, then key in the desired value and proceed to the next variable by pressing btn:[R/S],
* when the last variable has been entered, the display flashes message kbd:[SOLVING] until the solution is found for the unknown variable.

The value found for the unknown is displayed using function VIEW and stored in the corresponding variable. The stack is filled with values emerging from the solution:

* x-register: contains the root
* y-register: contains the previous estimate before the solution was found
* z-register: contains the value of the equation at the root (which is zero if an exact solution has been found)


==== Integrating equations

TBW

== Improvements over legacy HP-32SII (TBC)

=== CPU

CPU speed is 24MHz when running on battery (due to limited battery current) and increases to 80MHz when the USB cable is connected.

=== Memory

==== Extended variable space
In addition to the original 27 variables A to Z and i, the DM32 has 25 memory registers ranging from a to z (lowercase alpha characters). To store/recall these lowercase variables, toggle to lowercase by pressing
image:orange_btn.svg[Orange Shift,24,24] while the kbd:[A..Z] annunciator is lit (after pressing btn:[STO] or btn:[RCL]). The annunciator changes to kbd:[a..z]. The mode is retained for the next variable calls until toggled again.

=== Programming

==== Extended labels

In addition to the original 27 global programming labels A to Z, the DM32 has 26 labels ranging from a to z (lowercase alpha characters). To invoke these lowercase labels, toggle to lowercase by pressing
image:orange_btn.svg[Orange Shift,24,24] while the kbd:[A..Z] annunciator is lit (after pressing image:orange_btn.svg[Orange Shift,24,24] btn:[+] [LBL]). The annunciator changes to kbd:[a..z]. The mode is retained for the next label calls until toggled again.

==== Local labels

Programs on the DM32 can use 10 local labels named numerically from 0 to 9. Example:

----
L001 LBL L
L002 1.01
L003 STO Z
-- 7 LBL 7
L004 ISG Z
L005 GTO 7
L006 RTN
----

For this loop, using local label kbd:[7] saves a global alpha label for use as a different program's name.

To use a local label in a program, go to PRGM mode by pressing image:orange_btn.svg[Orange Shift,24,24] btn:[R/S] (PRGM), press either image:orange_btn.svg[Orange Shift,24,24] btn:[+] [LBL] to insert a label or image:orange_btn.svg[Orange Shift,24,24] btn:[XEQ] [GTO] to instert a GTO instruction and:

- press image:blue_btn.svg[Blue Shift,24,24] to toggle the alpha kbd:[A..Z]/kbd:[a..z] annunciator to digit annunciatior kbd:[0..9]
- key in the digit corresponding to the label number desired
- at this point, pressing a non-number key has no effect
- at this point, pressing image:blue_btn.svg[Blue Shift,24,24] or image:orange_btn.svg[Orange Shift,24,24] toggles the digit annunciatior kbd:[0..9] back to alpha kbd:[A..Z]/kbd:[a..z] annunciator
- pressing btn:[C] cancels input of label or GTO instruction

WARNING: As the name implies, the program only looks for a local label within the global label it is invoked in. Local labels inside other global labels are ignored.

==== Additional subroutine nesting depth

A program can call another while running by using btn:[XEQ] [label]. The called program can itself call another, which can call another... Then, at every RTN instruction, the program pointer pops back to the line following
the XEQ function in the parent program. This is called subroutine nesting. The allowed nesting depth was originally 8, it is now 16.

=== Local variables

TBW

=== F-Keys

DM32 has an additional row of keys at the top of the keypad, right under the display. They have no printed name but are designated from left to right as btn:[F1] to btn:[F6]. 

image::dia_dm32_fkeys.png[DM32 F-keys,400,600,pdfwidth=50%,scaledwidth=50%]

They serve various purposes depending on the current mode of the calculator. They are shortcuts to calculator functions, useful mostly to reach functions which require several keypresses
because they are buried down in a menu. The table below shows what the F-key shortcuts do by default.

[options="header",cols="1,1,1,1,1,1,1",width="100%"]
|===
|current mode       | btn:[F1]                  | btn:[F2]                  | btn:[F3]                  | btn:[F4]                  | btn:[F5]                  | btn:[F6]                  
| normal            | HELP                      | CLEAR menu                | SOLVE                     | ▼                         | ▲                         | clear stack               
| program           |                           | LBL                       | GTO                       | ▼                         | ▲                         | RTN                       
| equation view     | kbd:[←]                   |                           |                           | ▼                         | ▲                         | kbd:[→]                   
| DM32 menus        | back to top               |                           |                           | move down to next item    | move up to previous item  |                           
|                   |                           |                           |                           |                           |                           |                           
|===

Custom shortcuts can be assigned to F-Keys. Please read below. (Procedure TBW)

==== Custom F-Key assignments (proposed)

===== Internal shortcuts structure

The functions fo F-Keys can be user-defined. Internal F-Key structure is organized like this:

* There are 3 shift layers
** unshifted [US]
** left-shifted [LS] (orange)
** right-shifted [RS] (blue)
* On top of that, there are 3 context layers:
** normal [N] (no annunciator)
** equation [EQN] (EQN annunciator lit, except when entering an equation in PRGM mode)
** program [PRGM] (PRGM annunciator lit)

There are some exceptions to what is assignable:

* the F1 key in normal unshifted layer can't be modified and always calls the onboard Help file
* the F1 key in EQN unshifted layer can't be modified and always activates equation scrolling to left (if annunciator lit, otherwise does nothing)
* the F6 key in EQN unshifted layer can't be modified and always activates equation scrolling to right (if annunciator lit, otherwise does nothing)
* + ?

===== Assignment mechanics

To assign a custom shortcut to a key, go to the releveant section of Settings and complete 4 steps:

1. designate one of context layers:
** normal [N]
** equation mode [EQN]
** program mode [PRGM]
2. designate one of shift layers:
** none or unshifted [US]
** orange or left-shift [LS]
** blue or right-shift [RS]
3. designate one of F-Keys:
** F1
** F2
** F3
** F4
** F5
** F6
4. assign a function:
** XEQ program label: A-Z and a-z
** key shortcut: any shifted-key function call (limited by what is possible in each mode; for instance, several functions aren't available in EQN mode, like the BASE menu or MODES)
** RCL or STO as function call + argument (the variable name)

===== Examples

If user needs key image:blue_btn.svg[Blue Shift,24,24] btn:[F3] to call function kbd:[FS?] in PRGM mode, then the path through the selection is:

1. PRGM layer
2. RS layer
3. F3
4. FS?

Which gives assignment code: PRGM-RS-F3-FS?

Other example: user needs key btn:[F2] to execute program label S in normal mode:

1. N layer
2. US layer
3. F2
4. XEQ S

Assignment code: N-US-F2-XEQ.S

Other example: user needs key btn:[F3] to recall variable p in normal mode:

1. N layer
2. US layer
3. F3
4. RCL p

Assignment code: N-US-F3-RCL.p

Other example: user needs key image:orange_btn.svg[Orange Shift,24,24] btn:[F5] to call function kbd:[Cn{ll}r] in EQN mode:

1. EQN layer
2. LS layer
3. F5
4. Cn,r

Assignment code: EQN-LS-F5-Cn,r

===== Assignment storage model (proposed)

The complete list of assignments could be represented as a text file in the following way, where XXX is replaced by command or variable names:

----
N-US-F2-XXX
N-US-F3-XXX
N-US-F4-XXX
N-US-F5-XXX
N-US-F6-XXX

N-LS-F1-XXX
N-LS-F2-XXX
N-LS-F3-XXX
N-LS-F4-XXX
N-LS-F5-XXX
N-LS-F6-XXX

N-RS-F1-XXX
N-RS-F2-XXX
N-RS-F3-XXX
N-RS-F4-XXX
N-RS-F5-XXX
N-RS-F6-XXX

EQN-US-F2-XXX
EQN-US-F3-XXX
EQN-US-F4-XXX
EQN-US-F5-XXX

EQN-LS-F1-XXX
EQN-LS-F2-XXX
EQN-LS-F3-XXX
EQN-LS-F4-XXX
EQN-LS-F5-XXX
EQN-LS-F6-XXX

EQN-RS-F1-XXX
EQN-RS-F2-XXX
EQN-RS-F3-XXX
EQN-RS-F4-XXX
EQN-RS-F5-XXX
EQN-RS-F6-XXX

PRGM-US-F1-XXX
PRGM-US-F2-XXX
PRGM-US-F3-XXX
PRGM-US-F4-XXX
PRGM-US-F5-XXX
PRGM-US-F6-XXX

PRGM-LS-F1-XXX
PRGM-LS-F2-XXX
PRGM-LS-F3-XXX
PRGM-LS-F4-XXX
PRGM-LS-F5-XXX
PRGM-LS-F6-XXX

PRGM-RS-F1-XXX
PRGM-RS-F2-XXX
PRGM-RS-F3-XXX
PRGM-RS-F4-XXX
PRGM-RS-F5-XXX
PRGM-RS-F6-XXX
----

[[arrows]]
=== About arrow keys

Up- and down-arrow functions on the original calculator were selected using shift functions (namely, image:orange_btn.svg[Orange Shift,24,24] btn:[7] [▼] and 
image:orange_btn.svg[Orange Shift,24,24] btn:[8] [▲]). While this original functionality is preserved, the DM32 facilitates its use via non-shift options:

* in default configuration, F-Key shortcuts are so that keys btn:[F4] + btn:[F5] perform the same function
* btn:[–] +  btn:[+] perform the same function in the DM32 menus

=== USB connectivity/flash disk (TBW)

==== Micro-USB B connector

The USB port on the top edge of the calculator transports both power and data:

- Power: when connected to an USB port delivering power, the CPU runs at 80 mHz instead of 24 mHz when on battery power.
- Data: connecting to a computer allows for moving data from and to the calculator. See <<usb_disk,Activate USB Disk>> for more info.

WARNING: This USB connection does not recharge the battery. The battery inside the calculator is not rechargeable. See <<battery,Changing the battery>> for more detail.

image::dia_dm32_usb.png[DM32 Micro-USB B,400,600,pdfwidth=50%,scaledwidth=50%]

[[menus]]
== DM32 Menus

To display the DM32 menus, press image:orange_btn.svg[Orange Shift,24,24] btn:[C] (SETUP)

A list of menus appears:

1. <<file_menu,File>> 
2. <<settings_menu,Settings>>
3. <<usb_disk,Activate USB Disk>>
4. <<system_menu,System>>
5. <<about_menu,About>>

=== Menus navigation

Menu items can be selected in two ways:

* Using arrow keys + Enter:
** highlight menu item using btn:[F2] and btn:[F3] (TBC) keys to move the pointer up and down, respectively,
** enter highlighted menu item by pressing btn:[ENTER].
* Using direct selection:
** press the calculator key matching the number in front of the desired menu item.

Every selection advances the display one step down the menus hierarchy (or toggles a checkbox). To go back up a step, press btn:[C] or btn:[←] key. When at topmost level, either of these keys exit the the menus.


[[file_menu]]
=== File

[[save_load_state]]
==== Save/Load State
It is possible to Save/Load complete calculator state.

Calculator state contains:

* complete stack XYZT and LASTx
* memory registers
* flag states
* program(s)
* active MODES and DISP selections (like RAD, FIX 6, etc)
* (not implemented yet) equations

Default save/load directory is `/STATE`. Last saved/loaded file is taken as _active_ and is re-loaded after calculator RESET (either RESET button press or firmware update).

* Load State: loads calculator state from selected state file and makes it active.
* Save State: saves current calculator state to specified file and makes it active.
* Load Clean State: completely clears calculator state. No active state file is selected.

[[settings_menu]]
=== Settings

Accessible from Settings menu (Setup Menu -> 2. Settings)

1. Set Time: allows to set time and time format.
2. Set Date: allows to set date and date format.
3. (_) Full Font: toggles between segmented (which emulates gaps between LCD segments) and full font.

Date/Time format and font settings are automatically saved into `/config.txt` on change. Therefore, user settings should be preserved after calculator RESET.

[[usb_disk]]
=== Activate USB Disk

Used to copy files from/to a host computer — e.g. backup/restore the calculator state files from `/STATE/` directory.

- connect the calculator to a computer using a USB cable,
- the DM32's flash disk should be visible on the computer,
- read and/or write files,
- 'eject device' on the host machine,
- calculator should automatically end USB disk mode automatically if correctly ejected by OS. You can end USB disk mode by pressing btn:[C] on the calculator but be sure all data are flushed to disk first.

WARNING: The last two points 'eject device' and 'press btn:[C] on calculator' (if it doesn't end automatically) are important to avoid unsaved data and possible FAT disk corruption!

[[system_menu]]
=== System Menu

[[firmware_update]]
==== Firmware update

Typical firmware file name looks like

----
DMCP_flash_3.24_DM32S-1.53.bin
----

where

----
DMCP   - OS name
flash  - target area for flashing (CPU flash)
3.24   - version of OS
DM32S  - program name (preloaded to OS)
{fw}   - program version
----

[[about_menu]]
=== About

== Appendix

include::vertical_platform_batt_change.adoc[]

== Manual dev notes

Mentions "TBC" in the above text means "To Be Confirmed" and relate to functions which will depend on further development.

Mentions "TBW" in the above text means "To Be Written".

HP-32SII had no output capability: remove the mention of IR in the specs?

HP-32SII had no buzzer: remove the mention in the specs?

Can the DM32 have more than 299 program lines? If yes, how are lines numbered in PRGM mode? (i.e. A256 instead of A,56)?

Can the DM32 have more than 999 program lines? If yes, are there 4 digit places permanently displayed in line numbers in PRGM mode? (i.e. A0256 instead of A256)?

Extended UI mechanics for review:

- custom shortcuts using shifted F-keys
- toggling to lowercase alphabet for extended labels and variables
- toggling to digit entry for local labels and variables

Equations display: will the display be able to show 4 equations from the list? If yes, then it must be clear which one is currently _selected_ (the one appearing at bottom "x-register", I would say)