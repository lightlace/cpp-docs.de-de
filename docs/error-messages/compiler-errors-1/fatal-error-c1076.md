---
title: "Schwerwiegender Fehler C1076 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1076"
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Schwerwiegender Fehler C1076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Interne Heapgrenze erreicht; Verwenden Sie \/Zm, um eine höhere Grenze anzugeben  
  
 Dieser Fehler kann durch zu viele Symbole oder Vorlageninstanziierungen verursacht werden.  
  
 So beheben Sie diesen Fehler:  
  
1.  Verwenden Sie die Option [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md), um das Arbeitsspeicherlimit des Compilers auf den in der Fehlermeldung [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) angegebenen Wert festzulegen.  Weitere Informationen über die Festlegung des Werts in [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] finden Sie im Abschnitt "Hinweise" unter [\/Zm \(Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen\)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).  
  
2.  Verwenden Sie in einem 64\-Bit\-Betriebssystem anstelle von gehosteten 32\-Bit\-Compilern gehostete 64\-Bit\-Compiler.  Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren eines 64\-Bit\-Visual C\+\+\-Toolsets auf der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Löschen Sie überflüssige Includedateien.  
  
4.  Entfernen Sie unnötige globale Variablen, indem Sie beispielsweise Speicher dynamisch belegen, anstatt ein umfangreiches Array zu deklarieren.  
  
5.  Entfernen Sie nicht benötigte Deklarationen.  
  
6.  Teilen Sie umfangreichere Funktionen in kleinere Funktionen auf.  
  
7.  Teilen Sie umfangreichere Klassen in kleinere Klassen auf.  
  
8.  Teilen Sie die aktuelle Datei in kleinere Dateien auf.  
  
 Wenn C1076 unmittelbar nach dem Start des Buildvorgangs auftritt, ist der für **\/Zm** festgelegte Wert u. U. zu hoch für das Programm.  Verringern Sie den **\/Zm**\-Wert.