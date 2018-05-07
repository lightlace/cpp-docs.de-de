---
title: Compilerfehler C2912 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2912
dev_langs:
- C++
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b165e868f4a2055d692d768c7e5c0164dd34002
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2912"></a>Compilerfehler C2912
Explizite Spezialisierung 'declaration' ist keine Spezialisierung einer Funktionsvorlage  
  
 Nur Vorlagenfunktionen können spezialisiert werden.  
  
 Im folgenden Beispiel wird C2912 generiert:  
  
```  
// C2912.cpp  
// compile with: /c  
void f(char);  
template<> void f(char);   // C2912  
template<class T> void f(T);   // OK  
```  
  
 Dieser Fehler wird außerdem infolge einer Konformitätsverbesserung für Compiler generiert, die in Visual Studio .NET 2003 durchgeführt wurde: Für jede explizite Spezialisierung müssen Sie die Parameter der expliziten Spezialisierung so wählen, dass sie mit den Parametern der primären Vorlage übereinstimmen.  
  
```  
// C2912b.cpp  
class CF {  
public:  
   template <class A> CF(const A& a) {}   // primary template  
  
   // attempted explicit specialization  
   template <> CF(const char* p) {}   // C2912  
  
   // try the following line instead  
   // template <> CF(const char& p) {}  
};  
```