---
title: Compilerfehler C3382 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 782e5c4cc61294dbdaecbd63ff5c6031d387f843
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3382"></a>Compilerfehler C3382
"sizeof" wird von /clr:safe nicht unterstützt.  
  
 Die Ausgabedatei einer **/clr:safe** -Kompilierung ist eine überprüfbar typsichere Datei, und „sizeof“ wird nicht unterstützt, weil der Rückgabewert des sizeof-Operators „size_t“ lautet und seine Größe je nach Betriebssystem variiert.  
  
 Weitere Informationen finden Sie unter  
  
-   [sizeof-Operator](../../cpp/sizeof-operator.md)  
  
-   [/ CLR (common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3382 generiert:  
  
```  
// C3382.cpp  
// compile with: /clr:safe  
int main() {  
   sizeof( char );   // C3382  
}  
```
