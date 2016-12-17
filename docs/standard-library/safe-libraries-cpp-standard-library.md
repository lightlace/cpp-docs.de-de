---
title: "Sichere Bibliotheken: C++-Standardbibliothek"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Sichere Bibliotheken"
  - "Sichere Bibliotheken, C++-Standardbibliothek"
  - "Sichere Standard-C++-Bibliothek"
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Sichere Bibliotheken: C++-Standardbibliothek
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An den mit Visual C\+\+ ausgelieferten Bibliotheken wurden verschiedene Verbesserungen vorgenommen, einschließlich der C\+\+\-Standardbibliothek, um die Sicherheit zu erhöhen.  
  
 Einige Methoden in der C\+\+\-Standardbibliothek wurden als möglicherweise unsicher identifiziert, da sie zu einem Pufferüberlauf oder anderen Codefehlern führen könnten. Von der Verwendung dieser Methoden wird abgeraten, und es wurden neue, sicherere Methoden erstellt, um diese zu ersetzen. Diese neuen Methoden enden alle mit `_s`.  
  
 Zudem wurden verschiedene Verbesserungen vorgenommen, um Iteratoren und Algorithmen sicherer zu gestalten. Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md), [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md) und [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Hinweise  
 In der folgenden Tabelle sind die Methoden der C\+\+\-Standardbibliothek enthalten, die als potenziell unsicher gelten, sowie deren sicherere Entsprechung:  
  
|Potenziell unsichere Methode|Sicherere Entsprechung|  
|----------------------------------|----------------------------|  
|[basic\_string::copy](../Topic/basic_string::copy.md)|[basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md)|  
|[char\_traits::copy](../Topic/char_traits::copy.md)|[char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md)|  
  
 Wenn Sie eine der oben genannten potenziell unsicheren Methoden aufrufen oder die Iteratoren unsachgemäß verwenden, generiert der Compiler eine [Compilerwarnung \(Stufe 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Informationen zum Deaktivieren dieser Warnungen finden Sie unter [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## In diesem Abschnitt  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Überprüfte Iteratoren](../standard-library/checked-iterators.md)  
  
 [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)