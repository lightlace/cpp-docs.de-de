---
title: 4. Umgebungsvariablen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5fcd308f21d66535a983e70506fe91afb5c7042f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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