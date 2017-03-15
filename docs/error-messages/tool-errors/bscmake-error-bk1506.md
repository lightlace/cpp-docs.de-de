---
title: "BSCMAKE-Fehler BK1506 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1506"
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# BSCMAKE-Fehler BK1506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Datei "Dateiname" kann nicht geöffnet werden \[: Grund\]  
  
 BSCMAKE kann die Datei nicht öffnen.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Datei ist von einem anderen Prozess gesperrt.  Wenn *Grund* **Berechtigung verweigert** lautet, verwendet der Browser möglicherweise die Datei.  Schließen Sie in diesem Falle das Browserfenster, und versuchen Sie erneut, das Build auszuführen.  
  
2.  Ein voller Datenträger.  
  
3.  Ein Hardwarefehler.  
  
4.  Die angegebene Ausgabedatei besitzt den gleichen Namen wie ein vorhandenes Unterverzeichnis.