---
title: Compilerfehler C3366 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c26bfbb5d66ad22484184bd361f14004ed8aa30c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254273"
---
# <a name="compiler-error-c3366"></a>Compilerfehler C3366
'Variable': statische Datenmember von verwalteten oder WinRTtypes muss innerhalb der Klassendefinition definiert werden  
  
 Sie haben versucht, auf einen statischen Member einer WinRT- oder .NET-Klasse oder -Schnittstelle außerhalb der Definition der Klasse oder Schnittstelle zu verweisen.  
  
 Der Compiler muss die vollständige Definition der Klasse kennen (um Metadaten nach einer Übergabe auszugeben) und erfordert statische Datenmember für die Initialisierung innerhalb der Klasse.  
  
 Beispielsweise generiert das folgende Beispiel C3366 und zeigt, wie Sie den Fehler beheben:  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  
