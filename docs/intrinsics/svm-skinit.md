---
title: __svm_skinit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_skinit
dev_langs:
- C++
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8c59ad4af53a38ee28450e51adf9cdf81ec7bad
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687284"
---
# <a name="svmskinit"></a>__svm_skinit
**Microsoft-spezifisch**  
  
 Initiiert das Laden der überprüfbar sichere Software, z. B. einen Monitor für die virtuellen Computer an.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`SLB`|Die 32-Bit-physische Adresse eines 64K Bytes sichere Ladeprogramm Block (SLB).|  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_skinit` -Funktion ist gleichbedeutend mit der `SKINIT` computeranweisung. Diese Funktion ist Teil eines Security Systems, das der Prozessor und ein Trusted Platform Module (TPM) verwendet, um zu überprüfen, und Laden vertrauenswürdige Software, die einen Security-Kernel (SK) aufgerufen. Ein VM-Monitor ist ein Beispiel für einen Security-Kernel. Das Sicherheitssystem überprüft Programmkomponenten während der Initialisierung geladen, und schützt Komponenten vor Manipulationen durch Interrupts, den Zugriff von Geräten oder ein anderes Programm, wenn der Computer über mehrere Prozessoren verfügt.  
  
 Die `SLB` Parameter gibt an, die physische Adresse eines Blocks 64 KB Arbeitsspeicher wird aufgerufen, die *sichere Ladeprogramm Block* (SLB). Der SLB enthält, ein Programm, das sichere Ladeprogramm, das die betriebsumgebung für den Computer her und lädt anschließend den Security-Kernel aufgerufen wird.  
  
 Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_skinit`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)