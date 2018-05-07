---
title: Linkertoolfehler Lnk1301 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b4e298ad3815c741ff6c901ac39bf7838ed135d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1301"></a>Linkertoolfehler LNK1301
Clr-Module für LTCG gefunden, die nicht kompatibel mit /LTCG:parameter  
  
 Ein Modul mit "/ CLR" und/GL kompiliert wurde an den Linker zusammen mit der profilgesteuerten Optimierungen (PGO)-Parameter von/LTCG übergeben.  
  
 Profilgesteuerte Optimierungen sind bei/CLR-Modulen nicht unterstützt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG (Link-Zeitcodegenerierung)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
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