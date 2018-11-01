---
title: __sidt
ms.date: 11/04/2016
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 2188b2cdbf5c5f8836197f8cf2ee33928b7e9425
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624457"
---
# <a name="sidt"></a>__sidt

**Microsoft-spezifisch**

Speichert den Wert des Interrupt-Deskriptor Tabelle Registers (IDTR) in der angegebenen Speicheradresse.

## <a name="syntax"></a>Syntax

```
void __sidt(void * Destination);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Ziel*|[in] Ein Zeiger auf die Speicheradresse, wo die IDTR gespeichert werden.|

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__sidt`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die `__sidt` -Funktion entspricht der `SIDT` -Computeranweisung. Weitere Informationen zu suchen, nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference," auf die [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__lidt](../intrinsics/lidt.md)