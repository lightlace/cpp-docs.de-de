---
title: "Compilerfehler C2146 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2146"
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Compilerfehler C2146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: Fehlendes 'Token' vor Bezeichner 'Bezeichner'  
  
 Der Compiler hat ein `token` erwartet, jedoch einen `identifier` gefunden.  Mögliche Ursachen:  
  
1.  Schreibfehler oder falsche Groß\-\/Kleinschreibung.  
  
2.  Fehlender Typspezifizierer in der Deklaration des Bezeichners.  
  
 Dieser Fehler wird möglicherweise durch einen typografischen Fehler verursacht.  Der Fehler [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) geht diesem Fehler normalerweise voraus.  
  
## Beispiel  
 Im folgenden Beispiel wird C2146 generiert.  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## Beispiel  
 Dieser Fehler kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden: fehlendes `typename`\-Schlüsselwort.  
  
 Der folgende Beispielcode wird in Visual Studio .NET 2002 kompiliert, verursacht in Visual Studio .NET 2003 jedoch einen Fehler:  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## Beispiel  
 Dieser Fehler kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden: explizite Spezialisierungen finden nicht länger Vorlagenparameter aus der primären Vorlage.  
  
 Die Verwendung von `T` aus der primären Vorlage ist in der expliziten Spezialisierung nicht zulässig.  In Code, der in der Visual Studio .NET 2003\-Version und der Visual Studio .NET\-Version von Visual C\+\+ gültig sein soll, ersetzen Sie alle Instanzen des Vorlagenparameters in der Spezialisierung durch den explizit spezialisierten Typ.  
  
 Der folgende Beispielcode wird in Visual Studio .NET kompiliert, verursacht in Visual Studio .NET 2003 jedoch einen Fehler:  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```