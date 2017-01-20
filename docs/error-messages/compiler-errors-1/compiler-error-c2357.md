---
title: "Compilerfehler C2357"
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
  - "C2357"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2357"
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2357
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Muss eine Funktion vom Typ 'Typ' sein  
  
 Durch den Code wird eine Version der `atexit`\-Funktion deklariert, die nicht mit der Version übereinstimmt, die intern vom Compiler deklariert wurde.  Deklarieren Sie `atexit` wie folgt:  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 Weitere Informationen finden Sie unter [init\_seg](../../preprocessor/init-seg.md).  
  
 Im folgenden Beispiel wird C2357 generiert:  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```