---
title: __svm_stgi | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_stgi
dev_langs:
- C++
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4717fdc2018788d1fe56c26ae913a71e4f83475f
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540015"
---
# <a name="svmstgi"></a>__svm_stgi
**Microsoft-spezifisch**  
  
 Legt das globale Interrupt-Flag fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_stgi(void);  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_stgi` -Funktion ist gleichbedeutend mit der `STGI` computeranweisung. Das globale Interrupt-Flag bestimmt, ob der Mikroprozessor ignoriert, verschiebt oder Unterbrechungen, z. B. durch einen e/a-Abschluss, eine temperaturwarnung Hardware oder eine debugausnahme behandelt.  
  
 Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_stgi`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__svm_clgi](../intrinsics/svm-clgi.md)