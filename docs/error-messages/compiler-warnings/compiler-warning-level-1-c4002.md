---
title: Compilerwarnung (Stufe 1) C4002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4002
dev_langs:
- C++
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa1943000becde663fbb0da445f861f408f01f9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4002"></a>Compilerwarnung (Stufe 1) C4002
Zu viele übergebene Parameter für das Makro "Bezeichner"  
  
 Die Anzahl der tatsächlich im Makro enthaltenen Parameter überschreitet die Anzahl der formalen Parameter in der Makrodefinition. Der Präprozessor erfasst die zusätzlichen Parameter, aber ignoriert diese bei der Makroerweiterung.  
  
 C4002 kann bei falscher Verwendung von [Variadic Macros](../../preprocessor/variadic-macros.md)auftreten.  
  
 Im folgenden Beispiel wird C4002 generiert:  
  
```  
// C4002.cpp  
// compile with: /W1  
#define test(a) (a)  
  
int main() {  
   int a = 1;  
   int b = 2;  
   a = test(a,b);   // C4002  
   // try..  
   a = test(a);  
}  
```  
  
 Dieser Fehler kann auch infolge einer Konformitätsverbesserung für Compiler für Visual Studio .NET 2003 auftreten: Zusätzliche Kommas in Makros werden nicht mehr akzeptiert.  
  
 Zusätzliche Kommas in Makros werden vom Compiler nicht mehr akzeptiert. Entfernen Sie zusätzliche Kommas, damit der Code in den Visual Studio .NET 2003- und Visual Studio .NET-Versionen von Visual C++ gültig ist.  
  
```  
// C4002b.cpp  
// compile with: /W1  
#define F(x,y)  
int main()  
{  
   F(2,,,,,,3,,,,,,)   // C4002  
   // Try the following line instead:  
   // F(2,3)  
}  
```