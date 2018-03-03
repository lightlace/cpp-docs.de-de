---
title: Linkertoolfehler Lnk1301 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfcdb90b967ce5f0e9eda8dded9b93db5bdcc268
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1301"></a>Linkertoolfehler LNK1301
Clr-Module für LTCG gefunden, die nicht kompatibel mit /LTCG:parameter  
  
 Ein Modul mit "/ CLR" und/GL kompiliert wurde an den Linker zusammen mit der profilgesteuerten Optimierungen (PGO)-Parameter von/LTCG übergeben.  
  
 Profilgesteuerte Optimierungen sind bei/CLR-Modulen nicht unterstützt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [/ GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/ LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/ CLR (common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Nicht mit/CLR kompiliert oder nicht mit einer der Parameter für die profilgesteuerte Optimierung an/LTCG verknüpfen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird LNK1301 generiert:  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```