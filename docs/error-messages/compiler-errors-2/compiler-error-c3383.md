---
title: Compilerfehler C3383 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3383
dev_langs:
- C++
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2a97cd1348bc927b633e683bed80a6b907f88a58
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3383"></a>Compilerfehler C3383
"operator new" wird mit /clr:safe nicht unterstützt.  
  
 Die Ausgabedatei einer **/clr:safe** -Kompilierung ist Datei, die überprüfbar typsicher ist; Zeiger werden nicht unterstützt.  
  
 Weitere Informationen finden Sie unter  
  
-   [/ CLR (common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3383 generiert:  
  
```  
// C3383.cpp  
// compile with: /clr:safe  
int main() {  
   char* pCharArray = new char[256];  // C3383  
}  
```
