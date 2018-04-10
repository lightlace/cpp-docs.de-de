---
title: Schwerwiegender Fehler C1060 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c551ed3a6befbf646394929a6bcc6406ea93b19f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="fatal-error-c1060"></a>Schwerwiegender Fehler C1060
Kein verfügbarer Speicher mehr im Heap  
  
 Das Betriebssystem oder die Laufzeitbibliothek können keine Speicheranforderung füllen.  
  
### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Versuchen Sie zum Beheben dieses Fehlers die folgenden Lösungen   
  
1.  Wenn der Compiler auch Fehler gibt [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) und [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), verwenden Sie die [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) Compileroption, um die maximale speicherzuweisung zu senken. Mehr Heapspeicher ist für Ihre Anwendung verfügbar, wenn Sie die verbleibende Speicherzuweisung reduzieren.  
  
     Wenn die [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) -Option bereits festgelegt ist, versuchen Sie es zu entfernen. Der Heap-Speicher ist möglicherweise erschöpft, weil die in der Option angegebene maximale Speicherzuweisung zu hoch ist. Der Compiler verwendet eine Standardgrenze, wenn Sie entfernen die [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) Option.  
  
2.  Wenn Sie auf einer 64-Bit-Plattform kompilieren, verwenden Sie das 64-Bit-Compilertoolset. Informationen finden Sie unter [Vorgehensweise: Aktivieren Sie eine 64-Bit-Visual C++-Toolsets in der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Auf 32-Bit-Windows, versuchen Sie es mit der [/3 GB](http://go.microsoft.com/fwlink/p/?linkid=177831) Switch "Boot.ini".  
  
4.  Vergrößern Sie die Windows-Auslagerungsdatei.  
  
5.  Schließen Sie andere ausgeführte Programme.  
  
6.  Löschen Sie überflüssige Includedateien.  
  
7.  Entfernen Sie unnötige globale Variablen, indem Sie beispielsweise Speicher dynamisch belegen, anstatt ein umfangreiches Array zu deklarieren.  
  
8.  Entfernen Sie nicht benötigte Deklarationen.  
  
9. Teilen Sie die aktuelle Datei in kleinere Dateien auf.