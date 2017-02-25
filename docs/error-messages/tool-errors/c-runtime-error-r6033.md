---
title: "C-Laufzeitfehler R6033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6033"
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# C-Laufzeitfehler R6033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es wurde versucht, während der Initialisierung von prozessorspezifischem Maschinencode MSIL\-Code aus dieser Assembly zu verwenden.Dies weist auf einen Fehler in der Anwendung hin.Höchstwahrscheinlich ist er auf den Aufruf einer MSIL\-kompilierten \(\/clr\) Funktion durch einen Konstruktor im prozessorspezifischen Maschinencode oder aus DllMain zurückzuführen.  
  
 Diese Diagnose zeigt an, dass MSIL\-Anweisungen während der Ladeprogrammsperre ausgeführt wurden.  Weitere Informationen finden Sie unter [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md).