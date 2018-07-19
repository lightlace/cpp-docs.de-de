---
title: Compilerfehler C3764 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3764
dev_langs:
- C++
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c214fcf40f442c35d754db64c8443c328d50ae10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273627"
---
# <a name="compiler-error-c3764"></a>Compilerfehler C3764
'Überschreibungsfunktion': kann nicht "Basisklassenfunktion" für die Methode der Basisklasse überschreiben  
  
 Der Compiler hat ein falsch formatiertes überschreiben. Beispielsweise wurde die Funktion der Basisklasse nicht `virtual`. Weitere Informationen finden Sie unter [überschreiben](../../windows/override-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3764 generiert.  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## <a name="example"></a>Beispiel  
 C3764 kann auch auftreten, wenn eine Basisklassenmethode sowohl explizit ist, und mit dem Namen überschreiben. Im folgenden Beispiel wird C3764 generiert.  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```