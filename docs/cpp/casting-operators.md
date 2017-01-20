---
title: "Umwandlungsoperatoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Umwandlungsoperatoren"
  - "Operatoren [C++], Umwandlung von Typen"
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Umwandlungsoperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt mehrere Umwandlungsoperatoren, die spezifisch für die Programmiersprache C\+\+ sind.  Diese Operatoren sind vorgesehen, um einen Teil der Mehrdeutigkeiten und Gefahren zu beseitigen, die Umwandlungen in der C\-Programmiersprache im altem Stil mit sich brachten.  Diese Operatoren sind:  
  
-   [dynamic\_cast](../cpp/dynamic-cast-operator.md) Wird zur Konvertierung von polymorphen Typen verwendet.  
  
-   [static\_cast](../cpp/static-cast-operator.md) Wird für die Konvertierung von nicht polymorphen Typen verwendet.  
  
-   [const\_cast](../cpp/const-cast-operator.md) Wird verwendet, um `const`, `volatile` und `__unaligned`\-Attribute zu entfernen.  
  
-   [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) Für einfache Neuinterpretation von Bits.  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) Wird verwendet, um überprüfbare MSIL zu erzeugen.  
  
 Verwenden Sie `const_cast` und `reinterpret_cast` als letzten Ausweg, da diese Operatoren dieselben Gefahren wie Umwandlungen im alten Stil darstellen.  Allerdings sind sie weiterhin erforderlich, um alte Umwandlungen vollständig zu ersetzen.  
  
## Siehe auch  
 [Umwandlung von Typen](../cpp/casting.md)