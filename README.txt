
======================================================================================
miSCellaneous - a library of SuperCollider extensions (c) 2009-2016 Daniel Mayer 
======================================================================================

Version 0.14a - as GUI redirect has been deprecated with SC 3.7, a-branch versions of 
miSCellaneous (which have started with 0.10) are necessary for SC 3.7 onwards, 
though they are also working with 3.5 and 3.6 using Qt GUI only. 
For SC versions from 3.5 up to 3.6.x you can use 0.14b, which still gives the option of 
switching between Qt, SwingOSC and Cocoa GUI.

By version 0.14 miSCellaneous contains these class and help files 
(HTML and new SCDoc system):


1.)	VarGui:  a slider / player gui to set envir variables and synth controllers and 
	play synths, event patterns and tasks, see also "VarGui shortcut builds".
	"HS with VarGui", a specific tutorial about the combination of HS family and VarGui.

2.)	General tutorials: "Event patterns and LFOs" contains an overview of
	related LFO-control setups with event patterns. "Event patterns and Functions" 
	is treating requirements of the control of EventStreamPlayers with VarGui.
	"Event patterns and array args" focusses on passing arrays to synths with patterns.
	"enum" is a general enumeration method suited for many combinatorial problems such as 
	listing subsets, partitions of integers, searching for paths within graphs etc.

3.)	"PLx suite", dynamic scope variants of common Pattern classes for convenient 
	replacement. Can be used for shorter writing of Pbinds to be played with VarGui 
	and / or live coding, see "PLx and live coding with Strings". 
	
	PLbindef and PLbindefPar as subclasses of Pdef allow replacement of 
	key streams
	in shortcut pseudomethod syntax.

4.)	PSx stream patterns, Pattern variants that have a state and can remember their 
	last values. Can be used for recording streams and event streams (PS),
	data sharing between event streams (PSdup), comfortable defining of subpatterns
	with counted embedding, defining of recursive (event) sequences (PSrecur) and
	building loops on given Patterns/Streams with a variety of options, also for 
	live interaction (PSrecur).

5.)	Event pattern classes for use with effects: PbindFx can handle arbitrary effect
	graphs per event, PmonoPar and PpolyPar follow the Pmono paradigm.
	
6.)	Further Pattern classes (PlaceAll, Pshufn, PsymNilSafe).

7.)	"Buffer Granulation", a tutorial covering different approaches of implementing
	this synthesis method in SC (server versus language control, mixed forms),
	examples with VarGui, language-driven control with PLx suite patterns.
	
8.)	A family of classes for the use of synth values in Pbind-like objects.
	Take Working with HS and HSpar as a starting point, see also
	HS, PHS, PHSuse, HSpar, PHSpar, PHSparUse, PHSplayer, PHSparPlayer, PHSusePlayer

9.)	EventShortcuts, a class for user-defined keywords for events and event patterns.
	The tutorial "Other event and pattern shortcuts" collects some further abbreviations,
	e.g. functional reference within events and event patterns, similar to Pkey.

10.) An implementation of Xenakis' Sieves as class and pattern family, see
	
	"Sieves and Psieve patterns" for an overview and examples. 


Many of the examples here are using patterns, resp. event patterns but do not cover 
their basic concepts. For a detailled description of SC's sequencing capabilities see 
James Harkins' Practical Guide to Patterns (PG_01_Introduction), the tutorial 
Streams-Patterns-Events (1-7) and the Pattern help files 
(Pattern, Pbind and the type-specific ones).

VarGui handles namespace separation by using different Environments.
So a gui for control of parametrized families of different types of objects can be 
built on the fly (e.g. a number of EventStreamPlayers from a single Pbind definition 
with snippets of functional code, a number of Function plots from a single 
parametric function definition etc.).
See Environment and Event helpfiles for the underlying concepts and 
"Event patterns and Functions" and "PLx suite" for their application to 
event patterns resp. EventStreamPlayers.


