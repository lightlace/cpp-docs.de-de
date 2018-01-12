---
title: Compilerfehler C3225 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3225
dev_langs: C++
helpviewer_keywords: C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c189e2f4a0af7363f5bb988c9911bd90eb72809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3225"></a>Compilerfehler C3225
generisches Typargument für 'Arg' kann nicht 'Typ', es muss ein Werttyp oder ein Handletyp  
  
 Das generische Typargument war nicht den richtigen Typ.  
  
 Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Einen generischen Typ mit einem systemeigenen Typ kann nicht instanziiert werden. Im folgende Beispiel wird C3225 generiert.  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Komponente, die mithilfe von c# erstellt. Beachten Sie, dass die Einschränkung gibt an, dass der generische Typ nur mit einem Werttyp instanziiert werden kann.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet der c#-erstellte Komponente und die Einschränkung, die MyList nur kann gegen instanziiert mit einem Werttyp außer <xref:System.Nullable>. Im folgende Beispiel wird C3225 generiert.  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```