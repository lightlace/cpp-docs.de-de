---
title: Linkertoolfehler Lnk2020 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2020
dev_langs:
- C++
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33dd1b381d36a90f2e9b144e690e364ac512c081
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2020"></a>Linkertoolfehler LNK2020
nicht aufgelöstes Token 'Token'  
  
 Ähnlich wie ein nicht definierter externe Fehler mit dem Unterschied, dass der Verweis über Metadaten ist. In den Metadaten die alle Funktionen und Daten definiert werden.  
  
 So lösen Sie:  
  
-   Definieren Sie die fehlende Funktion oder Daten, oder  
  
-   Schließen Sie die Objektdatei oder die Bibliothek, die in dem die fehlende Funktion oder die Daten bereits definiert ist.  
  
## <a name="example"></a>Beispiel  
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
  
## <a name="example"></a>Beispiel  
 LNK2020 erfolgt auch, wenn Sie eine Variable eines verwalteten Vorlagentyps erstellen, aber auch nicht den Typ instanziiert wird.  
  
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