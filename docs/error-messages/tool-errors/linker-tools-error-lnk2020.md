---
title: "Linkertoolfehler LNK2020"
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
  - "LNK2020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2020"
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht aufgelöstes Token 'Token'  
  
 Vergleichbar mit einem nicht definierten externen Fehler, mit dem Unterschied, dass der Verweis über Metadaten erfolgt.  In Metadaten müssen alle Funktionen und Daten definiert werden.  
  
 So beheben Sie diesen Fehler:  
  
-   Definieren Sie die fehlende Funktion bzw. die fehlenden Daten. \- oder \-  
  
-   Lesen Sie die Objektdatei oder die Bibliothek ein, in der die fehlende Funktion bzw. die Daten bereits definiert sind.  
  
## Beispiel  
 Im folgenden Beispiel wird LNK2020 generiert.  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## Beispiel  
 LNK2020 tritt auch dann auf, wenn Sie eine Variable eines verwalteten Vorlagentyps erstellen, jedoch diesen Typ nicht instaziieren.  
  
 Im folgenden Beispiel wird LNK2020 generiert.  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```