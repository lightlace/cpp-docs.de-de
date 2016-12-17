---
title: "Klassen und Strukturen (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++]"
  - "Strukturen, C++-Klassen"
  - "Benutzerdefinierte Typen"
  - "Benutzerdefinierte Typen, C++-Klassen"
  - "Visual C++, Klassen"
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Klassen und Strukturen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt werden die C\+\+\-Klassen und \-Strukturen vorgestellt.  Die zwei Konstrukte sind identisch in C\+\+. Der Unterschied besteht jedoch darin, dass der Standardzugriff in Strukturen öffentlich ist, während der Standard in Klassen privat ist.  
  
```  
  
```  
  
 Klassen und Strukturen sind die Konstrukte, anhand denen Sie Ihre eigenen Typen definieren.  Klassen und Strukturen können Datenmember und Memberfunktionen enthalten. Mit diesen können Sie den Status und das Verhalten des Typs beschreiben.  
  
 Es sind folgende Themen enthalten:  
  
-   [Klasse](../cpp/class-cpp.md)  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [Übersicht über Klassenmember](../cpp/class-member-overview.md)  
  
-   [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md)  
  
-   [Vererbung](../cpp/inheritance-cpp.md)  
  
-   [Statische Member](../cpp/static-members-cpp.md)  
  
-   [Konvertierungen](../cpp/user-defined-type-conversions-cpp.md)  
  
-   [Änderbare Datenmember \(mutable Spezifizierer\)](../cpp/mutable-data-members-cpp.md)  
  
-   [Geschachtelte Klassendeklarationen](../cpp/nested-class-declarations.md)  
  
-   [Anonyme Klassentypen](../cpp/anonymous-class-types.md)  
  
-   [Zeiger auf Member](../cpp/pointers-to-members.md)  
  
-   [this\-Zeiger](../cpp/this-pointer.md)  
  
-   [C\+\+\-Bitfelder](../cpp/cpp-bit-fields.md)  
  
 Die drei Klassentypen sind "structure", "class" und "union".  Sie werden mithilfe der Schlüsselwörter [struct](../cpp/struct-cpp.md), [class](../cpp/class-cpp.md) und [union](../cpp/unions.md) deklariert \(siehe [Definieren von Klassentypen](assetId:///e8c65425-0f3a-4dca-afc2-418c3b1e57da)\).  In der folgenden Tabelle werden die Unterschiede zwischen den drei Klassentypen gezeigt.  
  
 Weitere Informationen zu Unions finden Sie unter [Unions](../cpp/unions.md).  Weitere Informationen über verwaltete Klassen und Strukturen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
### Zugriffssteuerung und Einschränkungen von Strukturen, Klassen und Unions  
  
|Strukturen|Klassen|Unions|  
|----------------|-------------|------------|  
|Klassenschlüssel ist `struct`|Klassenschlüssel ist **class**|Klassenschlüssel ist **union**|  
|Der Standardzugriff ist öffentlich.|Der Standardzugriff ist privat.|Der Standardzugriff ist öffentlich.|  
|Keine Verwendungseinschränkungen|Keine Verwendungseinschränkungen|Verwenden Sie jeweils nur einen Member.|  
  
## Siehe auch  
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)