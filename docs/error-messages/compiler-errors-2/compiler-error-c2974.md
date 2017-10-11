---
title: Compilerfehler C2974 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2974
dev_langs:
- C++
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e24e25816ac646bcf26099abbfa8e681fdd72a6e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2974"></a>Compilerfehler C2974
Ungültiger Typ das Argument "Zahl", Typ erwartet  
  
 Die generische oder Vorlagenklasse Argument entspricht nicht der generische oder Vorlagendeklaration. Ein Typ die spitzen Klammern angezeigt. Überprüfen Sie die generische oder Vorlagenklasse Definition so, dass die richtigen Typen zu ermitteln.  
  
 Im folgenden Beispiel wird C2974 generiert:  
  
```  
// C2974.cpp  
// C2974 expected  
template <class T>  
struct TC {};  
  
template <typename T>  
void tf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   TC<1>* tc;  
   tf<"abc">("abc");  
  
   TC<int>* tc;  
   tf<const char *>("abc");  
}  
```  
  
 C2974 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2974b.cpp  
// compile with: /clr  
// C2974 expected  
using namespace System;  
generic <class T>  
ref struct GCtype {};  
  
generic <typename T>  
void gf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   GCtype<"a">^ gc;  
   gf<"a">("abc");  
  
   // OK  
   GCtype<int>^ gc;  
   gf<String ^>("abc");  
}  
```
