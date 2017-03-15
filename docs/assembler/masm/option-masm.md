---
title: "OPTION (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "option"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OPTION directive"
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# OPTION (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert und deaktiviert die Funktionen des Assemblers.  
  
## Syntax  
  
```  
  
OPTION   
optionlist  
  
```  
  
## Hinweise  
 Verfügbares folgende Optionen:  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**EMULATOR**|  
|**NOEMULATOR**|**EPILOG**|**EXPR16**|**EXPR32**|  
|**LANGUAGE**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**EINLEITUNG**|**READONLY**|**NOREADONLY**|  
|**BEWERTET**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 Die Syntax für LANGUAGE ist **OPTION LANGUAGE:***x*, wobei *x* eine von C, SYSCALL PASCAL, STDCALL aus, aus, BASIC oder Fortran ist.  SYSCALL, BASIC, PASCAL Fortran und werden nicht mit EBENE verwendetem mit [.MODEL](../../assembler/masm/dot-model.md) unterstützt.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)