---
title: "Explizite Spezialisierung von Funktionsvorlagen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
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