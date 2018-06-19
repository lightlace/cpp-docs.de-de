---
title: OPTION (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80291c805cad3ef041fffc58983ff399da07c9d9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057720"
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
  
 Die Syntax für Sprache ist **OPTION LANGUAGE: *** X*, wobei *x* C, SYSCALL, "stdcall", wie in PASCAL, FORTRAN oder BASIC ist.  SYSCALL, PASCAL FORTRAN und BASIC können nicht mit der Verwendung [. Modell](../../assembler/masm/dot-model.md) Flatfile.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)