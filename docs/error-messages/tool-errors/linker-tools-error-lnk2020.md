---
title: Linkertoolfehler Lnk2020 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2020
dev_langs:
- C++
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 394cafe23851df5320a78a4e165a90422fc305de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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