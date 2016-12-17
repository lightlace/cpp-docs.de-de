---
title: "Compilerfehler C3862"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3862"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3862"
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3862
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Eine nicht verwaltete Funktion kann nicht mit \/clr:pure oder \/clr:safe kompiliert werden  
  
 Eine Kompilierung mit **\/clr:pure** oder **\/clr:safe** generiert ausschließlich ein MSIL\-Abbild, d. h. ein Abbild ohne systemeigenen \(nicht verwalteten\) Code.  Daher können Sie das `unmanaged`\-Pragma nicht in einer **\/clr:pure**\- oder **\/clr:safe** \-Kompilierung verwenden.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) und [managed, unmanaged](../../preprocessor/managed-unmanaged.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3862 generiert:  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```