---
title: "Linkertoolfehler LNK1211 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1211"
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Linkertoolfehler LNK1211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vorkompilierte Typinformationen nicht gefunden; 'Dateiname' ist nicht verknüpft oder überschrieben  
  
 Die angegebene Objektdatei, die mit [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) kompiliert wurde, wurde entweder nicht im LINK\-Befehl angegeben oder überschrieben.  
  
 Wenn Sie eine Debugbibliothek erstellen, die vorkompilierte Header verwendet, und **\/Yc** sowie [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) festlegen, erstellt Visual C\+\+ eine vorkompilierte Objektdatei, die Debuginformationen zur Codeansicht enthält.  Der Fehler tritt nur dann auf, wenn Sie die vorkompilierte Objektdatei in einer Bibliothek speichern, die Bibliothek zur Erstellung einer ausführbaren Anwendung verwenden, und wenn die Objektdateien, auf die verwiesen wird, keine transitiven Verweise auf eine Funktion haben, die durch die vorkompilierte Objektdatei definiert wird.  
  
 Es gibt zwei Methoden, um diese Situation zu umgehen:  
  
-   Sie geben die [\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)\-Compileroption an, um die Codeansichtsinformationen aus dem vorkompilierten Header in jedes einzelne Objektmodul einzufügen.  Diese Methode ist weniger empfehlenswert, da hierdurch in der Regel große Objektmodule erstellt werden. Diese können den Zeitaufwand erhöhen, der zum Verknüpfen der Anwendung erforderlich ist.  
  
-   Sie geben [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) an und übergeben den Namen einer beliebigen Zeichenfolge, wenn Sie eine vorkompilierte Headerdatei erstellen, die keine Funktionsdefinitionen enthält.  Dadurch wird der Compiler angewiesen, ein Symbol in der vorkompilierten Objektdatei sowie einen Verweis auf dieses Symbol in jeder Objektdatei zu erstellen, die die mit der vorkompilierten Objektdatei verknüpfte, vorkompilierte Headerdatei verwendet hat.  
  
 Wenn Sie ein Modul mit **\/Yc** und **\/Yl** kompilieren, erstellt der Compiler ein mit `__@@_PchSym_@00@...@symbol_name` vergleichbares Symbol und speichert es im Objektmodul. Die Auslassungszeichen \(...\) stellen dabei eine vom Compiler generierte Zeichenfolge dar.  Jede mit diesem vorkompilierten Header kompilierte Quelldatei bezieht sich auf das angegebene Symbol. Dies bewirkt, dass das Objektmodul und die dazugehörigen Debuginformationen aus der Bibliothek vom Linker eingebunden werden.  
  
 Weitere Informationen zu diesem Fehler finden Sie im Knowledge Base\-Artikel Q102697 "PRB: Build Errors Using Precompiled Header in Debugging Lib" \(nur auf Englisch verfügbar\).