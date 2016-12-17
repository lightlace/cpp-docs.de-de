---
title: "Schwerwiegender Fehler C1060"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C1060"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1060"
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1060
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compiler ist außerhalb des Heap\-Speichers  
  
 Das Betriebssystem oder die Laufzeitbibliothek können keine Speicheranforderung füllen.  
  
### Versuchen Sie zum Beheben dieses Fehlers die folgenden Lösungen  
  
1.  Wenn der Compiler auch die Fehler [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)und [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) ausgibt, verwenden Sie die [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)\-Compileroption, um die maximale Speicherzuweisung zu senken.  Mehr Heapspeicher ist für Ihre Anwendung verfügbar, wenn Sie die verbleibende Speicherzuweisung reduzieren.  
  
     Wenn die [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)\-Option bereits festgelegt ist, entfernen Sie sie.  Der Heap\-Speicher ist möglicherweise erschöpft, weil die in der Option angegebene maximale Speicherzuweisung zu hoch ist.  Der Compiler verwendet eine Standardgrenze, wenn Sie die [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)\-Option entfernen.  
  
2.  Wenn Sie auf einer 64\-Bit\-Plattform kompilieren, verwenden Sie das 64\-Bit\-Compilertoolset.  Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren eines 64\-Bit\-Visual C\+\+\-Toolsets auf der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Verwenden Sie auf 32\-Bit\-Windows den [\/3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) Switch "Boot.ini".  
  
4.  Vergrößern Sie die Windows\-Auslagerungsdatei.  
  
5.  Schließen Sie andere ausgeführte Programme.  
  
6.  Löschen Sie überflüssige Includedateien.  
  
7.  Entfernen Sie unnötige globale Variablen, indem Sie beispielsweise Speicher dynamisch belegen, anstatt ein umfangreiches Array zu deklarieren.  
  
8.  Entfernen Sie nicht benötigte Deklarationen.  
  
9. Teilen Sie die aktuelle Datei in kleinere Dateien auf.