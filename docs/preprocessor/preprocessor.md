---
title: "Präprozessor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ac8f12739493b07d8dacf782fb6355aa02b64a17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="preprocessor"></a>Präprozessor
Der Präprozessor ist ein Textprozessor, der den Text einer Quelldatei im Rahmen der ersten Übersetzungsphase bearbeitet. Der Präprozessor analysiert den Quelltext zwar nicht, teilt ihn jedoch in Token auf, um Makroaufrufe zu finden. Obwohl der Compiler den Präprozessor normalerweise im ersten Durchlauf aufruft, kann der Präprozessor auch separat aufgerufen werden, um Text ohne Kompilierung zu verarbeiten.  
  
 Das Referenzmaterial zum Präprozessor enthält die folgenden Abschnitte:  
  
-   [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)  
  
-   [Präprozessor-Operatoren](../preprocessor/preprocessor-operators.md)  
  
-   [Vordefinierte Makros](../preprocessor/predefined-macros.md)  
  
-   [Pragmas](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
  
 **Microsoft-spezifisch**  
  
 Sie erhalten eine Liste der Quellcode nach der vorverarbeitung mithilfe der [/e](../build/reference/e-preprocess-to-stdout.md) oder [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) -Compileroption. Beide Optionen rufen den Präprozessor auf und geben den daraus resultierenden Text auf dem Standardausgabegerät aus, was in den meisten Fällen die Konsole ist. Der Unterschied zwischen beiden Optionen ist, dass /E `#line`-Direktive enthält und /EP diese Direktive entfernt.  
  
 **Ende Microsoft-spezifisch**  
  
##  <a name="_predir_special_terminology"></a>Besondere Terminologie  
 In der Präprozessordokumentation bezieht sich der Begriff „Argument“ auf die Entität, die an eine Funktion übergeben wird. In einigen Fällen wird diese durch "tatsächlich" oder "formal" modifiziert, womit der Argumentausdruck, der im Funktionsaufruf angegeben wird, bzw. die Argumentdeklaration, die in der Funktionsdefinition festgelegt wird, beschrieben wird.  
  
 Der Begriff "Variable" bezeichnet ein einfaches C-Datenobjekt. Der Begriff "Objekt" verweist auf beides, C++-Objekte und Variablen. Es handelt sich um einen inklusiven Begriff.  
  
## <a name="see-also"></a>Siehe auch  
 [C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Phasen der Übersetzung](../preprocessor/phases-of-translation.md)