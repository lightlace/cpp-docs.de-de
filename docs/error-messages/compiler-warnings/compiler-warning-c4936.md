---
title: "Compilerwarnung C4936"
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
  - "C4936"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4936"
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4936
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec wird nur bei einer Kompilierung mit \/clr oder \/clr:pure unterstützt.  
  
 Ein `__declspec`\-Modifizierer wurde verwendet, der `__declspec`\-Modifizierer ist aber nur gültig, wenn er mit einer der [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)\-Optionen kompiliert wird.  
  
 Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).  
  
 C4936 wird immer als Fehler ausgegeben.  Sie können C4936 mit dem [warning](../../preprocessor/warning.md)\-Pragma deaktivieren.  
  
 Im folgenden Beispiel wird C4936 generiert:  
  
```  
// C4936.cpp // compile with: /c // #pragma warning (disable : 4936) __declspec(process) int i;   // C4936 __declspec(appdomain) int j;   // C4936  
```