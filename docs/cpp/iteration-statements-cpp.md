---
title: Iterationsanweisungen (C++) | Microsoft Docs
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
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c06ae1c043551bbb4ed6469ab3f87d1ed86fd92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iteration-statements-c"></a>Iterationsanweisungen (C++)
Iterationsanweisungen bewirken, dass Anweisungen (oder Verbundanweisungen) NULL mal oder mehrmals ausgeführt werden, je nach LOOP-Beendigungskriterien. Wenn diese Anweisungen verbundanweisungen sind, sie werden nacheinander ausgeführt, außer wenn entweder die [Break](../cpp/break-statement-cpp.md) Anweisung oder der [weiterhin](../cpp/continue-statement-cpp.md) Anweisung gefunden wird.  
  
 C++ stellt vier iterationsanweisungen bereit – [während](../cpp/while-statement-cpp.md), [führen](../cpp/do-while-statement-cpp.md), [für](../cpp/for-statement-cpp.md), und [bereichsbasierter for](../cpp/range-based-for-statement-cpp.md). Jede dieser durchläuft, bis der beendigungsausdruck mit Null (False) ausgewertet wird oder der erzwungenen Beendigung der Schleife mit einer **Break** Anweisung. In der folgenden Tabelle werden diese Anweisungen und ihre Aktionen zusammengefasst. Jede von ihnen wird in den folgenden Abschnitten im Detail behandelt.  
  
### <a name="iteration-statements"></a>Iterationsanweisungen  
  
|Anweisung|Ausgewertet an|Initialisierung|Inkrement|  
|---------------|------------------|--------------------|---------------|  
|`while`|Anfang der Schleife|Nein|Nein|  
|**do**|Ende der Schleife|Nein|Nein|  
|**for**|Anfang der Schleife|Ja|Ja|  
|**bereichsbasierte for**|Anfang der Schleife|Ja|Ja|  
  
 Der Anweisungsteil einer Iterationsanweisung kann keine Deklaration sein. Es kann jedoch eine Verbundanweisung sein, die eine Deklaration enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über C++-Anweisungen](../cpp/overview-of-cpp-statements.md)