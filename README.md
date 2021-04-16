# Latex for Students 🧪
This project provides a template to create reports and academic papers in latex.   
:heavy_check_mark: Optimized for natural sciences especially electrical engineering.  
:heavy_check_mark: Choose between several predefined templates.  
:heavy_check_mark: Drawing Karnaugh maps in LaTeX (KV-Diagram)  
:heavy_check_mark: Custom VHDL Syntax Highlighting  

## Example 🧾

## How To Start 👷‍

## How To Contribute :hugs:
If you would like to have new functions or templates that are not included in the project yet, feel free to create them yourself and add them to this project.

## Documentation :green_book:
This is supposed to give you an overview of the use and structure of the project. If you are missing further explanations open an Issue or add the missing explanation yourself.

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
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ├── closingPageHAW.tex  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ├── titlePageAcademicPaper.tex  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; └── titlePageReport.tex  
- Coming soon: Explanation of the individual files and folders

### Images and Graphics
Include images and graphics with our custom commands.  
The images and graphics will get centered and become a caption and a reference label.  
The commands are looking for the specified files in the folder `src/img/`.  
```latex
%One Image
%\imgOne{FileOne}{Scaling}{Signature}{Label}
\imgOne{test.png}{0.5}{The Test figure}{Tstfig}

%Tow Images
%\imgTow{FileOne}{Scaling}{FileTow}{Scaling}{Signature}{Label}
\imgTow{test1.png}{0.5}{test2.png}{0.5}{The Test figure}{Tstfig}

%Three Images
%\imgThree{FileOne}{Scaling}{FileTow}{Scaling}{FileThree}{Scaling}{Signature}{Label}
\imgThree{test1.png}{0.5}{test2.png}{0.5}{test3.png}{0.5}{The Test figure}{Tstfig}

%Four Images
%\imgFour{FileOne}{Scaling}{FileTow}{Scaling}{FileThree}{Scaling}{FileFour}{Scaling}{Signature}{Label}
\imgFour{test1.png}{0.5}{test2.png}{0.5}{test3.png}{0.5}{test4.png}{0.5}{The Test figure}{Tstfig}
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
    U_b&=\frac{R_2}{R_1+R_2} \cdot U_q\\
\end{align}
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
```

### Include Code 
To insert Code listings into your Latex use the following commands.  
I recommend creating a new folder for your code files in your project under `src/<languageName>` e.g. `src/python`.  
Replace `path` with the path to the code files you want to include relative to the `main.tex` file.
- If you want to read more about how to customize code listings I recommend reading this [guide](https://www.overleaf.com/learn/latex/Code_listing).
```latex
% Include files
\lstinputlisting[style=vhdl]{path/fileName}
\lstinputlisting[style=vhdl]{VHDL/VHDL-Beschreibung.vhdl}

%  Include code directly
\begin{lstlisting}[style=vhdl]
    entity FULL_ADD is
        port( A, B, CIN : in bit ;
        SUM, COUT : out bit );
    end FULL_ADD;
    architecture FA_1 of FULL_ADD is
    end FA_1;
\end{lstlisting}
```

### References 

### Sources

### Draw Karnaugh maps in LaTeX (KV-Diagram) 

## Contributors :star:
[FRautenberg](https://github.com/FRautenberg)

## Special Thanks To :wink:
[Ignasi](https://tex.stackexchange.com/users/1952/ignasi)

## Project ☕
https://github.com/mathisheeren/latex-for-students

## License 👮‍
[GPL-3.0 License](LICENSE.txt)
