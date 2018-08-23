---
title: Präprozessor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 980058c588e02751113b889d44cf0bb5f69066f1
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538629"
---
# <a name="preprocessor"></a>Präprozessor
Der Präprozessor ist ein Textprozessor, der den Text einer Quelldatei im Rahmen der ersten Übersetzungsphase bearbeitet. Der Präprozessor analysiert den Quelltext zwar nicht, teilt ihn jedoch in Token auf, um Makroaufrufe zu finden. Obwohl der Compiler den Präprozessor normalerweise im ersten Durchlauf aufruft, kann der Präprozessor auch separat aufgerufen werden, um Text ohne Kompilierung zu verarbeiten.  
  
Das Referenzmaterial zum Präprozessor enthält die folgenden Abschnitte:  
  
- [Präprozessoranweisungen](../preprocessor/preprocessor-directives.md)  
  
- [Präprozessor-Operatoren](../preprocessor/preprocessor-operators.md)  
  
- [Vordefinierte Makros](../preprocessor/predefined-macros.md)  
  
- [Pragmas](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
  
**Microsoft-spezifisch**  
  
Sie erhalten eine Liste des Quellcodes nach der vorverarbeitung mithilfe der [/e](../build/reference/e-preprocess-to-stdout.md) oder [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) -Compileroption. Beide Optionen rufen den Präprozessor auf und geben den daraus resultierenden Text auf dem Standardausgabegerät aus, was in den meisten Fällen die Konsole ist. Der Unterschied zwischen beiden Optionen ist, dass /E `#line`-Direktive enthält und /EP diese Direktive entfernt.  
  
**Ende Microsoft-spezifisch**  
  
##  <a name="_predir_special_terminology"></a> Besondere Terminologie  

In der Präprozessordokumentation bezieht sich der Begriff „Argument“ auf die Entität, die an eine Funktion übergeben wird. In einigen Fällen wird diese durch "tatsächlich" oder "formal" modifiziert, womit der Argumentausdruck, der im Funktionsaufruf angegeben wird, bzw. die Argumentdeklaration, die in der Funktionsdefinition festgelegt wird, beschrieben wird.  
  
Der Begriff "Variable" bezeichnet ein einfaches C-Datenobjekt. Der Begriff "Objekt" verweist auf beides, C++-Objekte und Variablen. Es handelt sich um einen inklusiven Begriff.  
  
## <a name="see-also"></a>Siehe auch  
 
[C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)   
[Phasen der Übersetzung](../preprocessor/phases-of-translation.md)