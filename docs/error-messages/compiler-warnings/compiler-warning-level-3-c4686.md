---
title: "Compilerwarnung (Stufe 3) C4686"
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
  - "C4686"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4686"
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4686
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**"**   
 ***benutzerdefinierter Typ* ": Mögliche Verhaltensänderung, Änderung in der UDT gibt Aufrufkonvention zurück**  
  
 Die Spezialisierung einer Klassenvorlage wurde vor der Verwendung in einem Rückgabetyp nicht definiert.  Alles, das die Klasse instanziiert, löst C4686 auf; eine Instanz deklarieren oder den Zugriff auf einen Member \(\<\>Cint::anything\) sind auch Optionen.  
  
 Diese Warnung resultiert aus einer Verbesserung bezüglich des Visual C\+\+ .NET 2003\-Compilers, die Konformität mit dem ISO C\+\+\-Standard gewährleisten soll.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Gehen Sie stattdessen wie folgt vor:  
  
```  
// C4686.cpp  
// compile with: /W3  
#pragma warning (default : 4686)  
template <class T>  
class C;  
  
template <class T>  
C<T> f(T);  
  
template <class T>  
class C {};  
  
int main() {  
   f(1);   // C4686  
}  
  
template <class T>  
C<T> f(T) {  
   return C<int>();  
}  
```