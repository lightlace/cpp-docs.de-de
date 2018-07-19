---
title: __svm_clgi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_clgi
dev_langs:
- C++
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 679c2b4d7abb792dfe6baa5ad5e18752fb7ca8bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332545"
---
# <a name="svmclgi"></a>__svm_clgi
**Microsoft-spezifisch**  
  
 Löscht das globale Interrupt-Flag.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_clgi( void );  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_clgi` -Funktion ist gleichbedeutend mit der `CLGI` computeranweisung. Das globale Interrupt-Flag bestimmt, ob Mikroprozessors ignoriert, verschiebt oder Interrupts aufgrund von Ereignissen, z. B. eine e/a-Abschluss, eine hardwarewarnung für die Temperatur oder eine Debug-Ausnahme behandelt.  
  
 Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593 Revision 3.11, an die [AMD Corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_clgi`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__svm_stgi](../intrinsics/svm-stgi.md)