Requirements

At least SuperCollider version 3.5, though with 3.5 and 3.6 you'd have
to use Qt GUI kit, which is the only option with and after 3.7. 
In SC 3.7 Cocoa and SwingOSC aren't supported anymore which required some
changes in miSCellaneous lib. For backward compatibility down to SC 3.5
and use with SwingOSC or Cocoa see miSCellaneous version 0.14b.

For using VarGui with EZSmoothSlider and EZRoundSlider you would need to 
install Wouter Snoei's wslib Quark, one buffer granulation
example using Wavesets depends on Alberto de Campo's Wavesets Quark. 

I tested examples on SC versions 3.5 - 3.8, 
on OS 10.5 - 10.8, Ubuntu 12.04 and Windows 7, though not every 
platform / OS version / SC version combination.

If you work with 3.5.x I'd suggest taking a SC version >= 3.5.3.
There have been some changes in SCDoc (especially from 3.5.1 to 3.5.2)
due to which wrong renderings (broken links) of newer SCDoc help files 
can happen with elder SC versions in some rare cases.
Reciprocally elder versions of miSCellaneous SCDoc help files 
- due to formerly tolerated syntax inaccuracies - 
might not be rendered correctly or at all in newer versions of SC.


Installation

Copy the miSCellaneous folder into the Extensions folder and recompile 
the class library or (re-)start SC. If the Extensions folder doesn't exist 
you'd probably have to create it yourself. Check SC help for platform-specific 
conventions (or changes) of extension places.

Typical user-specific extension directories:

OSX:	~/Library/Application Support/SuperCollider/Extensions/
Linux:	~/.local/share/SuperCollider/Extensions/

Typical system-wide extension directories:

OSX:	/Library/Application Support/SuperCollider/Extensions/
Linux:	/usr/share/SuperCollider/Extensions/

You can check Extension directories with

Platform.userExtensionDir;
Platform.systemExtensionDir;

On Windows see the README file of SC for the recommended extensions path.
On Windows and OSX you might have to make the concerned folders visible,
if they aren't already. The miSCellaneous folder should be placed directly
into the Extensions folder, not into a subfolder. This can easily happen 
with dezipping and in this case examples with buffers won't work because of a wrong path.

Buffer Granulation tutorial examples using the included soundfile 
assume an install in the user extension directory, otherwise you'd just have to 
replace userExtensionDir by systemExtensionDir in the concerned load paths.

If you replace an other version of miSCellaneous 
do the following before starting SCDoc:

SCDoc.cleanState(true)  // for SC version 3.5.0 - 3.5.1
SCDoc.indexAllDocuments(true)  // for SC >= version 3.5.2


License

miSCellaneous is distributed under the GNU Public License in accordance 
with SuperCollider. You should have received a copy of the 
GNU General Public License along with this program; 
if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.


Contact

Email:	daniel-mayer@email.de
URL:	www.daniel-mayer.at


Credits

Many thanks to James McCartney for developing SuperCollider, 
Alberto de Campo for showing me its capabilities,
Wouter Snoei for his nice slider classes in wslib and 
the whole community for contributions and hints !


=====================================================================================


History


v0.14		2016-08-25

	.) Sieves and Psieve patterns, an implementation of Xenakis' sieves
	.) PLbindef / PLbindefPar: replacement of key streams in pseudomethod syntax 
	.) Tutorial: PLx and live coding with Strings
	.) PsymNilSafe, method symplay: avoid hangs with nil input
	.) EventShortcuts: reworking of replacement, new method eventShortcuts
	.) PbindFx: reworking of bus match check
	.) Minor fixes (help files, typos)	


v0.13		2015-10-28

	.) PbindFx:
	   Event pattern class for effect handling on per-event base
	.) Minor fixes (help files, typos)	


