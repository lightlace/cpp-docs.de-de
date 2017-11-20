---
title: _CIsin | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CIsin
apilocation:
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- CIsin
- _CIsin
dev_langs: C++
helpviewer_keywords:
- _CIsin intrinsic
- CIsin intrinsic
ms.assetid: f215f39a-2341-4f1c-ba8e-cb522451ceb2
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 83771532c05d00ebd52c62646b04c3de14dbbe3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cisin"></a>_CIsin
Berechnet den Sinus des obersten Werts im Stapel.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __cdecl _CIsin();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Version der `sin`-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Sie beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.  
  
 Der resultierende Wert wird oben auf dem Stapel abgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** x86  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Funktionsreferenz (alphabetisch)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)