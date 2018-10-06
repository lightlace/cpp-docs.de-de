---
title: __lidt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lidt
- __lidt_cpp
dev_langs:
- C++
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f07f4aee87df98b93c5aca54d1435339bf546539
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820658"
---
# <a name="lidt"></a>__lidt

**Microsoft-spezifisch**

Lädt das Interrupt-Deskriptor Tabelle Register (IDTR) mit dem Wert in der angegebenen Speicheradresse.

## <a name="syntax"></a>Syntax

```
void __lidt(void * Source);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Source*|[in] Zeiger auf den Wert in der IDTR kopiert werden sollen.|

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__lidt`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die `__lidt` -Funktion ist gleichbedeutend mit der `LIDT` computeranweisung und steht nur im Kernelmodus ausgeführt. Weitere Informationen zu suchen, nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference," auf die [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__sidt](../intrinsics/sidt.md)