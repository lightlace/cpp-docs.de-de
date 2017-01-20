---
title: "Compilerfehler C3383"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3383"
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operator new" wird mit \/clr:safe nicht unterstützt.  
  
 Die Ausgabedatei einer **\/clr:safe**\-Kompilierung ist Datei, die überprüfbar typsicher ist; Zeiger werden nicht unterstützt.  
  
 Weitere Informationen finden Sie unter  
  
-   [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Häufig auftretende 64\-Bit\-Migrationsprobleme bei Visual C\+\+](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Beispiel  
 Im folgenden Beispiel wird C3383 generiert:  
  
```  
// C3383.cpp // compile with: /clr:safe int main() { char* pCharArray = new char[256];  // C3383 }  
```