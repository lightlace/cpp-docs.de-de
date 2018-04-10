---
title: Parameterarray und Ellipse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function overloading, argument matching
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f6d256fd48d8c9f206619e6baa9a50a0278d30c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="param-array-and-ellipsis"></a>Parameterarray und Ellipse
Rangfolge des Parameterarrays zum Auflösen von Aufrufen überladener Funktionen wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 In Managed Extensions und der neuen Syntax ist es keine explizite Unterstützung für das Parameterarray, das C#- und Visual Basic unterstützen. Stattdessen kennzeichnet eine ein normales Array mit einem Attribut wie folgt:  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 Während beide gleich, suchen Sie die `ParamArray` Attribut kennzeichnet dieses für C#- oder andere CLR-Programmiersprachen als ein Array, eine Variable Anzahl von Elementen mit jedem Aufruf aufnehmen. Die Änderung im Verhalten von Programmen mit Managed Extensions und der neuen Syntax wird in die Auflösung einer überladenen Funktion legen Sie in der eine Instanz eine Ellipse deklariert und eine zweite deklariert eine `ParamArray` -Attribut, wie im folgenden Beispiel bereitgestellt von Artur Laksberg.  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 In Managed Extensions wurde mit der Auslassungspunkten Vorrang vor mit dem Attribut angegeben, die sinnvoll ist, da das Attribut nicht über eine formale Aspekt der Sprache ist. Allerdings in der neuen Syntax Parameterarrays ist jetzt direkt in der Sprache unterstützt, und wird Vorrang vor über die Schaltfläche angegeben werden, da es mehr stark typisiert ist. Folglich in Managed Extensions wird der Aufruf  
  
```  
fx( 1, 2 );  
```  
  
 Löst in `fx(...)` klicken Sie in der neuen Syntax wird löst die `ParamArray` Instanz. Fall, der das Verhalten des Programms über die auf den Aufruf der Instanz mit den Auslassungspunkten abhängig ist die `ParamArray`, müssen Sie die Signatur oder der Aufruf zu ändern.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)