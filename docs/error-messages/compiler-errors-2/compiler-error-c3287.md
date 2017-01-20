---
title: "Compilerfehler C3287"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3287"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3287"
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3287
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Typ 'Typ' \(Rückgabetyp von 'GetEnumerator'\) muss eine passende öffentliche MoveNext\-Memberfunktion und eine öffentliche Current\-Eigenschaft aufweisen.  
  
 Benutzerdefinierte Auflistungsklassen müssen Definitionen für `MoveNext` und `Current` enthalten.  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Durchlaufen einer benutzerdefinierten Auflistung mit der for\-each\-Klausel](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3287 generiert:  
  
```  
// C3287.cpp // compile with: /clr using namespace System; ref struct R { bool MoveNext() { return true; } property Object^ Current { Object^ get() { Object ^ o = gcnew Object; return o; } } }; ref struct R2 { R ^GetEnumerator() { R^ r = gcnew R; return r; } }; ref struct T {}; ref struct T2 { T ^GetEnumerator() { T^ t = gcnew T; return t; } }; int main() { for each (int i in gcnew T2) {}   // C3287 for each (int i in gcnew R2) {}   // OK }  
```