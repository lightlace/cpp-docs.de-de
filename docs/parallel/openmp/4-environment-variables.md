---
title: 4. Umgebungsvariablen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cef1bac78afbcc8b852c3bd42e0904e1963137c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="4-environment-variables"></a>4. Umgebungsvariablen
In diesem Kapitel wird beschrieben, die Umgebungsvariablen OpenMP-C- und C++-API (oder die entsprechende plattformspezifische Mechanismen), die die Ausführung des parallelen Code steuern.  Die Namen der Umgebungsvariablen müssen in Großbuchstaben angegeben werden. Die Werte, die ihnen zugewiesen werden Groß-/Kleinschreibung und möglicherweise führende und nachfolgende Leerzeichen.  Änderungen der Werte aus, nachdem das Programm gestartet wurde, werden ignoriert.  
  
 Die Umgebungsvariablen sind wie folgt aus:  
  
-   **OMP_SCHEDULE** legt die Laufzeit-Zeitplan Typ und Segment Größe fest.  
  
-   **OMP_NUM_THREADS** legt die Anzahl der Threads an, die während der Ausführung verwenden.  
  
-   **OMP_DYNAMIC** aktiviert oder deaktiviert die dynamische Anpassung der Anzahl von Threads.  
  
-   **OMP_NESTED** aktiviert oder deaktiviert die geschachtelten Parallelität.  
  
 In den Beispielen in diesem Kapitel wird nur veranschaulichen, wie diese Variablen in Unix C-Shell (Csh)-Umgebungen festgelegt werden können. In Korn ähneln sich Shell und DOS-Umgebungen die Aktionen, wie folgt:  
  
 Csh:  
 Setenv OMP_SCHEDULE "dynamisch"  
  
 Ksh:  
 Exportieren Sie OMP_SCHEDULE = "dynamic"  
  
 DOS:  
 Legen Sie OMP_SCHEDULE = "dynamic"