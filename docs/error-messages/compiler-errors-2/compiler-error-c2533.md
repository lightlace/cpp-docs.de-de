---
title: Compilerfehler C2533 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2533
dev_langs: C++
helpviewer_keywords: C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c21849c7318ac4f169bf7104a478fa57ba7dd040
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2533"></a>Compilerfehler C2533
„Bezeichner“: Rückgabetyp für Konstruktoren nicht zulässig  
  
 Ein Konstruktor kann keinen Rückgabetyp haben (auch keinen `void`-Rückgabetyp).  
  
 Eine häufige Ursache für diesen Fehler ist ein fehlendes Semikolon zwischen dem Ende einer Klassendefinition und der ersten Konstruktorimplementierung. Der Compiler erkennt die Klasse als Definition des Rückgabetyps für die Konstruktorfunktion und generiert C2533.  
  
 Im folgenden Beispiel wird C2533 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2533.cpp  
// compile with: /c  
class X {  
public:  
   X();     
};  
  
int X::X() {}   // C2533 - constructor return type not allowed  
X::X() {}   // OK - fix by using no return type  
```