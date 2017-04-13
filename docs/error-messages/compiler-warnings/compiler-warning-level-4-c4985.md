---
title: Compilerwarnung (Stufe 4) C4985 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4a36692420ea9d5547f236c1e5dfeaa269afbb67
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4985"></a>Compilerwarnung (Stufe 4) C4985
"Symbolname": Attribute sind in vorheriger Deklaration nicht vorhanden.  
  
 Die Microsoft SAL-Anmerkungen (Source Code Annotation Language, Quellcodeanmerkungssprache) zur aktuellen Methodendeklaration oder -definition unterscheiden sich von den Anmerkungen zu einer früheren Deklaration. In der Definition und den Deklarationen einer Methode müssen dieselben SAL-Anmerkungen verwendet werden.  
  
 Die SAL stellt einen Satz Anmerkungen bereit, mit denen Sie beschreiben können, wie eine Funktion ihre Parameter verwendet, welche Annahmen sie über diese Parameter trifft, und wie ihr garantierte Ergebnis aussieht, wenn sie abgeschlossen wird. Die Anmerkungen sind in der Headerdatei „sal.h“ definiert.  
  
 Beachten Sie, die die SAL-Makros nicht erweitert werden, es sei denn, das Projekt verfügt über die [/ analyze](../../build/reference/analyze-code-analysis.md) Flag angegeben. Wenn Sie **/analyze**angeben, kann der Compiler C4985 auslösen, selbst wenn ohne **/analyze**keine Warnungen oder Fehler angezeigt würden.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verwenden Sie für die Definition einer Methode und deren Deklarationen dieselben SAL-Anmerkungen.  
  
## <a name="see-also"></a>Siehe auch  
 [SAL-Anmerkungen](../../c-runtime-library/sal-annotations.md)
