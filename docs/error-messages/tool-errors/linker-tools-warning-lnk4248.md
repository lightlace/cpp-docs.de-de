---
title: Linkertoolwarnung Lnk4248 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01053ddbbb0c7d234f6b465392f5bbe991ea329c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4248"></a>Linkertoolwarnung LNK4248
nicht aufgelöste Typeref-Token (Token) für 'Typ'; Abbild kann möglicherweise nicht ausgeführt.  
  
 Ein Typ aufweisen keine Definition in MSIL-Metadaten.  
  
 LNK4248 kann auftreten, wenn es nur eine Vorwärtsdeklaration für einen Typ in einem MSIL-Modul ist (kompiliert mit **"/ CLR"**), auf den Typ im MSIL-Modul verwiesen wird, und die MSIL-Modul mit einem systemeigenen Modul verknüpft ist, die eine Definition für verfügt Der Typ.  
  
 In diesem Fall kann der Linker wird die Definition der systemeigene Typ in den MSIL-Metadaten bereitstellen, und dies kann eine für das richtige Verhalten.  
  
 Jedoch, wenn eine Vorwärts-Typdeklaration ein CLR-Typ ist, systemeigene Typdefinition für den Linker nicht richtig möglicherweise  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie die Typdefinition in der MSIL-Modul.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK4248 generiert. Definieren Sie die Struktur ein aufgelöst.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wurde eine Rollforward Definition eines Typs.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK4248 generiert.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```