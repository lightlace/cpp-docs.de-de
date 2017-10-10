---
title: Compilerfehler C2217 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2217
dev_langs:
- C++
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f1795534af1332859fd1a33a137573df82643b4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2217"></a>Compilerfehler C2217
'Attribut1' erfordert 'Attribut2'  
  
 Die erste Funktionsattribut ist das zweite Attribut erforderlich.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Unterbrechen (`__interrupt`) als Funktion deklariert `near`. Unterbrechen Funktionen muss `far`.  
  
2.  Unterbrechen Sie die Funktion deklariert mit `__stdcall`, oder `__fastcall`. Diese Funktionen müssen verwenden C Aufrufkonventionen.  
  
## <a name="example"></a>Beispiel  
 C2217 kann auch auftreten, wenn Sie versuchen, einen Delegaten an eine CLR-Funktion zu binden, die eine Variable Anzahl von Argumenten akzeptiert. Wenn die Funktion auch Parameterarrayüberladung aufweist, verwenden Sie stattdessen. Im folgenden Beispiel wird C2217 generiert.  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```
