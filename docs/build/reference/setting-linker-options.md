---
title: "Festlegen von Linkeroptionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dateien [C++], LINK"
  - "Eingabedateien [C++]"
  - "Eingabedateien [C++], Linker"
  - "Linker [C++], Schalter"
  - "Linker [C++], Möglichkeiten zum Festlegen von Optionen"
  - "Objekt-/Bibliotheksmodule"
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Festlegen von Linkeroptionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Linkeroptionen können innerhalb oder außerhalb der Entwicklungsumgebung festgelegt werden.  In den Themen zu den einzelnen Linkeroptionen wird erläutert, wie die jeweilige Option in der Entwicklungsumgebung eingestellt werden kann.  Eine vollständige Liste finden Sie unter [Linkeroptionen](../../build/reference/linker-options.md).  
  
 Wenn Sie **LINK** außerhalb der Entwicklungsumgebung aufrufen, gibt es mehrere Möglichkeiten der Eingabe:  
  
-   [In der Befehlszeile](../../build/reference/linker-command-line-syntax.md)  
  
-   Verwenden von [Befehlsdateien](../../build/reference/link-command-files.md)  
  
-   In [Umgebungsvariablen](../../build/reference/link-environment-variables.md)  
  
 **LINK** verarbeitet zuerst die in der **LINK**\-Umgebungsvariablen angegebenen Optionen, danach die Optionen in der Befehlszeile und in Befehlsdateien in der angegebenen Reihenfolge.  Wenn eine Option mit unterschiedlichen Argumenten wiederholt wird, erhält das zuletzt verarbeitete den Vorrang.  
  
 Optionen werden auf den gesamten Buildvorgang angewendet; es ist nicht möglich, Optionen nur auf bestimmte Eingabedateien anzuwenden.  
  
## Siehe auch  
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)