---
title: __svm_skinit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_skinit
dev_langs: C++
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e02bafc9319a6a3a4c5e07b46c9da6586f440d59
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="svmskinit"></a>__svm_skinit
**Microsoft-spezifisch**  
  
 Initiiert das Laden der überprüfbar sichere Software, z. B. einen Monitor für die virtuelle Maschine an.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`SLB`|Die 32-Bit-physische Adresse eines Bytes 64K Secure Ladeprogramm Block (SLB).|  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_skinit` -Funktion ist gleichbedeutend mit der `SKINIT` computeranweisung. Diese Funktion ist Teil einer Sicherheitssystem, die den Prozessor und eine vertrauenswürdige Platform Module (TPM) verwendet, stellen Sie sicher, und Laden vertrauenswürdige Software, die einen Kernel Sicherheit (SK) aufgerufen. Ein VM-Monitor ist ein Beispiel für einen Kernel Sicherheit. Das Sicherheitssystem überprüft Komponenten während der Initialisierung geladen und schützt Komponenten vor Manipulationen durch Interrupts, den Zugriff von Geräten oder ein anderes Programm, wenn der Computer über mehrere Prozessoren verfügt.  
  
 Die `SLB` Parameter gibt die physische Adresse eines Codeblocks 64 KB Arbeitsspeicher wird aufgerufen, die *Secure Ladeprogramm Block* (SLB). Der SLB enthält, ein Programm, das sichere Ladeprogramm, das die betriebsumgebung für den Computer her und lädt anschließend die Sicherheit Kernel aufgerufen wird.  
  
 Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593 Revision 3.11, an die [AMD Corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_skinit`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)