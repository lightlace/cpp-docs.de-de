---
title: _CIsqrt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _CIsqrt
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _CIsqrt
- CIsqrt
dev_langs:
- C++
helpviewer_keywords:
- CIsqrt intrinsic
- _CIsqrt intrinsic
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef9ebf20a365b48058bc7e5cf4dc0556d917ef44
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386201"
---
# <a name="cisqrt"></a>_CIsqrt
Berechnet die Quadratwurzel des obersten Werts im Stapel.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __cdecl _CIsqrt();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Version der `sqrt`-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Sie beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.  
  
 Der resultierende Wert wird oben auf dem Stapel abgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** x86  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)