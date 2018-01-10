---
title: _CItan | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CItan
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _CItan
- CItan
dev_langs: C++
helpviewer_keywords:
- CItan intrinsic
- _CItan intrinsic
ms.assetid: d1ea3113-50a2-45a6-b6bc-680fcdcc0928
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42bf2d2f7d38779dbed78414fcd94dc33ab82480
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="citan"></a>_CItan
Berechnet den Tangens des obersten Werts im Stapel.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __cdecl _CItan();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Version der `tan`-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Die Funktion beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.  
  
 Der resultierende Wert wird oben auf dem Stapel abgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** x86  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)