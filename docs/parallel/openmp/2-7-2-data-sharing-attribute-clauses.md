---
title: "2.7.2 Data-Sharing Attribute Clauses"
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
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2 Data-Sharing Attribute Clauses
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mehrere Direktiven akzeptieren Klauseln, die einem Benutzer ermöglichen, die Freigabe von Attributen von Variablen für die Dauer des Bereichs zu steuern.  Freigeben klauseln Attribut gelten nur für Variablen im lexikalischen Wertebereich der Direktiven an, auf denen die Klausel wird.  Nicht alle nachfolgenden Klauseln sind auf allen Direktive ermöglicht.  Die Liste der Klauseln, die für bestimmte \- Direktive gültig sind, werden mit der Direktive beschrieben.  
  
 Wenn eine Variable sichtbar ist, wenn eine Ähnlichkeit oder Arbeitsteilungs konstrukt unterbrochen wird und die Variable nicht in einer Freigabe oder clause Attribut **threadprivate**\-Direktive angegeben ist, wird die Variable freigegeben.  Die statischen Variablen, die innerhalb des dynamischen Wertebereichs eines parallelen Bereichs deklariert wurden, werden freigegeben.  Heap belegter Speicher \(z. B. mithilfe **malloc \(\)** in C oder C\+\+ oder des Operators **neu** C\+\+\) wurde aufgehoben.  \(Der Zeiger auf diesen Speicher kann jedoch privat oder freigegeben sein.\) Variablen mit dauer die automatische Speicherung dynamischer, die innerhalb des Wertebereichs eines parallelen Bereichs deklarierter sind privat.  
  
 Die meisten Klauseln akzeptieren ein *Variable Liste*\-Argument, das eine durch Trennzeichen getrennte Liste von Variablen ist, die sichtbar sind.  Wenn eine Variable, die in eine Datenfreigabe Attribut für clause verwiesen wird, einen Typ aufweist, der aus einer Vorlage abgeleitet ist und keine weiteren Verweise auf den vorhanden ist, der im Programm variabel ist, ist das Verhalten nicht definiert.  
  
 Alle Variablen, die innerhalb der Klauseln angegeben werden, müssen sichtbar sein.  Klauseln nach Bedarf wiederholt werden, aber keine Variable wurde in mehr als einer Klausel angegeben, außer dass eine Variable kann in **firstprivate** und in einer **lastprivate**\-Klausel angegeben werden.  
  
 In den folgenden Abschnitten werden die Datenfreigabe Attribut für klauseln:  
  
-   **private**, [2.7.2.1 Abschnitt](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25.  
  
-   **firstprivate**, [2.7.2.2 Abschnitt](../../parallel/openmp/2-7-2-2-firstprivate.md) auf Seite 26.  
  
-   **lastprivate**, [2.7.2.3 Abschnitt](../../parallel/openmp/2-7-2-3-lastprivate.md) auf Seite 27.  
  
-   **Shared**, [2.7.2.4 Abschnitt](../../parallel/openmp/2-7-2-4-shared.md) auf Seite 27.  
  
-   **Standardwert**, [2.7.2.5 Abschnitt](../../parallel/openmp/2-7-2-5-default.md) auf Seite 28.  
  
-   **Verringerung**, [2.7.2.6 Abschnitt](../../parallel/openmp/2-7-2-6-reduction.md) auf Seite 28.  
  
-   **copyin**, [2.7.2.7 Abschnitt](../../parallel/openmp/2-7-2-7-copyin.md) auf Seite 31.  
  
-   **copyprivate**, [2.7.2.8 Abschnitt](../../parallel/openmp/2-7-2-8-copyprivate.md) auf Seite 32.