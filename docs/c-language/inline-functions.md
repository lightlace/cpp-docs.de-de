---
title: Inlinefunktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 1ef83efdde0a8227ce1a5aa76f2b38816bc96023
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="inline-functions"></a>Inlinefunktionen
**Microsoft-spezifisch**  
  
 Das `__inline`-Schlüsselwort weist den Compiler an, den Code in der Funktionsdefinition für jede Instanz eines Funktionsaufrufs zu ersetzen. Die Ersetzung wird allerdings nur nach Ermessen des Compilers ausgeführt. Zum Beispiel führt der Compiler eine Funktion nicht inline aus, wenn ihre Adresse akzeptiert wird oder wenn sie für den Inlinevorgang zu groß ist.  
  
 Damit eine Funktion als Kandidat für das Inlining in Betracht gezogen werden kann, muss sie die neue Funktionsdefinition verwenden.  
  
 Verwenden Sie dieses Format, um eine Inlinefunktion anzugeben:  
  
 `__inline` *Typ*Option*Funktionsdefinition*`;`  
  
 Die Verwendung von Inlinefunktionen generiert einen schnelleren Code und kann manchmal auch kleineren Code generierten als der entsprechende Funktionsaufruf. Das hat folgende Gründe:  
  
-   Die Zeit, die erforderlich ist, um Funktionsaufrufe ausführen, wird gespart.  
  
-   Kleine Inlinefunktionen, etwa drei Zeilen oder weniger, erstellen weniger Code als der entsprechende Funktionsaufruf, da der Compiler keinen Code generiert, um Argumente und einen Rückgabewert zu behandeln.  
  
-   Inline generierte Funktionen werden Codeoptimierungen unterzogen, die für normale Funktionen nicht verfügbar sind, da der Compiler keine interprozeduralen Optimierungen durchführt.  
  
 Funktionen, die `__inline` verwenden, sollten nicht mit Inlineassemblercode verwechselt werden. Weitere Informationen finden Sie unter [Inlineassembler](../c-language/inline-assembler-c.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [inline, __inline, \__forceinline](../cpp/inline-functions-cpp.md)


