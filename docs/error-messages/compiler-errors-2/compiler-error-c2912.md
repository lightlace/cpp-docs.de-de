---
title: "Compilerfehler C2912"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2912"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2912"
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2912
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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