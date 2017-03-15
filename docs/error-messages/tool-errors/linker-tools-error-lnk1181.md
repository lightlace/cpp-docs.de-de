---
title: "Linkertoolfehler LNK1181 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1181"
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Linkertoolfehler LNK1181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eingabedatei 'Dateiname' kann nicht geöffnet werden  
  
 Der Linker kann `filename` nicht finden, da die Datei nicht vorhanden ist oder der Pfad nicht gefunden wird.  
  
 Zu den häufigen Gründen für den Fehler LNK1181 gehören folgende:  
  
-   In der Linkerzeile wird auf `filename` als zusätzliche Abhängigkeit verwiesen, aber die Datei ist nicht vorhanden.  
  
-   Eine **\/LIBPATH**\-Anweisung, die das Verzeichnis angibt, in dem `filename` enthalten ist, fehlt.  
  
 Um die oben genannten Fehler zu beheben, müssen Sie sicherstellen, dass alle Dateien, auf die in der Linkerzeile verwiesen wird, im System vorhanden sind.  Außerdem müssen Sie sicherstellen, dass für jedes Verzeichnis, das eine linkerabhängige Datei enthält, eine **\/LIBPATH**\-Anweisung vorhanden ist.  
  
 Eine weitere mögliche Ursache für LNK1181 ist ein langer Dateiname mit Leerzeichen, der nicht in Anführungszeichen steht.  In diesem Fall wird der Dateiname vom Linker nur bis zum ersten Leerzeichen erkannt, und es wird angenommen, dass die Datei über die Dateierweiterung .obj verfügt.  Beheben Sie dieses Problem, indem Sie den langen Dateinamen \(Dateiname inklusive Pfad\) in Anführungszeichen setzen.  
  
 Weitere Informationen finden Sie unter [LIB\-Dateien als Eingabe für den Linker](../../build/reference/dot-lib-files-as-linker-input.md).  
  
## Siehe auch  
 [\/LIBPATH \(Libpath\-Pfad hinzufügen\)](../../build/reference/libpath-additional-libpath.md)