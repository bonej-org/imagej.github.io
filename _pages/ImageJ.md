{{AboutMenu}}ImageJ is an open source Java image processing program inspired by [[NIH Image]]. It runs on any computer with a Java 1.8 or later virtual machine. [[Downloads|Downloadable distributions]] are available for Windows, Mac OS X and Linux. ImageJ has a strong, established user base, with thousands of [[plugins]] and [[macros]] for performing a wide variety of tasks.

== Flavors ==

There are a few different flavors of ImageJ with very similar names, and some confusion is inevitable. Below is a table which should help to clarify the purpose of each. For the historical context of these projects, see [[#History|History]] below.

{| class="wikitable"
|-
|
|'''Name'''
|'''Author/Maintainer(s)'''
|'''Description'''
|'''Initiated'''
|'''Status'''
|-
|[[File:Fiji-icon.png|64px]]
|[[Fiji]]
|[[Contributors|Fiji contributors]]
| 
'''F'''iji '''i'''s '''J'''ust '''I'''mageJ, with extras. It is a distribution of ImageJ with many plugins useful for scientific image analysis in fields such as life sciences. It is actively maintained, with updates released often.

We recommend Fiji as the preferred version of ImageJ.

|[[User:Schindelin#A_short_story_about_Fiji|Dec. 2007]]
|Active
|-
|[[File:imagej2-icon.png|64px]]
|[[ImageJ2]]<br>
ImageJDev
|[[Contributors|ImageJ developers]]
|A new version of ImageJ targeting scientific multidimensional image data. It is a complete rewrite of ImageJ, but includes [[ImageJ1]] with a compatibility layer, so that old-style plugins and macros can run the same as always. ImageJ2 provides several significant new features, such as an automatic [[updater]], and improved [[scripting]] capabilities.
|Dec. 2009
|Active
|-
|[[File:imagej1-icon.png|64px]]
|[[ImageJ1]]
|{{Person|Rasband}}
|A stable version of ImageJ which has been in development since 1997. It has a strong, established user base, with thousands of plugins and macros for performing a wide variety of tasks.
|1997
|Active
|-
|[[File:imagej1-icon.png|64px]]
|[[ImageJA]]
|[[Contributors|ImageJ developers]]
| 
ImageJA is a project that provides a clean [[Git]] history of ImageJ1, with a proper 'pom.xml' file so that it can be used with Maven without hassles.

It is what ImageJ2's legacy support uses at its core.
|Jul. 2005
|Active

|-
|
|[[ImageJFX]]
|{{Person|cmongis}}
| ImageJFX is a new user interface for ImageJ, built using [[wikipedia:JavaFX|JavaFX]].
|2015
|Active
|-
|[[File:imagesxm-icon.png|64px]]
|[[ImageSXM]]
|Steve Barrett
|Image SXM is a version of NIH Image that has been extended to handle the loading, display and analysis of scanning microscope images.
|May 1993
|Active
|-
|[[File:astroimagej.png|64px]]
|[http://www.astro.louisville.edu/software/astroimagej/ AstroImageJ]
|[http://www.astro.louisville.edu/john_kielkopf/ John Kielkopf]
|AstroImageJ is ImageJ with astronomy plugins and macros installed.
|Unknown
|Active
|-
|
|[http://www.rawak.de/ij2x/imagej2x.html ImageJ2x]
|[http://rawak.de/ Rawak Software]
|ImageJ2x is a fork of ImageJ1, modified to use a Swing interface.
|Unknown
|Last update:<br>
May 2015
|-
! colspan=6 | Closed-source variants
|-
|[[File:eu-hou-logo.png|64px]]
|[http://www.euhou.net/index.php?option=com_content&task=view&id=7&Itemid=9 SalsaJ]
|[http://www.euhou.net/ EU-HOU]
|SalsaJ is a closed-source fork of ImageJ1 intended for use with professional astronomy images. It was designed to be used in classrooms, and has been localized into over 30 different languages.
|Unknown
|Last update:<br>
Oct. 2012
|-
! colspan=6 | Obsolete variants
|-
|
|[[MBF ImageJ]]
|Tony Collins
|
The MBF "ImageJ for Microscopy" bundle (formerly [http://www.uhnres.utoronto.ca/facilities/wcif/imagej/ WCIF ImageJ]) is a collection of plugins and macros, collated and organized by the MacBiophotonics facility.

It went hand in hand with a comprehensive manual describing how to use the bundle with light microscopy image data. It was a great resource by microscopists, for microscopists. Unfortunately, the manual went offline in late 2012. In response, the software team at [[LOCI]] created the [[Cookbook]] user guide and [[update site]], which includes most of the same plugins.

|2005
|Defunct<br>
(Last update:<br>
Dec. 2009)
|-
|
|[[ImageJX]]
|{{Person|Harris}}
|
ImageJX was created as a means to discuss and explore improvements to ImageJ. There was an [http://groups.google.com/group/imagejx ImageJX mailing list] as well as an ImageJX software prototype.

The ImageJX software prototype was a proof of concept—an attempt to reorganize ImageJ's internals to make it more flexible. The prototype demonstrated this flexibility by recasting the program in Swing. The ImageJX project formed the basis of an application to NIH for funding, which is what launched the ImageJ2 project (see above).

|Mar. 2009
|Superceded by ImageJ2
|-
|
|[[NIH Image]]
|{{Person|Rasband}}
|NIH Image is a public domain image processing and analysis program for the Macintosh. It is the direct predecessor of ImageJ, and is no longer under active development (though see ImageSXM below).
|1993 or earlier
|Superceded by ImageJ
|}

== History ==

The first imaging program that {{Person|Rasband}} developed, starting in the late 70s, was called simply "Image". It was written in Pascal, ran on PDP-11 minicomputers and ran in only 64KB of memory! Rasband started work on the second, [[NIH Image]], in 1987 when the Mac II became available. Rasband was a Mac enthusiast, and the Mac II had card slots just like the PDP-11. Rasband started work on ImageJ in 1997, when Java was becoming popular. Rasband was intrigued by the idea of creating a version of NIH Image that would "run anywhere", including as an applet in Web browsers.

== Timeline ==

Here is a timeline of software development related to ImageJ:

{{#tag:timeline|
Preset    = TimeHorizontal_AutoPlaceBars_UnitYear
ImageSize = width:690 barincrement:17
PlotArea  = left:15 right:20 bottom:30

Colors     =
  id:canvas  value:rgb(0.97,0.97,0.97)
  id:grid1   value:gray(0.7)
  id:grid2   value:gray(0.88)
  id:black   value:rgb(0,0,0)
  id:section value:rgb(0.8,0.8,0)
  id:mark1   value:rgb(0.7,0,0)
  id:years   value:gray(0.5)

BackgroundColors = canvas:canvas

Period     = from:1987 till:{{CURRENTYEAR}}
ScaleMajor = unit:year increment:2 start:1987 grid:grid1
ScaleMinor = unit:year increment:1 start:1987 grid:grid2
AlignBars  = justify

BarData=

  bar:title
  bar:dummy0 # empty bar functions as separator
  bar:section1
  barset:flavors
  bar:dummy1
  bar:section2
  barset:related
  bar:dummy2

# explanation: attribute 'barset' instead of 'bar' means consecutive data lines are automatically placed on new bar
#              data lines are lines containing at: or from: & till: attributes
#              'barset:break' means 'reset barcounter' = next line will be placed at first bar in barset
#              'barset:skip'  means 'increment barcounter' = skip one bar for next data line (to allow extra space
#                                                                             for text containing line break = ~)

PlotData =

  fontsize:M
  width:16
  color:section
  mark:(line,section)
  shift:(5,-6)

  bar:title from:start till:end text:"History of ImageJ" fontsize:XL anchor:middle align:center width:25 color:canvas mark:(line,canvas)
  bar:section1 from:start till:end text:"Flavors of ImageJ"
  bar:section2 from:start till:end text:"Related software"

  shift:(5,-5)
  fontsize:M
  mark:(line,mark1)

# ImageJ flavors

  barset:flavors
  at:1987 text:"[[NIH Image]]"
  at:1997 text:"[[ImageJ1]]"
  at:2000 text:"[[ImageSXM]]"
  at:2005 text:"[[WCIF ImageJ]]"
  at:2005 text:"[[ImageJA]]"
  at:2007 text:"[[MBF ImageJ]]"
  at:2008 text:"[[Fiji]]"
  at:2009 text:"[[ImageJX]]"
  at:2009 text:"[[ImageJ2]]" # October 2009
  at:2015 text:"[[ImageJFX]]"

# Related software

  barset:related
  at:1999 text:"[[ITK]]"
  at:2002 text:"[[VisBio]]" # 27-Aug-2002
  at:2004 text:"[[KNIME]]" # Jan-2004
  at:2006 text:"[[Bio-Formats]]" # 10-Jan-2006
  at:2006 text:"[[BioImageXD]]" # Feb-2006
  at:2006 text:"[[CellProfiler]]"
  at:2006 text:"[[OMERO]]"
  at:2007 text:"[[Bio7]]" # Jul-2007 - http://bio7.622846.n4.nabble.com/Welcome-td622851.html
  at:2007 text:"[[Endrov]]"
  at:2007 text:"[[Micro-Manager]]" # 08-Feb-2007
  at:2009 text:"[[BoneJ]]"
  at:2010 text:"[[Alida]]"
  at:2010 text:"[[MiToBo]]"
  at:2011 text:"[[Icy]]"
}}

== Publications ==
* {{Citation | last = Schneider | first = C. A.
| last2 = Rasband | first2 = W. S.
| last3 = Eliceiri | first3 = K. W.
| year = 2012
| journal = Nature methods
| url = http://www.nature.com/nmeth/journal/v9/n7/full/nmeth.2089.html
| title = NIH Image to ImageJ: 25 years of image analysis
| volume = 9(7)
| pages = 671-675
| pmid = 22930834}}.
* {{Citation | last = Schindelin | first = J.
| last2 = Rueden | first2 = C. T.
| last3 = Hiner | first3 = M. C.
| last4 = Eliceiri | first4 = K. W.
| year = 2015
| journal = Molecular Reproduction and Development
| url = http://onlinelibrary.wiley.com/doi/10.1002/mrd.22489/full
| title = The ImageJ ecosystem: An open platform for biomedical image analysis
| volume = 
| pages = 
| pmid = 26153368}}.

See also [[Citing]].

[[Category:Citable]]
[[Category:Software]]