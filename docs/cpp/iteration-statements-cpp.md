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
caps.latest.revision: 8
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
ms.openlocfilehash: e00939a9ff383be4cf84c098ee7e93af307a1536
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
