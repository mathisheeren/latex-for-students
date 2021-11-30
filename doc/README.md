### Images and Graphics
Include images and graphics with our custom commands.  
The images and graphics will get centered and become a caption and a reference label.  
The commands are looking for the specified files in the folder `src/img/`.  
```latex
%One figure
%\figOne{FileOne}{Scaling}{Signature}{Label}
\figOne{test.png}{0.5}{The Test figure}{Tstfig}

%Two figures
%\figTwo{FileOne}{Scaling}{FileTow}{Scaling}{Signature}{Label}
\figTwo{test1.png}{0.5}{test2.png}{0.5}{The Test figure}{Tstfig}

%Three figures
%\figThree{FileOne}{Scaling}{FileTow}{Scaling}{FileThree}{Scaling}{Signature}{Label}
\figThree{test1.png}{0.5}{test2.png}{0.5}{test3.png}{0.5}{The Test figure}{Tstfig}

%Four figures
%\figFour{FileOne}{Scaling}{FileTow}{Scaling}{FileThree}{Scaling}{FileFour}{Scaling}{Signature}{Label}
\figFour{test1.png}{0.5}{test2.png}{0.5}{test3.png}{0.5}{test4.png}{0.5}{The Test figure}{Tstfig}
```
Rotatet figures
```latex
%90 degree rotatet figure
\includegraphics[angle=90,origin=c]{src/img/File}

%90 degree rotatet figure and caption
\begin{sidewaysfigure}
	\figOne{FileOne}{Scaling}{Signature}{Label}
\end{sidewaysfigure}
```

