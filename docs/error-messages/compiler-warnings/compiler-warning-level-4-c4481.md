---
title: Compilerwarnung (Stufe 4) C4481 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4481
dev_langs: C++
helpviewer_keywords: C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52c296251e22adef2702aa9feba2b1fe2bc5122e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4481"></a>Compilerwarnung (Stufe 4) C4481
nicht dem Standard entsprechende Erweiterung: Überschreibungsspezifizierer 'Schlüsselwort'  
  
 Ein Schlüsselwort wurde verwendet, die nicht in der C++-standard, z. B. einen Überschreibungsspezifizierer, die funktioniert auch unter "/ CLR" ist.  Weitere Informationen finden Sie unter  
  
-   [/ CLR (common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
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