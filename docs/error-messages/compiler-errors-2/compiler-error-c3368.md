---
title: "Compilerfehler C3368"
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
  - "C3368"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3368"
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3368
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'funktionsdeklaration': Ungültige Aufrufkonvention für IDL  
  
 In einer IDL\-Datei können nur die [\_\_stdcall](../../cpp/stdcall.md)\- oder [\_\_cdecl](../../cpp/cdecl.md)\-Aufrufkonventionen verwendet werden.  
  
 Im folgenden Beispiel wird C3368 generiert:  
  
```  
// C3368.cpp // processor: x86 [idl_module(name="Name", dllname="Some.dll")]; [idl_module(name="Name")] int __fastcall f1();   // C3368  
```