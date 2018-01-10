---
title: Aufrufkonventionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d2b5dbd0821516f5de1d05bc2069ee165e762241
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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