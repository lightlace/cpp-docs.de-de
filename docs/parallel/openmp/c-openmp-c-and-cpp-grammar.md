---
title: C. OpenMP-C- und C++-Grammatik
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 85e18161079b49e83cc9fedb3184ee220c889e75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362945"
---
# <a name="c-openmp-c-and-c-grammar"></a>C. OpenMP-C- und C++-Grammatik

[C.1 Notation](#c1-notation)<br/>
[C.2 Regeln](#c2-rules)

## <a name="c1-notation"></a>C.1 Notation

Der Grammatikregeln für den bestehen aus des Namens für eine nicht-Terminal, gefolgt von einem Doppelpunkt, gefolgt von Ersatz alternativen in separaten Zeilen.

Die syntaktische Ausdruck<sub>opt</sub> gibt an, dass der Begriff innerhalb die Ersetzung optional ist.

Der syntaktischen Ausdruck *Begriff*<sub>Optseq</sub> entspricht *Begriff-Seq*<sub>opt</sub> mit den folgenden zusätzlichen Regeln:

*term-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*term*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*term-seq* *term*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*term-seq*   `,` *term*

## <a name="c2-rules"></a>C.2 Regeln

Die Notation wird in Abschnitt 6.1 des C-standard beschrieben. In diesem Anhang Grammatik zeigt die Erweiterungen die Basissprache-Grammatik für die OpenMP-C- und C++-Anweisungen.

**/\* in C++ (ISO/IEC 14882:1998) \*/**

*statement-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-directive*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung-Seq-Anweisung*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung-Seq-Anweisung (OpenMP)*

**/\* in C90 (ISO/IEC 9899:1990) \*/**

*statement-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-directive*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Statement-List-Anweisung*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung-List-Anweisung (OpenMP)*

**/\* in C99 (ISO/IEC 9899:1999) \*/**

*block-item*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-directive*

**/\* Standard-Anweisungen \*/**

*Anweisung*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-construct*

*openmp-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sections-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*single-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-for-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-sections-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*master-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*critical-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ordered-construct*

*openmp-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*barrier-directive*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Flush-Direktive*

*structured-block*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*

*parallel-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-Direktive strukturiert-block*

*parallel-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel` *parallel-clause*<sub>optseq</sub> *new-line*

*parallel-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*

*unique-parallel-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (` *Ausdruck*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (` *Ausdruck*   `)`

*for-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*für die Richtlinie Iteration-Anweisung*

*for-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for` *for-clause*<sub>optseq</sub> *new-line*

*for-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-for-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*unique-for-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *Plantyp:*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *Plantyp* `,` *Ausdruck*   `)`

*Plantyp*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*sections-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Abschnitt-Scope-Abschnitten-Richtlinie*

*sections-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections` *sections-clause*<sub>optseq</sub> *new-line*

*sections-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*section-scope*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{Abschnitt-Sequenz}*

*section-sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*section-directive*<sub>opt</sub> *structured-block*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*strukturierte abschnittsdirektive Abschnitt-Sequence-block*

*section-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section` *new-line*

*single-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*strukturierte Single-Directive-block*

*single-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single` *single-clause*<sub>optseq</sub> *new-line*

*single-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*parallel-for-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-für-Directive-Iteration-Anweisung*

*parallel-for-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for` *parallel-for-clause*<sub>optseq</sub> *new-line*

*parallel-for-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-for-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*

*parallel-sections-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-Abschnitten-Richtlinie im Abschnitt Bereich*

*parallel-sections-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections` *parallel-sections-clause*<sub>optseq</sub> *new-line*

*parallel-sections-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*

*master-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Master-Direktive strukturiert-block*

*master-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master` *new-line*

*critical-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*die Critical-Direktive von strukturierten block*

*critical-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical` *Region-Satz*<sub>opt</sub> *neue-Zeile*

*region-phrase*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(ID)*

*barrier-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier` *new-line*

*atomic-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Atomic-Direktive Ausdruck-Anweisung*

*atomic-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic` *new-line*

*Flush-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush` *Flush-Vars*<sub>opt</sub> *neue-Zeile*

*Flush-Vars*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(variable-list)*

*ordered-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*strukturierte sortiert-Directive-block*

*ordered-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered` *new-line*

**/\* Standard-Deklarationen \*/**

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate-directive*

*threadprivate-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (` *variable-list*    `)` *new-line*

*data-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (` *variable-list*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (` *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (` *variable-list*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *Reduction-Operator*`:`*Variablenliste*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *variable-list*    `)`

*reduction-operator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;One of:   `+ \* - & ^ | && ||`

**/\* in C \*/**

*variable-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Variablenliste* `,` *Bezeichner*

**/\* in C++ \*/**

*variable-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*id-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*variable-list*   `,` *id-expression*
