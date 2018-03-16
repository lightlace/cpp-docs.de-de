---
title: OPTION (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d8e8049ecea3775b9df85eb1d5c8ee5e94a9243
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="option-masm"></a>OPTION (MASM)
Aktiviert und deaktiviert die Funktionen des Assemblers.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Verfügbare Optionen:  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**EMULATOR**|  
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|  
|**LANGUAGE**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**PROLOG**|**READONLY**|**NOREADONLY**|  
|**IM BEREICH**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 Die Syntax für Sprache ist **OPTION LANGUAGE: *** X*, wobei *x* C, SYSCALL, "stdcall", wie in PASCAL, FORTRAN oder BASIC ist.  SYSCALL, PASCAL FORTRAN und BASIC können nicht mit der Verwendung [. Modell](../../assembler/masm/dot-model.md) Flatfile.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)