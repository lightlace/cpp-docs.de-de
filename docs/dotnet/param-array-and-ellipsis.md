---
title: "Parameterarray und Ellipse"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionsüberladung, Argumentübereinstimmung"
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Parameterarray und Ellipse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Rangfolge des Parameterarrays zum Auflösen von Aufrufen überladener Funktionen hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Sowohl in Managed Extensions als auch in der neuen Syntax gibt es keine explizite Unterstützung des Parameterarrays, das von C\# und [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] unterstützt wird.  Stattdessen wird wie folgt ein gewöhnliches Array mit einem Attribut gekennzeichnet:  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 Während diese beiden Varianten gleich aussehen, kennzeichnet das `ParamArray`\-Attribut dieses Array für C\# oder andere CLR\-Programmiersprachen als ein Array, das bei jedem Aufruf eine unterschiedliche Anzahl von Elementen aufnehmen kann.  Das unterschiedliche Verhalten von Programmen mit Managed Extensions und der neuen Syntax besteht in der Auflösung einer Reihe von Funktionen, in der eine Instanz eine Ellipse deklariert und eine zweite Instanz ein `ParamArray`\-Attribut deklariert, wie das folgende von Artur Laksberg zur Verfügung gestellte Beispiel zeigt.  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 In Managed Extensions hat die Ellipse Vorrang vor dem Attribut. Dies ist angemessen, da das Attribut keinen formalen Aspekt der Programmiersprache darstellt.  In der neuen Syntax wird das Parameterarray jetzt jedoch direkt in der Programmiersprache unterstützt und hat Vorrang vor der Ellipse, da es eine striktere Typbindung hat.  In Managed Extensions wird also der Aufruf  
  
```  
fx( 1, 2 );  
```  
  
 nach `fx(…)` aufgelöst, während er in der neuen Syntax zur `ParamArray`\-Instanz aufgelöst wird.  In dem unwahrscheinlichen Fall, dass das Verhalten des Programms eher vom Aufruf der Ellipseninstanz als vom Aufruf der `ParamArray`\-Instanz abhängt, müssen Sie entweder die Signatur oder den Aufruf ändern.  
  
## Siehe auch  
 [Allgemeine Sprachänderung](../dotnet/general-language-changes-cpp-cli.md)