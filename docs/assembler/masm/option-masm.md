---
title: "OPTION (MASM)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "option"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OPTION directive"
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
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