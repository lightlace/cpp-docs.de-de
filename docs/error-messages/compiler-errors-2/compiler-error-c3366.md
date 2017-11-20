---
title: Compilerfehler C3366 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3366
dev_langs: C++
helpviewer_keywords: C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b862e606b86eca0a7eb7f2ad1e91f2776c8c0b23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