### Tables
Copy and paste this in your document if you want a nice formatted table.  
Adjust the tabular Environment to fit your needs.  
- This website provides a good [table generator](https://www.tablesgenerator.com/).   
- If you want to read more about how to customize tables I recommend reading this [guide](https://de.overleaf.com/learn/latex/tables).   
```latex
\begin{table}[H]
    \centering
    \begin{adjustbox}{max width=\textwidth} % Adjusts the table to the maximum width 
        \bgroup\def\arraystretch{1.5} % Distance between text and table  
        \begin{tabular}{|p{6cm}|l|}
            \hline\rowcolor{lightgray}
            foo     & bar \\ \hline
            1 	    & test \\ \hline
        \end{tabular}
        \egroup
    \end{adjustbox}
    \caption{Some Caption for the Table}  % Caption
    \label{tab:exampleTable} % Label for reference within the document
\end{table}
```

### Formulas
To create a formula in a Latex document you must use a formula environment.  
1. **Inline formulas** use the `$` before and at the end of the formula. 
```latex
% Example
$ u_{M} = u_{R_M} + u_{q} $
```
2. **Centered** with and without numbering.
- If you dont want a numbering use `\begin{align*}` and `\end{align*}`.
- To define multiple formulas use `\\` at the end of the line.
- Align among each other wit the `&` operator.
```latex
\begin{align}
    U_a=\frac{R_4}{R_3+R_4}\cdot U_q\\
    U_b=\frac{R_2}{R_1+R_2} \cdot U_q\\
    U_a&=\frac{R_4}{R_3+R_4}\cdot U_q\\ 
    U_b&=\frac{R_2}{R_1+R_2} \cdot U_q
\end{align}
```

### Listings
For **Unordered lists** use `\begin{itemize}` and `\end{itemize}`.  
For **Ordered lists** use `\begin{enumerate}` and `\end{enumerate}`.  
- If you want to read more about how to customize listings I recommend reading this [guide](https://de.overleaf.com/learn/latex/lists).
```latex
\begin{itemize}
    \item One bullet point
    \item One more bullet point
    \item Bullet point three
\end{itemize}
```
Listing with specific characters:
```latex
\begin{itemize}
    \item[a)] One bullet point
    \item[*)] One more bullet point
    \item[?)] Bullet point three
\end{itemize}
```

### Split latex code into multiple files
You can split latex code into multiple files if you use `\subfile{tex/name.tex}`.  
<br/><br/>
![no page number](../../media/examples/subfile.gif)

### Cross referencing
To make cross references to equations, sections or figures use the `\label{name}` command.  
You must place the `\label{name}` directly after the element you want to reference to.  
At the point in the document where the reference is to be inserted use:  
1. `\ref{name}` To output only the number of the element. 
1. `\pageref{name}` To output only the page number of the element.  
1. `\autoref{name}` To added automatic prefix to the reference. 

 To indicate what is being labeled it is best practice to add a prefix to the label name.  
 This helps to keep track of the labels in large documents.  
 There are common names for certain elements that you should follow.  (`\autoref{}` only works with these prefixes) 
 - Section `sec:name`
 - Table `tab:name`
 - Figure `fig:name`
 - Equation `eq:name`  
 
### Sources
To make a source specification, the source must first be defined in the file `src/literature.bib`.
- This website provides an awesome [bibliographie generator](https://www.tablesgenerator.com/).
- If you want to read more about how to Citing with BibTeX I recommend reading this [guide](https://de.wikibooks.org/wiki/LaTeX-Kompendium:_Zitieren_mit_BibTeX).
- If the compilation fails, it may help to update the file src/literature.bib with TexStudio -> Tools -> Bibligraphy (F8) to index new literature.

At the point in the document where the Citation is to be inserted use:  
1. `\citep{name}` To output only the number from the bibliography e.g. [1]. 
1. `\citep[][Page 8]{name}` To output the number from the bibliography and the page number e.g. [1, Page 8].
1. `\citep[vgl.][Page 8]{name}` To add something before the number from the bibliography e.g. [vgl. 1, Page 8]. 

### Include PDF Documents
To insert PDF documents into your Latex use the following commands.  
I recommend creating a new folder for your PDF documents in your project under `src/pdf`.  
Replace `path` with the path to the PDF document you want to include relative to the `main.tex` file.   
```latex
% Insert PDF (On the page):
\includegraphics[page=1,width=\textwidth,height=.9\textheight,keepaspectratio]{path/fileName}

% Insert all PDF pages (Whole pages):
\includepdf[pages=-]{path/fileName}

% All pages but in reverse order (Whole pages):
\includepdf[pages=last-1]{path/fileName}

% All pages from ... to ... (Whole pages):
% \includepdf[pages={from-to}]{path/fileName}
\includepdf[pages={2-10}]{path/fileName}

% Only certain pages X,Y and Z (Whole pages):
% \includepdf[pages={X,Y,Z}]{path/fileName}
\includepdf[pages={2,5,11}]{path/fileName}

% Inserting a blank page between X and Y (Whole pages):
% \includepdf[pages={X,{},Y}]{path/fileName}
\includepdf[pages={2,{},4}]{path/fileName}

% Combination possible (Whole pages):
% \includepdf[pages={from-to, X,Y,{},Z}]{path/fileName}
\includepdf[pages={2-7,2,4,{},6}]{path/fileName}

% Insert PDF with 90° rotatet page
\newpage
\global\pdfpageattr\expandafter{\the\pdfpageattr/Rotate 90}
	\includepdf[pages=-,angle=90]{path/fileName}
\global\pdfpageattr\expandafter{\the\pdfpageattr/Rotate 0}
```

### Include Code 
To insert Code listings into your Latex use the following commands.
If you don't want to include VHDL code use e.g. `[language=Python]` instead of `[style=vhdl]`.  
I recommend creating a new folder for your code files in your project under `src/<languageName>` e.g. `src/python`.    
Replace `path` with the path to the code files you want to include relative to the `main.tex` file.
- If you want to read more about how to customize code listings I recommend reading this [guide](https://www.overleaf.com/learn/latex/Code_listing).
```latex
% Include files
\lstinputlisting[style=cvs, caption=Some test, label=test]{path/fileName} % c code in Visualstudio look
\lstinputlisting[style=vhdl, caption=Some test, label=test]{VHDL/VHDL-Beschreibung.vhdl}

%  Include code directly
\begin{lstlisting}[style=vhdl, caption=Some test, label=test]
    entity FULL_ADD is
        port( A, B, CIN : in bit ;
        SUM, COUT : out bit );
    end FULL_ADD;
    architecture FA_1 of FULL_ADD is
    end FA_1;
\end{lstlisting}
```

### Supperss page number
You can suppress the page number if you use `\begin{noPageNumber}`.  
The page numbering will be continued on the next page after `\end{noPageNumber}`.    
<br/><br/>
![no page number](../../media/examples/noPageNumber.gif)

### Draw Karnaugh maps in LaTeX (KV-Diagram) 
![Example-4x4-groups-caption](../../media/Media-Karnaugh-maps/Example-4x4-groups-caption.PNG)  
**Create KV diagrams**  
You can create KV diagrams in the following sizes;
1. 2x2 use `\begin{kvTable22}` and `\end{kvTable22}`.
1. 2x4 use `\begin{kvTable24}` and `\end{kvTable24}`.
1. 4x4 use `\begin{kvTable44}` and `\end{kvTable44}`.
1. 4x8 use `\begin{kvTable48}` and `\end{kvTable48}`.    

**Fill with values**  
Use `fillKv{0,1,2,3,4,5,6,7,...}` to fill the KV diagram with values.       
The values are filled from the first element at the top left to the last element at the bottom right.  
The array index corresponds to the position number.  
The first element of the array has the index 0 and is set to position 0.
```latex
\begin{kvTable24}
    \fillKv{0,1,2,3,4,5,6,7} % Fill in values
\end{kvTable24}
```
Only numbers can be entered. If an Indeterminate is to be entered instead of a number,    
leave out the position where it is to be entered when filling in and use `\indeterminats{position}`.  
```latex
\begin{kvTable22}
    \fillKv{0,1,2,3, ,5,6,7} % Fill in values
    \indeterminats{4}        % Indeterminate at position 4
\end{kvTable22}
```

**Group Terms**  
You can mark groups and individual values in a desired color: 
```latex
\groupTerm{9}{red}                  % Highlight individual value in color
\groupTerms{2}{7}{green}            % Mark group of values in color
\groupLeftRight{4}{11}{purple}      % Marking over edge (left/right)
\groupTopBottom[3pt]{1}{13}{blue}   % Marking over edge (top/bottom)
\groupCorner[2pt]{orange}           % Corners become colored marking
```
Example:
```latex
\begin{kvTable44}
    \fillKv{
        0,1,2,3,
        4,5,6,7,
        8,9,10,11,
        12,13,14,15
    }
    \groupTerm{9}{red}                  % Highlight individual value in color
    \groupTerms{2}{7}{green}            % Mark group of values in color
    \groupLeftRight{4}{11}{purple}      % Marking over edge (left/right)
    \groupTopBottom[3pt]{1}{13}{blue}   % Marking over edge (top/bottom)
    \groupCorner[2pt]{orange}           % Corners become colored marking
\end{kvTable44}
```

### Project Structure
/latex-for-students  
├── .gitignore  
├── LICENSE  
├── main.tex  
├── README.md  
├── src  
│&nbsp; &nbsp; &nbsp; ├── literature.bib  
│&nbsp; &nbsp; &nbsp; └── img  
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; └── Logo.png  
└── tex  
&nbsp; &nbsp; &nbsp; &nbsp; ├── lib  
&nbsp; &nbsp; &nbsp; &nbsp; │&nbsp; &nbsp; &nbsp; ├── customCommands.tex  
&nbsp; &nbsp; &nbsp; &nbsp; │&nbsp; &nbsp; &nbsp; ├── karnaughsMaps.tex  
&nbsp; &nbsp; &nbsp; &nbsp; │&nbsp; &nbsp; &nbsp; └── vhdlCode.tex  
&nbsp; &nbsp; &nbsp; &nbsp; └── templates  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ├── closingPage.tex  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ├── titlePageAcademicPaper.tex  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; └── titlePageReport.tex  

| Files / Folders | Description |
|------|-------------|
|main.tex|Is the main file. The structure of the latex document is described here. <br/> All packages are imported and the formatting settings are made.|
|src|Contains all (non-latex) files that are to be included. <br/>For a better structuring new subfolders can be created. |
|literature.bib|Here all sources are specified which are to be used for source information in the document.|
|img|Contains all images to be included in the document.|
|tex|Contains all latex documents of the project. <br/> New files can also be created here. |
|lib|Contains files with custom commands that provide new functionality. <br/>How to use the commands is described in the documentation.|
|customCommands.tex|Contains all self-created comandos that do not specifically belong to a topic.| 
|karnaughsMaps.tex|Contains all commands needed to create karnaugh Maps.|
|vhdlCode.tex|Setting for the display of VHDL code.|
|templates|All the different templates that can be used are stored here.|
|closingPage.tex|Is the default closing page. Contains the list of sources, bibliography and list of tables.|
|titlePageAcademicPaper.tex|For work that is written on your own, such as term papers.|
|titlePageReport.tex|For work that is written in groups such as laboratory reports.|
