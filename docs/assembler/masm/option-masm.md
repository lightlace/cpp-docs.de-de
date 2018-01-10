---
title: OPTION (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: option
dev_langs: C++
helpviewer_keywords: OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f449606b143bfbf188e878b261f3d35017846862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|**NOEMULATOR**|**EPILOG**|**EXPR16**|**EXPR32**|  
|**SPRACHE**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**PROLOG**|**READONLY**|**NOREADONLY**|  
|**IM BEREICH**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 Die Syntax für Sprache ist **OPTION LANGUAGE:***x*, wobei *x* C, SYSCALL, "stdcall", wie in PASCAL, FORTRAN oder BASIC ist.  SYSCALL, PASCAL FORTRAN und BASIC können nicht mit der Verwendung [. Modell](../../assembler/masm/dot-model.md) Flatfile.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)