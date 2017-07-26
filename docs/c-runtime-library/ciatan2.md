---
title: _CIatan2 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CIatan2
apilocation:
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- CIatan2
- _CIatan2
dev_langs:
- C++
helpviewer_keywords:
- _CIatan2 intrinsic
- CIatan2 intrinsic
ms.assetid: 31f8cc78-b79f-4576-b73b-8add18e08680
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8c2794d75d04fc7c5333cb1779fd6b90b57e9df5
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="ciatan2"></a>_CIatan2
Berechnet den Arkustangens von *x* / *y*, wobei *x* und *y* die obersten Werte des Stapels sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __cdecl _CIatan2();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Version der `atan2`-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Sie beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.  
  
 Der resultierende Wert wird oben auf dem Stapel abgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** x86  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Funktionsreferenz (alphabetisch)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)
