---
title: "1.4 Kompatibilit&#228;t"
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
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 1.4 Kompatibilit&#228;t
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Implementierung der OpenMP-C/C++-API ist *OpenMP-kompatible* wenn es erkennt und behält die Semantik der alle Elemente dieser Spezifikation ist, wie in Kapitel 1, 2, 3, 4, angeordnet und Anhang C. Anhänge A, B, D, E und F dienen nur zu Informationszwecken und sind nicht Teil der Spezifikation. Implementierungen, die nur eine Teilmenge der API enthalten sind nicht in der OpenMP-kompatibel.  
  
 OpenMP-C- und C++-API ist eine Erweiterung für die Ausgangssprache, die von einer Implementierung unterstützt wird. Wenn die Ausgangssprache nicht unterstützt ein Sprachkonstrukt oder eine Erweiterung, die angezeigt wird in diesem Dokument, muss die OpenMP-Implementierung nicht unterstützt.  
  
 Alle C- und C++-Standardbibliotheksfunktionen und integrierte Funktionen (d. h. Funktionen, die von denen der Compiler verfügt über genaue Kenntnisse) muss threadsicher sein. Nicht synchronisierte Verwendung der Thread-sichere Funktionen von anderen Threads in einem parallelen Bereich erzeugt keine nicht definiertes Verhalten. Jedoch das Verhalten anders als eine serielle Region möglicherweise nicht. (Eine zufällige Zahl Generierungsfunktion ist ein Beispiel.)  
  
 OpenMP-C/C++-API gibt an, dass bestimmte Verhalten *Implementierung definiert.* Eine kompatible Implementierung der OpenMP ist das Definieren und dokumentieren ihr Verhalten in diesen Fällen erforderlich. Finden Sie unter [Anhang E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), Seite 97, eine Liste der Implementierung definierten Verhalten.