---
title: "Linkertoolfehler LNK1301 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1301"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1301"
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolfehler LNK1301
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es wurden clr\-Module für LTCG gefunden, die nicht kompatibel mit \/LTCG:parameter sind  
  
 Ein mit \/clr und \/GL kompiliertes Modul wurde zusammen mit einem der Parameter der profilgesteuerten Optimierungen \(PGO\) von \/LTCG an den Linker übergeben.  
  
 Profilgesteuerte Optimierungen werden für \/clr\-Module nicht unterstützt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [\/GL \(Optimierung des ganzen Programms\)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [\/LTCG \(Code zur Verknüpfungszeit generieren\)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Profilgesteuerte Optimierungen \(PGO\)](../../build/reference/profile-guided-optimizations.md)  
  
### So beheben Sie diesen Fehler  
  
1.  Kompilieren Sie nicht mit \/clr, oder erstellen Sie keine Verknüpfung mit einem der PGO\-Parameter zu \/LTCG.  
  
## Beispiel  
 Im folgenden Beispiel wird LNK1301 generiert:  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```