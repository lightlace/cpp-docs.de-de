---
title: "Compilerfehler C3389 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3389"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3389"
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3389
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(Schlüsselwort\) kann bei \/clr:pure oder \/clr:safe nicht verwendet werden  
  
 Ein verwendeter [\_\_declspec](../../cpp/declspec.md)\-Modifizierer impliziert einen prozessspezifischen Zustand.  [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md) impliziert einen [anwendungsdomänenspezifischen](../../cpp/appdomain.md) Zustand.  Die Deklaration einer Variable mit dem `keyword` **\_\_declspec**\-Modifizierer und die Kompilierung mit **\/clr:pure** ist daher nicht zulässig.  
  
 Im folgenden Beispiel wird C3389 generiert:  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```