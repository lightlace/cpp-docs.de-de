---
title: C.2 Regeln
ms.date: 11/04/2016
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
ms.openlocfilehash: 7c0de4c14e229716bcf764d9859be439090368b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642805"
---
# <a name="c2-rules"></a>C.2 Regeln

Die Notation wird in Abschnitt 6.1 des C-standard beschrieben. In diesem Anhang Grammatik zeigt die Erweiterungen die Basissprache-Grammatik für die OpenMP-C- und C++-Anweisungen.

**/\* in C++ (ISO/IEC 14882:1998) \*/**

*Anweisung-Seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung (OpenMP)*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung-Seq-Anweisung*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung-Seq-Anweisung (OpenMP)*

**/\* in C90 (ISO/IEC 9899:1990) \*/**

*statement-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung (OpenMP)*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Statement-List-Anweisung*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung-List-Anweisung (OpenMP)*

**/\* in C99 (ISO/IEC 9899: 1999) \*/**

*Block-Element*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anweisung (OpenMP)*

**/\* Standard-Anweisungen \*/**

*Anweisung*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP-Konstrukt*

*OpenMP-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*für die-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Abschnitte-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Single-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-für-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-Abschnitten-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Master-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Critical-Konstrukt:*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Atomic-Konstrukt*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*geordnete-Konstrukt*

*OpenMP-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Barrier-Direktive*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Flush-Direktive*

*strukturierte-Block*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*

*Parallel-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-Direktive strukturiert-block*

*Parallel-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp parallel** *Parallel-Klausel*<sub>Optseq</sub> *neue-Zeile*

*Parallel-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eindeutige-Parallel-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-Klausel*

*eindeutige-Parallel-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Wenn (** *Ausdruck* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Num_threads (** *Ausdruck* **)**

*für Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*für die Richtlinie Iteration-Anweisung*

*für die Richtlinie*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp für** *for-Klausel*<sub>Optseq</sub> *neue-Zeile*

*for-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eindeutige-für-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**NOWAIT**

*eindeutige-für-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Sortiert**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Zeitplan (** *Plantyp* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Zeitplan (** *Plantyp* **,** *Ausdruck* **)**

*Plantyp*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**static**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Dynamische**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**geführtes**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Common Language Runtime**

*Abschnitte-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Abschnitt-Scope-Abschnitten-Richtlinie*

*Abschnitte-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma-Omp-Abschnitten** *Abschnitte-Klausel*<sub>Optseq</sub> *neue-Zeile*

*Abschnitte-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**NOWAIT**

*im Abschnitt Bereich*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{Abschnitt-Sequenz}*

*Abschnitt-Sequenz*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Section-Direktive*<sub>opt</sub> *strukturiert-Block*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*strukturierte abschnittsdirektive Abschnitt-Sequence-block*

*Section-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**im Abschnitt Omp-Pragma** *neue-Zeile*

*Single-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*strukturierte Single-Directive-block*

*Single-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp einzelne** *einzigen Klausel*<sub>Optseq</sub> *neue-Zeile*

*Single-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**NOWAIT**

*Parallel-für-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-für-Directive-Iteration-Anweisung*

*Parallel-für-Directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp parallel für** *Parallel-for--Klausel*<sub>Optseq</sub> *neue-Zeile*

*Parallel-for--Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eindeutige-Parallel-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eindeutige-für-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-Klausel*

*Parallel-Abschnitten-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-Abschnitten-Richtlinie im Abschnitt Bereich*

*Parallel-Abschnitten-Directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp parallelen Abschnitten** *Parallel-Abschnitten-Klausel*<sub>Optseq</sub> *neue-Zeile*

*Parallel-Abschnitten-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eindeutige-Parallel-Klausel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-Klausel*

*Master-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Master-Direktive strukturiert-block*

*Master-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp Master** *neue-Zeile*

*Critical-Konstrukts*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*die Critical-Direktive von strukturierten block*

*die Critical-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp kritische** *Region-Satz*<sub>opt</sub> *neue-Zeile*

*Region-Satz*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(ID)*

*Barrier-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp Barriere** *neue-Zeile*

*Atomic-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Atomic-Direktive Ausdruck-Anweisung*

*Atomic-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp atomic** *neue-Zeile*

*Flush-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp leeren** *Flush-Vars*<sub>opt</sub> *neue-Zeile*

*Flush-Vars*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(Variablen-Liste)*

*geordnete-Konstrukt*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*strukturierte sortiert-Directive-block*

*geordnete Richtlinie*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp sortiert** *neue-Zeile*

**/\* Standard-Deklarationen \*/**

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Threadprivate-Direktive*

*Threadprivate-Direktive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Pragma Omp Threadprivate (** *Variablenliste*  **)** *neue-Zeile* 

*Data-Klausel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Private (** *Variablenliste* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Copyprivate (***Variablenliste***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Firstprivate (***Variablenliste***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Lastprivate (** *Variablenliste*  **)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Freigegebene (** *Variablenliste* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Standard (freigegeben)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Standard (keine)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Verringerung der (***Reduction-Operator***:***Variablenliste***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Copyin (***Variablenliste***)**

*Reduction-Operator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Einer der:  **+  \* -& ^ &#124; & &&#124;&#124;**

**/\* in C \*/**

*Variablenliste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Variablenliste* **,** *Bezeichner*

**/\* in C++ \*/**

*Variablenliste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ID-Ausdruck*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Variablenliste* **,** *-Id-Ausdruck*