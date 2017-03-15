---
title: "Compilerfehler C3883 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3883"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3883"
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3883
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Ein statischer initonly\-Datenmember muss initialisiert werden  
  
 Eine mit [initonly](../../dotnet/initonly-cpp-cli.md) markierte Variable wurde nicht ordnungsgemäß initialisiert.  
  
 Im folgenden Beispiel wird C3883 generiert:  
  
```  
// C3883.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   static int staticConst1;   // C3883  
};  
```  
  
 Das folgende Beispiel veranschaulicht eine mögliche Auflösung:  
  
```  
// C3883b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst2 = 0;  
};  
```  
  
 Anhand des folgenden Beispiels wird gezeigt, wie die Initialisierung in einem statischen Konstruktor erfolgt:  
  
```  
// C3883c.cpp  
// compile with: /clr /LD  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```