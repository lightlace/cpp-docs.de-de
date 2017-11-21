---
title: C. 2 Regeln | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f0b9c7a74c74f014c9ce8e3873635786fe1e560
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="c2-rules"></a>C.2 Regeln
Die Notation wird im Abschnitt 6.1 der C-standard beschrieben. Dieser Anhang Grammatik zeigt die Erweiterungen der Basissprache-Grammatik für die OpenMP-C- und C++-Direktiven.  
  
 **/\*in C++ (ISO/IEC 14882:1998)\*/**  
  
 *Anweisung Seq*:  
  
 *statement*  
  
 *OpenMP-Direktive*  
  
 *Anweisung Seq-Anweisung*  
  
 *Anweisung Seq-Direktive (OpenMP)*  
  
 **/\*in C90 (ISO/IEC 9899:1990)\*/**  
  
 *statement-list*:  
  
 *statement*  
  
 *OpenMP-Direktive*  
  
 *statement-list-Anweisung*  
  
 *Anweisung-List-Anweisung (OpenMP)*  
  
 **/\*in C99 (ISO/IEC 9899: 1999)\*/**  
  
 *Block-Element*:  
  
 *declaration*  
  
 *statement*  
  
 *OpenMP-Direktive*  
  
 *Anweisung*:  
  
 **/\*Standard-Anweisungen\*/**  
  
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
  
 *strukturierten Block*:  
  
 *statement*  
  
 *Parallel-Konstrukt*:  
  
 *Parallel-Direktive strukturierten block*  
  
 *Parallel-Direktive*:  
  
 **# Pragma Omp parallel***Parallel-Klausel*Optseq *neue-Zeile*   
  
 *Parallel-Klausel*:  
  
 *eindeutige-Parallel-Klausel*  
  
 *Data-Klausel*  
  
 *eindeutige-Parallel-Klausel*:  
  
 **Wenn (** *Ausdruck* **)**  
  
 **Num_threads (** *Ausdruck* **)**  
  
 *für Konstrukt*:  
  
 *für die Richtlinie-iterationsanweisung*  
  
 *für die Richtlinie*:  
  
 **# Pragma Omp für** *for-Klausel*Optseq *neue-Zeile*  
  
 *for-Klausel*:  
  
 *eindeutige-für-Klausel*  
  
 *Data-Klausel*  
  
 **nowait**  
  
 *eindeutige für Klausel*:  
  
 **sortiert**  
  
 **Zeitplan (** *Plantyp* **)**  
  
 **Zeitplan (** *Plantyp* **,** *Ausdruck* **)**  
  
 *Plantyp*:  
  
 **static**  
  
 **dynamic**  
  
 **Einführung**  
  
 **Common Language Runtime**  
  
 *Abschnitte-Konstrukt*:  
  
 *Abschnitte-Direktive Abschnitt-Bereich*  
  
 *Abschnitte-Direktive*:  
  
 **# Pragma Omp Abschnitte** *Abschnitte-Klausel*Optseq *neue-Zeile*  
  
 *Abschnitte-Klausel*:  
  
 *Data-Klausel*  
  
 **nowait**  
  
 *Abschnitt Bereich*:  
  
 *{Abschnitt sequenzielles}*  
  
 *Abschnitt Sequenz*:  
  
 *abschnittsdirektive*opt *strukturierten Block*  
  
 *strukturierte abschnittsdirektive Abschnitt Sequenz-block*  
  
 *abschnittsdirektive*:  
  
 **# Pragma Omp Abschnitt** *neue-Zeile*  
  
 *Single-Konstrukt*:  
  
 *Single-Direktive strukturierten block*  
  
 *Single-Direktive*:  
  
 **# Pragma Omp einzelne** *Single-Klausel*Optseq *neue-Zeile*  
  
 *Single-Klausel*:  
  
 *Data-Klausel*  
  
 **nowait**  
  
 *Parallel-für-Konstrukt*:  
  
 *Parallel-für-Direktive-iterationsanweisung*  
  
 *Parallel-für-Direktive*:  
  
 **# Pragma Omp parallel für** *Parallel-for-Klausel*Optseq *neue-Zeile*  
  
 *Parallel-for-Klausel*:  
  
 *eindeutige-Parallel-Klausel*  
  
 *eindeutige-für-Klausel*  
  
 *Data-Klausel*  
  
 *Parallel-Abschnitten-Konstrukt*:  
  
 *Parallel-Abschnitten-Direktive Abschnitt-Bereich*  
  
 *Parallel-Abschnitten-Direktive*:  
  
 **# Pragma Omp parallel Abschnitte** *Parallel-Abschnitten-Klausel*Optseq *neue-Zeile*  
  
 *Parallel-Abschnitten-Klausel*:  
  
 *eindeutige-Parallel-Klausel*  
  
 *Data-Klausel*  
  
 *Master-Konstrukt*:  
  
 *Master-Direktive strukturierten block*  
  
 *Master-Direktive*:  
  
 **# Pragma Omp Master** *neue-Zeile*  
  
 *Critical-Konstrukt*:  
  
 *Critical-Direktive strukturierten block*  
  
 *Critical-Direktive*:  
  
 **# Pragma Omp kritische** *Region-Satz*opt *neue-Zeile*  
  
 *Region-Satz*:  
  
 *(Bezeichner)*  
  
 *Barrier-Direktive*:  
  
 **# Pragma Omp Barriere** *neue-Zeile*  
  
 *Atomic-Konstrukt*:  
  
 *Ausdrucksanweisung Atomic-Direktive*  
  
 *Atomic-Direktive*:  
  
 **# Pragma Omp atomic** *neue-Zeile*  
  
 *Flush-Direktive*:  
  
 **# Pragma Omp flush** *leeren var*opt *neue-Zeile*  
  
 *Flush-var*:  
  
 *(Variablenliste)*  
  
 *geordnete Konstrukt*:  
  
 *sortiert-Direktive strukturierten block*  
  
 *geordnete Richtlinie*:  
  
 **# Pragma Omp sortiert** *neue-Zeile*  
  
 *Deklaration*:  
  
 **/\*Standard-Deklarationen\*/**  
  
 *Threadprivate-Direktive*  
  
 *Threadprivate-Direktive*:  
  
 **# Pragma Omp Threadprivate (** *Variablenliste***)** *neue-Zeile*   
  
 *Data-Klausel*:  
  
 **Private (** *Variablenliste* **)**  
  
 **Copyprivate (***Variablenliste***)**   
  
 **Firstprivate (***Variablenliste***)**   
  
 **Lastprivate (** *Variablenliste***)**   
  
 **Freigegebene (** *Variablenliste* **)**  
  
 **Standard (freigegeben)**  
  
 **Standard (keine)**  
  
 **Verringerung (***Reduction-Operator***:***Variablenliste***)**   
  
 **Copyin (***Variablenliste***)**   
  
 *Reduction-Operator*:  
  
 *Einer der*:  **+  \* -& ^ &#124; & & &#124; &#124;**  
  
 **/\*in C\*/**  
  
 *Variablenliste*:  
  
 *identifier*  
  
 *Variablenliste* **,** *Bezeichner*  
  
 **/\*in C++\*/**  
  
 *Variablenliste*:  
  
 *ID-Ausdruck*  
  
 *Variablenliste* **,** *-Id-Ausdruck*