---
title: OPTION (MASM) | Microsoft-Dokumentation
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
ms.openlocfilehash: 4a2dcbc55d6a2d033cde3b6189618afd67bdc3fb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221508"
---
# <a name="option-masm"></a>OPTION (MASM)
Aktiviert und deaktiviert die Funktionen des Assemblers.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Verfügbare Optionen sind:  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**EMULATOR**|  
|**NOEMULATOR**|**EPILOG**|**EXPR16**|**EXPR32**|  
|**SPRACHE**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**PROLOG**|**READONLY**|**NOREADONLY**|  
|**IM BEREICH EINER**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 Die Syntax für die Sprache ist **OPTION Sprache:**<em>x</em>, wobei *x* ist einer der C, SYSCALL, STDCALL, PASCAL, FORTRAN oder BASIC.  SYSCALL, PASCAL, FORTRAN und BASIC werden nicht unterstützt mit der Verwendung [. Modell](../../assembler/masm/dot-model.md) Flatfile.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)