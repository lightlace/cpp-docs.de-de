---
title: "Pr&#228;prozessor"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Präprozessor"
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Pr&#228;prozessor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Präprozessor ist ein Textprozessor, der den Text einer Quelldatei im Rahmen der ersten Übersetzungsphase bearbeitet.  Der Präprozessor analysiert den Quelltext zwar nicht, teilt ihn jedoch in Token auf, um Makroaufrufe zu finden.  Obwohl der Compiler den Präprozessor normalerweise im ersten Durchlauf aufruft, kann der Präprozessor auch separat aufgerufen werden, um Text ohne Kompilierung zu verarbeiten.  
  
 Das Referenzmaterial zum Präprozessor enthält die folgenden Abschnitte:  
  
-   [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)  
  
-   [Präprozessor\-Operatoren](../preprocessor/preprocessor-operators.md)  
  
-   [Vordefinierte Makros](../preprocessor/predefined-macros.md)  
  
-   [Pragmas](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
  
 **Microsoft\-spezifisch**  
  
 Mit der [\/E](../build/reference/e-preprocess-to-stdout.md)\- oder [\/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)\-Compileroption können Sie eine Liste des Quellcodes nach der Vorverarbeitung abrufen.  Beide Optionen rufen den Präprozessor auf und geben den daraus resultierenden Text auf dem Standardausgabegerät aus, was in den meisten Fällen die Konsole ist.  Der Unterschied zwischen beiden Optionen ist, dass \/E `#line`\-Direktive enthält und \/EP diese Direktive entfernt.  
  
 **END Microsoft\-spezifisch**  
  
##  <a name="_predir_special_terminology"></a> Besondere Terminologie  
 In der Präprozessordokumentation bezieht sich der Begriff "Argument" auf die Entität, die an eine Funktion übergeben wird.  In einigen Fällen wird diese durch "tatsächlich" oder "formal" modifiziert, womit der Argumentausdruck, der im Funktionsaufruf angegeben wird, bzw. die Argumentdeklaration, die in der Funktionsdefinition festgelegt wird, beschrieben wird.  
  
 Der Begriff "Variable" bezeichnet ein einfaches C\-Datenobjekt.  Der Begriff "Objekt" verweist auf beides, C\+\+\-Objekte und Variablen. Es handelt sich um einen inklusiven Begriff.  
  
## Siehe auch  
 [C\/C\+\+\-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Phasen der Übersetzung](../preprocessor/phases-of-translation.md)