---
title: Compilerfehler C2942 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2942
dev_langs:
- C++
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55dc1fc5c2762751762b3798d28245224281ce67
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2942"></a>Compilerfehler C2942
"Klasse": "Typ-Klasse-ID" wird als formales Argument einer Funktion neu definiert.  
  
 Eine generische oder Vorlagenklasse kann nicht als formales Argument verwendet werden. Ein Argument kann nicht direkt an den Konstruktor einer generischen oder Vorlagenklasse übergeben werden.  
  
 Im folgenden Beispiel wird C2942 generiert.  
  
```  
  
// C2942.cpp  
// compile with: /c  
template<class T>  
struct TC {};   
void f(int TC<int>) {}   // C2942  
  
// OK  
struct TC2 {};  
void f(TC2 i) {}  
```  
  
 C2942 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2942b.cpp  
// compile with: /clr /c  
generic<class T>  
ref struct GC {};  
void f(int GC<int>) {}   // C2942  
ref struct GC2 { };  
void f(int GC2) {}  
```