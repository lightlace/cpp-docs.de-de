---
title: __svm_stgi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_stgi
dev_langs: C++
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e76d0cda4dfe1644c590c555d9589c17b67686a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="svmstgi"></a>__svm_stgi
**Microsoft-spezifisch**  
  
 Legt die globalen Interrupt-Flag fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_stgi(void);  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_stgi` -Funktion ist gleichbedeutend mit der `STGI` computeranweisung. Das globale Interrupt-Flag bestimmt, ob Mikroprozessors ignoriert, verschiebt oder Interrupts aufgrund von Ereignissen, z. B. eine e/a-Abschluss, eine hardwarewarnung für die Temperatur oder eine Debug-Ausnahme behandelt.  
  
 Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593 Revision 3.11, an die [AMD Corporation](http://go.microsoft.com/fwlink/?LinkId=23746) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_stgi`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__svm_clgi](../intrinsics/svm-clgi.md)