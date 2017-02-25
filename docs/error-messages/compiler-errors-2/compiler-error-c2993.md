---
title: "Compilerfehler C2993 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2993"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2993"
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2993
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Ungültiger Typ für den Nichttyp\-Vorlagenparameter 'Parameter'  
  
 Eine Vorlage kann nicht mit einem Struktur\- oder Unionargument deklariert werden.  Verwenden Sie Zeiger, um Strukturen und Unions als Vorlagenparameter zu übergeben.  
  
 Im folgenden Beispiel wird C2993 generiert:  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 Dieser Fehler wird auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben: Nichttyp\-Vorlagenparameter in Form von Gleitkommaparametern sind nicht mehr zulässig.  Nichttyp\-Vorlagenparameter in Form von Gleitkommaparametern sind gemäß C\+\+\-Standard nicht zulässig.  
  
 Im Falle einer Funktionsvorlage verwenden Sie ein Funktionsargument, um den Gleitkomma\-Vorlagenparameter, der kein Typ ist, zu übergeben \(dieser Code ist sowohl in der Visual Studio .NET 2003\-Version als auch in der Visual Studio .NET\-Version von Visual C\+\+ zulässig\).  Im Falle von Klassenvorlagen gibt es keine einfache Problemumgehung.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```