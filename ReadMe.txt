========================================================================
                                VisFed
========================================================================

Background:

VisFed is a Visual Studio Add-In that allows Fed to be integrated
as the default text editor.  It will be used instead of the Visual
Studio built-in editor when you double-click on a file or press F4
after compiling (it will go to the proper line in the Fed buffer).

Installation:

1) Copy VisFed.dll (and the latest Fed.exe and Fed.chm) into your Fed directory.
   ie C:\Program Files\Quantel\Fed

2) Register the DLL using regsvr32.exe from a Command Prompt.
   ... for example:
   > cd C:\Program Files\Quantel\Fed
   > regsvr32 VisFed.dll

3) Add C:\Program Files\Quantel\Fed to your PATH environment variable.

4) Start Visual Studio and go to:
      Tools
        Customize...
          Add-Ins and Macro Files

5) Click on Browse, and point Visual Studio to your VisFed.dll file.

6) Click the checkbox to indicate that you want to use the Add-In, and
   Close the Customize dialog box.

7) You should notice the VisFed Toolbar with the familiar Fed
   icon and a new icon - an arrow pointing to an 'F' (ok, so I'm no
   artist...if you are, send me some new icons!) representing "Send To
   Fed" which will send the active document to Fed, regardless of
   the "enable Fed" setting.


Using VisFed:

Clicking the Fed Toolbar Icon will show the VisFed configuration dialog.

Use Visual Studio as normal, and Fed should almost always (I'm not
making any guarantees) bring Fed to the foreground to edit the
document.


Problems:

VisFed works by hooks exposed by Visual Studio.  Most of the
functionality works from the OpenDocument hook.
So...If a document is open in Visual Studio, and you double click
the file in the File Browser...Fed will NOT come to the foreground.
Since the document was open in the Visual Studio editor, the
OpenDocument event never occurred.

