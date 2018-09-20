---
title: __svm_vmload | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmload
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 837889478a4a646f8fb3829b3a05d0842edc1090
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399859"
---
# <a name="svmvmload"></a>__svm_vmload

**Microsoft-spezifisch**

Lädt eine Teilmenge der Prozessorzustand aus der angegebenen virtuellen Computer-Kontrollblock (VMCB).

## <a name="syntax"></a>Syntax

```
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] Die physische Adresse der VMCB.|

## <a name="remarks"></a>Hinweise

Die `__svm_vmload` -Funktion ist gleichbedeutend mit der `VMLOAD` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_vmload`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmrun](../intrinsics/svm-vmrun.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)