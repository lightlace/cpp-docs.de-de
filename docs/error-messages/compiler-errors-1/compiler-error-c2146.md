---
title: Compilerfehler C2146 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2146
dev_langs:
- C++
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73367284a8c13316d344a4cff87ccae4ee7c832d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170618"
---
# <a name="compiler-error-c2146"></a>Compilerfehler C2146
Syntaxfehler: Fehlendes "token" vor Bezeichner "Bezeichner"  
  
 Der Compiler erwartet `token` und `identifier` stattdessen.  Mögliche Ursachen:  
  
1.  Fehler bei Schreibweise oder Groß-/Kleinschreibung.  
  
2.  Fehlender Typspezifizierer in der Deklaration des Bezeichners.  
  
 Dieser Fehler kann durch einen Tippfehler verursacht werden. Fehler beim [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) in der Regel vor dem dieser Fehler.  
  
## <a name="example"></a>Beispiel  
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
  
## <a name="example"></a>Beispiel  
 Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Visual Studio .NET 2003 durchgeführt wurde, die generiert werden: fehlende `typename` Schlüsselwort.  
  
 Im folgende Beispiel in Visual Studio .NET 2003 treten jedoch in Visual Studio .NET 2002 kompiliert wird:  
  
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
  
## <a name="example"></a>Beispiel  
 Sehen Sie auch diesen Fehler infolge einer konformitätsverbesserung, die für Visual Studio .NET 2003 durchgeführt wurde: explizite spezialisierungen werden nicht mehr aus der primären Vorlage Vorlagenparameter finden.  
  
 Die Verwendung von `T` aus der primären Vorlage ist in der expliziten Spezialisierung nicht zulässig. Ersetzen Sie alle Instanzen des Vorlagenparameters in der Spezialisierung für Code in der Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig ist mit dem explizit spezialisierte Typ.  
  
 Im folgende Beispiel in Visual Studio .NET 2003 treten jedoch in Visual Studio .NET kompiliert wird:  
  
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