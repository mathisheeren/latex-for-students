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
% One Image
% \imgOne{FileOne}{Scaling}{Signature}{Label}
\imgOne{test.png}{0.5}{The Test figure}{Tstfig}

% Tow Images
% \imgTow{FileOne}{Scaling}{FileTow}{Scaling}{Signature}{Label}
\imgTow{test1.png}{0.5}{test2.png}{0.5}{The Test figure}{Tstfig}

% Three Images
% \imgThree{FileOne}{Scaling}{FileTow}{Scaling}{FileThree}{Scaling}{Signature}{Label}
\imgThree{test1.png}{0.5}{test2.png}{0.5}{test3.png}{0.5}{The Test figure}{Tstfig}

% Four Images
% \imgFour{FileOne}{Scaling}{FileTow}{Scaling}{FileThree}{Scaling}{FileFour}{Scaling}{Signature}{Label}
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

### Include PDF Documents

### Include Code 

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
