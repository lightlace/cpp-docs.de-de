---
title: "Explizite Spezialisierung von Funktionsvorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deklarieren von Funktionen, Spezialisierung der Funktionsvorlage"
  - "Explizite Spezialisierung von Funktionsvorlagen"
  - "Funktionsvorlagen, Spezialisierung"
  - "Überschreiben, Funktionen"
  - "Spezialisierung von Funktionsvorlagen"
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Explizite Spezialisierung von Funktionsvorlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei einer Funktionsvorlage können Sie ein spezielles Verhalten für einen bestimmten Typ definieren, indem Sie eine explizite Spezialisierung \(Überschreibung\) der Funktionsvorlage für diesen Typ angeben.  Beispiel:  
  
```  
template<> void MySwap(double a, double b);  
```  
  
 Durch diese Deklaration können Sie eine andere Funktion für **double**\-Variablen definieren.  Wie Nichtvorlagenfunktionen werden standardmäßige Typkonvertierungen \(z. B. Höherstufen einer Variable des Typs **float** auf **double**\) angewendet.  
  
## Beispiel  
  
```  
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)