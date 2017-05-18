---
title: Compiler-Fehler C2743 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 7420231e64515b556cfe81fc695eda5f75231506
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2743"></a>Compiler-Fehler C2743 generiert
'Typ': catch von systemeigenem Typ mit __clrcall-Destruktor oder Kopierkonstruktor kann nicht  
  
 Ein Modul kompiliert mit **/CLR** hat versucht, eine Ausnahme systemeigenen Typs aufzufangen, wobei Destruktor des Typs oder der Kopierkonstruktor verwendet `__clrcall` Aufrufkonvention.  
  
 Bei der Kompilierung mit **/CLR**, Ausnahmebehandlung erwartet die Memberfunktionen in einem systemeigenen Typ zu [__cdecl](../../cpp/cdecl.md) und nicht [__clrcall](../../cpp/clrcall.md). Systemeigene Typen mit Memberfunktionen verwenden `__clrcall` Aufrufkonvention kann nicht aufgefangen werden, in einem Modul kompiliert mit **/CLR**.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2743 generiert.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```