v0.12		2015-05-03

	.) PmonoPar, PpolyPar:
	   Event pattern classes for parallel setting streams and effect handling
	.) PSloop: Pattern to derive loops from a given Pattern
	.) Reworked replacing options of PL list patterns: cutItems arg.
	.) PLn: PLx Pattern for replacing with protecting periods
	.) Added PLxrand, PLx version of Pxrand
	.) Changed implementations of PStream (PS) and PSrecur,
	   now the MemoRoutine isn't instantiated before embedding,
	   this enables use of PSx patterns with VarGui
	.) Fixed a bug in PL list patterns (PL_PproxyNth) that caused too early
	   replacements in certain cases
	.) Added method bufSeq for PStream
	.) Added missing help file of PLtuple
	.) Minor fixes (help files, typos)	


v0.11		2015-02-02

	.) Tutorial: Event patterns and array args
	

v0.10		2014-10-06

	.) Split into branches 0.10a (3.7 onwards) and 0.10b (from 3.4 up to 3.6.x),
	   with SC 3.7 SwingOSC and Cocoa aren't supported anymore.
	.) Class EventShortcuts and tutorial "Other event and pattern shortcuts"


v0.9		2014-02-18

	.) PSx stream patterns (PS, PSdup, PSrecur), based on class MemoRoutine
	.) Buffer Granulation Tutorial: new examples (1c - 1e, 3d)
	.) VarGui save dialog fix (was broken with 3.6)	
	.) Minor fixes (help files, typos)	


v0.8		2013-05-05

	.) Enumeration tutorial: method enum	


v0.7.1		2013-04-28

	.) Fix in PLseries and PLgeom	


v0.7		2012-08-31

	.) Buffer Granulation tutorial file	
	.) VarGui
		.) Support of wslib slider classes EZSmoothSlider and EZRoundSlider
		.) Color grouping options for synth and envir variable control
		.) Adapting EZSlider to ControlSpec step size 
		  (fixes certain rounding and jitter issues)
	.) Multiple slider handling with modifier keys: fixes and cleanup


v0.6		2012-05-19

	.) PLx dynamic scope pattern suite	
		.) Implementation of a number of common Patterns as PLx classes
		.) Changing examples in some previous help files accordingly
	.) Pstream, PlaceAll, Pshufn


v0.5		2012-03-18

	.) VarGui shortcut build methods	
		.) Use of SynthDef metadata and global ControlSpecs
	.) Automatic Pbind generation
	.) Minor fixes in VarGui init procedure


v0.4		2011-12-27

	.) VarGui support for HS family classes	
	.) VarGui takes addAction as slider hook	
	.) Linux check (tested on Ubuntu):
		.) Fixed system time issue in HS family
		.) Specified VarGui appearance default parameters for platform and gui kit
	.) Supports SCDoc, the new SC help system
	.) Added general (2) and specific (1) tutorial files 
	.) Play methods of PHSx and PHSxPlayer now also take numbers as quant arg
	.) Minor fixes in HS family


v0.4beta	2011-08-18

	.) VarGui relaunch: 
		.) Player section for Synths, EventStreamPlayers and Tasks 
		.) Different player modes
		.) Button colors and background colors reflecting playing states 
		.) Handling groups of players and sliders with modifier keys
		.) Player action by mouse down or up (currently cocoa only)
		.) Variables can be set in different environments
		.) Latency setting, global and for synth player message bundling
		.) GUI appearance customization in size, arrangement and color
		.) Many other changes, e.g. arg conventions 
	.) Private extension methods get prefix miSC_


v0.3		2010-10-21

	.) VarGui:
		.) Arrayed synth control supported
		.) Slider update methods added
		.) Save dialog now uses unified gui class Dialog	
	.) Again compiling with SC 3.3 and 3.3.1


v0.2		2010-09-18

	.) Minor adaptions to SC 3.4
	.) Fixed time shifting issue


v0.1		2009-11-24


=====================================================================================


	