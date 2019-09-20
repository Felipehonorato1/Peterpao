%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Template de Relatório
% Version 0.8 (12/04/19)
%
% Authors:
% Franklin Coêlho
% Eudisley Anjos
% 
% License:
% CC BY-NC-SA 3.0 (http://creativecommons.org/licenses/by-nc-sa/3.0/)
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

\documentclass[10pt, a4paper, twocolumn]{article} 

\input{config.tex}



%%%%%%%%%%%%%%%%%%%%% HEADER %%%%%%%%%%%%%%%%%%%%%


\title{Peter Pão}

\author{
    \centering\authorstyle Daniel Cassiano \textsuperscript{1}, Felipe Honorato \textsuperscript{1}, Humberto Navarro \textsuperscript{1},Lara Pontes\textsuperscript{1}\\
    \textsuperscript{1}\institution{Bacharelando em Engenharia de Computação, Centro de Informática -- Universidade Federal da Paraíba}\\
    \email{danielchaves@eng.ci.ufpb.br, felipesousa@eng.ci.ufpb.br, humbertocarvalho@eng.ci.ufpb.br, larapontes@eng.ci.ufpb.br}
}

\date{}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

\begin{document}

\maketitle        

\thispagestyle{firstpage}

\lettrineabstract{Otimizar a produção de pães na Panificadora Jesus é o pão da vida, localizada na cidade de Borborema, interior da Paraíba. No projeto, solucionamos um dos problemas de logística do estabelecimento.} \\ \\ %Pula duas linhas
\textbf{Palavras-chave:} Pães, padaria, logística, automatização


\section*{INTRODUÇÃO}

\par A partir de um circuito elaborado utilizando portas lógicas, contadores, decodificadores e sensores de infravermelho, 


\section*{METODOLOGIA}\par
Para a execução do projeto, utilizamos o contador 4029, o decodificador 7447 e dois displays de 7 segmentos conectados em duas protoboards e interligados por jumpers. Para a alimentação do circuito, utilizamos um Arduino. Assim, através dos sinais recebidos pelos receptores Up/Down do contador, o contador cresce ou decresce, dependendo de qual sensor for ativado, pois o receptor fica em nível lógico alto (Up) apenas quando o sensor infravermelho de crescimento está ativado, enviando, dessa forma, sinal para o decodificador, que expressa o número atual da contagem no display.

\section*{DESCRIÇÃO DO PROJETO}
        \par 
Na Panificadora Jesus é o pão da vida, há uma rampa que conduz os pães desde o ambiente de produção até o de venda, deixando-os cair em uma caixa de armazenamento, de onde são retirados pelo vendedor, para os clientes. No entanto, uma das exigências desse processo em tempo real é a constante comunicação entre os dois funcionários envolvidos, tendo em vista que a oferta e a demanda de produto varia muitas vezes ao longo de um dia.\par

Assim, elaborou-se a ideia de automatizar o necessário canal comunicativo, a partir da implementação de um contador dos pães que passam pela rampa e dos que saem da caixa de armazenamento, ligado a dois displays de sete segmentos, disponíveis ao padeiro, informando a quantidade em questão.\par

A automatização da contagem se dará por meio do posicionamento de um sensor de proximidade infravermelho E18-D80NK em determinado ponto da rampa, para incrementar a quantidade de pães quando a distância padrão for interceptada pela passagem de um pão, e de um botão, para o vendedor decrementá-la a cada pão vendido.\par
O contador de pães será feito com dois contadores de década, sendo um deles dependente do outro. Como serão usados dois displays de sete segmentos, o que representará o algarismo menos significativo estará ligado ao contador dependente apenas do sensor infravermelho e do botão, enquanto o referente ao mais significativo terá um contador dependente também do primeiro contador, para que haja incremento somente quando o primeiro atingir o valor binário de 1010 e decremento quando esse estiver com o valor binário de 0000 antes do vendedor apertar o botão.\par

%Inserção de imagem
\begin{figure}[H]
    \centering
    %"width" serve para ajustar a dimensão da imagem
    \includegraphics[width=0.4\linewidth]{pictures/FOTO.png}
    \caption{Imagem adaptada. Esquemático da rampa com o contador.}
    \label{fig:f01}
\end{figure}

\begin{figure}[H]
    \centering 
    \includegraphics[scale=0.5]{pictures/mopa.png}
    \caption{Circuito.}    
    \label{fig:f02}
\end{figure}

\section*{EXECUÇÃO DO PROJETO, TESTES E RESULTADOS}

Pela ausência do circuito integrado 4029 (contador BCD/Decada com função Up/Down) no Quartus II, o circuito foi desenhado e verificado esquematicamente. 



\\ \\ \\

% Definindo novas cores
\definecolor{verde}{rgb}{0,0.5,0}
% Configurando layout para mostrar codigos em C
\lstset{
  language=C,
  basicstyle=\ttfamily\small, 
  keywordstyle=\color{blue}, 
  stringstyle=\color{verde}, 
  commentstyle=\color{red}, 
  extendedchars=true, 
  showspaces=false, 
  showstringspaces=false, 
  numbers=left,
  numberstyle=\tiny,
  breaklines=true, 
  backgroundcolor=\color{gray!10},
  breakautoindent=true, 
  captionpos=b,
  xleftmargin=0pt,
}
\pagestyle{empty}

\section*{CONCLUSÕES}
 Após a implementação do projeto no estabelecimento, a logística será facilitada, garantindo mais conforto aos funcionários, com o processo de contagem de pães e de comunicação automatizados, e clientes, que receberão os produtos de forma mais rápida e eficiente
\\ \\ \\ \\ \\ \\ \\ \\ \\
\\
\\
\\
\\
\\
\\
\\
\\
\\
\\
\\
\\
\\
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
\section*{REFERÊNCIAS}
BARBOSA, Carlos Ricardo. Eletrônica Digital. São Leopoldo: 2009. p.97
PINTO, Danilo; MAZZOCCANTE, Gustavo; SILVA, Karina. Estudo do sensor de proximidade infravermelho para pequenas distâncias e descontinuidades em superfícies planas. Goiânia: 2015.

https://www.alldatasheet.com/datasheet-pdf/pdf/50852/FAIRCHILD/CD4029.html

https://datasheetspdf.com/pdf-file/245544/ETC/7447/1 

https://datasheetspdf.com/pdf/500074/Fairchild/7408/1


\end{document}
