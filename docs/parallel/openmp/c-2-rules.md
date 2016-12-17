---
title: "C.2 Regeln"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# C.2 Regeln
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Notation wird im Abschnitt 6.1 des C-standard beschrieben. In diesem Anhang Grammatik zeigt die Erweiterungen für die Ausgangssprache Grammatik für die OpenMP-C- und C++-Direktiven.  
  
 **/\* in C++ (ISO/IEC 14882:1998) \*/**  
  
 *Anweisung Seq*:  
  
 *Anweisung*  
  
 *OpenMP-Direktive*  
  
 *Anweisung Seq-Anweisung*  
  
 *Anweisung Seq-Direktive (OpenMP)*  
  
 **/\* in C90 (ISO/IEC 9899:1990) \*/**  
  
 *Statement-List,*:  
  
 *Anweisung*  
  
 *OpenMP-Direktive*  
  
 *Statement-List-Anweisung*  
  
 *Statement-List, Openmp-Direktive*  
  
 **/\* in C99 (ISO/IEC 9899:1999) \*/**  
  
 *Block-Element*:  
  
 *Deklaration*  
  
 *Anweisung*  
  
 *OpenMP-Direktive*  
  
 *Anweisung*:  
  
 **/\* Standard-Anweisungen \*/**  
  
 *OpenMP-Konstrukt*  
  
 *OpenMP-Konstrukt*:  
  
 *Parallel-Konstrukt*  
  
 *für Konstrukt*  
  
 *Abschnitte-Konstrukt*  
  
 *Single-Konstrukt*  
  
 *Parallel-für-Konstrukt*  
  
 *Parallel-Abschnitten-Konstrukt*  
  
 *Master-construc*  
  
 *Critical-Konstrukt*  
  
 *Atomic-Konstrukt*  
  
 *geordnete-Konstrukt*  
  
 *OpenMP-Direktive*:  
  
 *Barrier-Direktive*  
  
 *Flush-Direktive*  
  
 *strukturierte Block*:  
  
 *Anweisung*  
  
 *Parallel-Konstrukt*:  
  
 *Parallel-Direktive strukturiert-block*  
  
 *Parallel-Direktive*:  
  
 **# Pragma Omp-parallel**  *Parallel-Klausel*Optseq *neue-Zeile*  
  
 *Parallel-Klausel*:  
  
 *eindeutige-Parallel-Klausel*  
  
 *Data-Klausel*  
  
 *eindeutige-Parallel-Klausel*:  
  
 **Wenn (** *Ausdruck* **)**  
  
 **Num_threads (** *Ausdruck* **)**  
  
 *für Konstrukt*:  
  
 *für die Richtlinie Iteration-Anweisung*  
  
 *für die Richtlinie*:  
  
 **# Pragma Omp für** *for-Klausel*Optseq *neue-Zeile*  
  
 *for-Klausel*:  
  
 *eindeutige-für-Klausel*  
  
 *Data-Klausel*  
  
 **NOWAIT**  
  
 *eindeutige-für-Klausel*:  
  
 **sortiert**  
  
 **Zeitplan (** *Zeitplan Art* **)**  
  
 **Zeitplan (** *Zeitplan Art* **,** *Ausdruck* **)**  
  
 *Zeitplan-Art*:  
  
 **statische**  
  
 **Dynamische**  
  
 **Einführung**  
  
 **Common Language Runtime**  
  
 *Abschnitte-Konstrukt*:  
  
 *Sections-Direktive Abschnitt-Bereich*  
  
 *Sections-Direktive*:  
  
 **# Pragma Omp Abschnitte** *Abschnitte-Klausel*Optseq *neue-Zeile*  
  
 *Abschnitte-Klausel*:  
  
 *Data-Klausel*  
  
 **NOWAIT**  
  
 *Abschnitt Bereich*:  
  
 *{Abschnitt Sequenz}*  
  
 *Abschnitt Sequenz*:  
  
 *Abschnitt-Direktive*opt *strukturiert-Block*  
  
 *Abschnitt Sequenz Abschnitt Richtlinie strukturiert-block*  
  
 *Abschnitt-Direktive*:  
  
 **# Pragma Omp Abschnitt** *neue-Zeile*  
  
 *Single-Konstrukt*:  
  
 *Single-Direktive strukturiert-block*  
  
 *Single-Direktive*:  
  
 **# Pragma Omp einzelne** *Single-Klausel*Optseq *neue-Zeile*  
  
 *Single-Klausel*:  
  
 *Data-Klausel*  
  
 **NOWAIT**  
  
 *Parallel-für-Konstrukt*:  
  
 *Parallel-für-Directive Iteration-Anweisung*  
  
 *Parallele für Richtlinie*:  
  
 **# Pragma Omp-parallel für** *Parallel-for-Klausel*Optseq *neue-Zeile*  
  
 *Parallel-for-Klausel*:  
  
 *eindeutige-Parallel-Klausel*  
  
 *eindeutige-für-Klausel*  
  
 *Data-Klausel*  
  
 *Parallel-Abschnitten-Konstrukt*:  
  
 *Parallel-Abschnitten-Richtlinie im Abschnitt-Bereich*  
  
 *Parallel-Abschnitten-Direktive*:  
  
 **# Pragma Omp parallelen Abschnitten** *Parallel-Abschnitten-Klausel*Optseq *neue-Zeile*  
  
 *Parallel-Abschnitten-Klausel*:  
  
 *eindeutige-Parallel-Klausel*  
  
 *Data-Klausel*  
  
 *Master-Konstrukt*:  
  
 *Master-Direktive strukturiert-block*  
  
 *Master-Direktive*:  
  
 **# Pragma Omp Master** *neue-Zeile*  
  
 *Critical-Konstrukt*:  
  
 *Critical-Direktive strukturiert-block*  
  
 *Critical-Direktive*:  
  
 **# Pragma Omp kritische** *Region-Satz*opt *neue-Zeile*  
  
 *Region-Satz*:  
  
 *(Bezeichner)*  
  
 *Barrier-Direktive*:  
  
 **# Pragma Omp Barriere** *neue-Zeile*  
  
 *Atomic-Konstrukt*:  
  
 *Atomic-Direktive Ausdrucks*  
  
 *Atomic-Direktive*:  
  
 **# Pragma Omp atomic** *neue-Zeile*  
  
 *Flush-Direktive*:  
  
 **# Pragma Omp leeren** *Flush Vars*opt *neue-Zeile*  
  
 *Flush-var*:  
  
 *(Variable-Liste)*  
  
 *geordnete Konstrukt*:  
  
 *geordnete Richtlinie strukturiert-block*  
  
 *geordnete Richtlinie*:  
  
 **# Pragma Omp sortiert** *neue-Zeile*  
  
 *Deklaration*:  
  
 **/\* Standard-Deklarationen \*/**  
  
 *Threadprivate-Direktive*  
  
 *Threadprivate-Direktive*:  
  
 **# Pragma Omp Threadprivate (** *Variablenliste*  **)** *neue-Zeile*  
  
 *Data-Klausel*:  
  
 **Private (** *Variablenliste* **)**  
  
 **Copyprivate (**  *Variablenliste*  **)**  
  
 **Firstprivate (**  *Variablenliste*  **)**  
  
 **Lastprivate (** *Variablenliste*  **)**  
  
 **Shared (** *Variablenliste* **)**  
  
 **Standard (freigegeben)**  
  
 **Standardwert (keine)**  
  
 **Reduzierung (**  *Reduction-Operator*  **:**  *Variablenliste*  **)**  
  
 **Copyin (**  *Variablenliste*  **)**  
  
 *Reduction-Operator*:  
  
 *Einer der*: **+ \* -& ^ & #124; & & & #124; & #124;**  
  
 **/\* in C \*/**  
  
 *Variablenliste*:  
  
 *Bezeichner*  
  
 *Variablenliste* **,** *Bezeichner*  
  
 **/\* in C++ \*/**  
  
 *Variablenliste*:  
  
 *ID-Ausdruck*  
  
 *Variablenliste* **,** *-Id-Ausdruck*