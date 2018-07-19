---
title: Compilerwarnung (Stufe 4) C4481 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4481
dev_langs:
- C++
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeef5f2121808c5444af942fac0e3b72919f2354
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293117"
---
# <a name="compiler-warning-level-4-c4481"></a>Compilerwarnung (Stufe 4) C4481
nicht dem Standard entsprechende Erweiterung: Überschreibungsspezifizierer 'Schlüsselwort'  
  
 Ein Schlüsselwort wurde verwendet, die nicht in der C++-standard, z. B. einen Überschreibungsspezifizierer, die funktioniert auch unter "/ CLR" ist.  Weitere Informationen finden Sie unter  
  
-   [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4481 generiert.  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```