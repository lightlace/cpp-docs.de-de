---
title: __svm_skinit
ms.date: 11/04/2016
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: 199cba2623f9d8e47c08be642ec485599b87976e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026135"
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

Die `__svm_skinit` -Funktion entspricht der `SKINIT` -Computeranweisung. Diese Funktion ist Teil eines Security Systems, das der Prozessor und ein Trusted Platform Module (TPM) verwendet, um zu überprüfen, und Laden vertrauenswürdige Software, die einen Security-Kernel (SK) aufgerufen. Ein VM-Monitor ist ein Beispiel für einen Security-Kernel. Das Sicherheitssystem überprüft Programmkomponenten während der Initialisierung geladen, und schützt Komponenten vor Manipulationen durch Interrupts, den Zugriff von Geräten oder ein anderes Programm, wenn der Computer über mehrere Prozessoren verfügt.

Die `SLB` Parameter gibt an, die physische Adresse eines Blocks 64 KB Arbeitsspeicher wird aufgerufen, die *sichere Ladeprogramm Block* (SLB). Der SLB enthält, ein Programm, das sichere Ladeprogramm, das die betriebsumgebung für den Computer her und lädt anschließend den Security-Kernel aufgerufen wird.

Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: "System Programming," Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_skinit`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)