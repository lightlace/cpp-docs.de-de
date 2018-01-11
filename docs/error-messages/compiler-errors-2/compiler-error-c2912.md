---
title: Compilerfehler C2912 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2912
dev_langs: C++
helpviewer_keywords: C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 88533f00ebf926823d6493aa1027013638694a43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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