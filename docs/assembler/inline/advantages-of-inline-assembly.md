---
title: Vorteile von Inlineassemblys | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60b8d458212cd2175f2460c1382ed7f8c2c269bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="advantages-of-inline-assembly"></a>Vorteile von Inlineassemblys
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Da der Inlineassembler keine separaten Assembly- und Verknüpfungsschritte erfordert, ist er einfacher als ein getrennter Assembler. Der Inlineassemblycode kann alle C-Variablen und -Funktionsnamen verwenden, die sich im Gültigkeitsbereich befinden. Daher ist es einfach, ihn in den C-Programmcode zu integrieren. Da der Assemblycode Inline mit C- oder C++-Anweisungen kombiniert werden, kann, können sie Aufgaben ausführen, die in C oder C++ mühsam oder unmöglich sind.  
  
 Die Verwendungsmöglichkeiten von Inlineassemblys aufgeführt:  
  
-   Schreiben von Funktionen in der Assemblysprache.  
  
-   Optimieren der Stelle Geschwindigkeit kritische Abschnitte des Codes.  
  
-   Machen direkten Hardwarezugriff für Gerätetreiber.  
  
-   Schreiben von Prolog- und Epilogcode Code für "naked" aufrufen.  
  
 Inlineassembly ist ein spezielles Tool. Wenn Sie beabsichtigen, eine Anwendung auf verschiedenen Computern zu portieren, möchten Sie wahrscheinlich in einem separaten Modul computerspezifische Code platzieren. Da der Inlineassembler aller Microsoft Macro Assembler (MASM) unterstützt keine Direktiven-Makro und Daten, Sie könnten praktischerweise mehr MASM für solche Module zu verwenden.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)