---
title: Aufrufkonventionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: bbdee0427dcefc019214e7f9af16831f162cef83
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="calling-conventions"></a>Aufrufkonventionen
Der Compiler für Visual C/C++ stellt mehrere unterschiedliche Konventionen für das Aufrufen von internen und externen Funktionen bereit. Das Verständnis dieser verschiedenen Ansätze hilft Ihnen, Ihr Programm zu debuggen und den Code mit Routinen in Assemblysprache zu verknüpfen.  
  
 In diesen Themen werden die Unterschiede zwischen den Aufrufkonventionen, wie Argumente übergeben werden und wie Werte über Funktionen zurückgegeben werden, erläutert. Es werden auch reine Funktionsaufrufe, eine erweiterte Funktion, die es erlaubt, Ihren eigenen Einleitungs- und Epilogcode zu schreiben, besprochen.  
  
 Informationen zu anderen Aufrufkonventionen für X64-Prozessoren finden Sie unter [Aufrufkonvention](../build/calling-convention.md).  
  
## <a name="topics-in-this-section"></a>Themen in diesem Abschnitt  
  
-   [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md) (`__cdecl`, `__stdcall`, `__fastcall`, usw.)  
  
-   [Aufrufbeispiel:Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)  
  
-   [Verwendung von naked-Funktionsaufrufe, um benutzerdefinierte Prolog-und Epilogcode zu schreiben.](../cpp/naked-function-calls.md)  
  
-   [Gleitkomma-Coprozessor und Aufrufkonventionen](../cpp/floating-point-coprocessor-and-calling-conventions.md)  
  
-   [Veraltete Aufrufkonventionen](../cpp/obsolete-calling-conventions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md)
