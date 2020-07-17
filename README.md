# ResumeLaTeX:
My resume in LaTeX.
It uses res.cls for templating which was created by Michael DeCorte

## Template:
I created the files within to be fairly easy to adapt for your own resume.  This was done as an easy way for RIT Space Exploration members to create professional looking resumes quickly.  It is really as simple as just replacing my details with your own.


### Fonting:
Depending on if you are on windows or mac there is the option to change the active font.  By default on windows it is set to use Arial (A calibri option is also comment out), and on Mac Helvetica Neue.  
```
%%%Windows Font Compile Options%%%
\ifwindows
	% Assign the calibri font + spacing.
	%\def \USEDSPACE {\26.4em}
	%\setmainfont[ BoldFont={Calibrib.ttf}, ItalicFont={Calibrii.ttf},BoldItalicFont={Calibriz.ttf}]{Calibri.ttf} 

	% Assign the arial font + spacing.
	\def \USEDSPACE {24.3em}
	\setmainfont[ BoldFont={Arialbd.ttf}, ItalicFont={Ariali.ttf},BoldItalicFont={Arialbi.ttf}]{Arial.ttf}
\fi

%%%Mac Font Compile Options%%%
\ifmacosx
	% Assign the Helvetica Neue font + spacing.
	\def \USEDSPACE {24.6em}
	\setmainfont[ BoldFont={Helvetica Neue Bold}, ItalicFont={Helvetica Neue Italic},BoldItalicFont={Helvetica Neue Bold Italic}]{Helvetica Neue} 
\fi
```

You will also notice the \USEDSPACE definition.  That is a value used to align the website header with the phone number below it.  Also, note that issues may arise on overleaf with the fonting, so you can comment/delete the section with the \ifwindows and \ifmacosx conditionals.  You would only have to modify the \USEDSPACE value.

### Sections:
Each actual section in the resume.tex is created with a \def statement.  This allows for easy additions of new sections or manipulations of existing ones.  Below is an example of an objective section

```
\def \OBJECTIVE {
	\section{OBJECTIVE}
	Fourth year Computer Science major looking to apply learned theory and obtain practical experience through full time employment.  Available January 2021.
}
```

Then it can be included in the document by just appending it the document section at the bottom of the .tex file.
```
% %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%
% Document:
% 
% This is where items are actually included inside the document.
% Everything leading up to it was just configuration and creating the content.
% If you want it to appear it has to be listed here...
%
% %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\begin{document}

% This should remain here in this location but feel free to modify the data.
\HEADERS % This existed previously

\begin{resume}
% Space between header and start of resume.  We are reducing it here.
\vspace{-7.5mm}

% Choose which sections to include/exclude here.  You can also re-arrange the order of them.
\OBJECTIVE  %%% HERE IS OUR NEW SECTION %%%

\end{resume}
\end{document}
```

Then if you have multiple sections they can moved around, removed, or conditionally compiled far easier.

## Using the Template:
The easiest way to use this template is to use Overleaf.  With Overleaf you just need to move the resume.tex and res.cls files to your project.  Then you can replace my information with your own.  There are plenty of examples for styling within the document that you can use.  

## Overleaf Compilation Issues:
If you are getting issues compiling your .pdf file from the template then you should try changing your compiler.  You can do this by clicking the leaf next to the "menu" button in the overleaf UI within your project.  Then you can change your compiler.  The one that I have tested this with is LuaLaTex.
