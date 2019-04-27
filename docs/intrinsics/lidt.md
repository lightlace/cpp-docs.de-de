---
title: __lidt
ms.date: 11/04/2016
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 757309603af48820a17668cfe272bbeaad9239b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263684"
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
|*Quelle*|[in] Zeiger auf den Wert in der IDTR kopiert werden sollen.|

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__lidt`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die `__lidt` -Funktion ist gleichbedeutend mit der `LIDT` computeranweisung und steht nur im Kernelmodus ausgeführt. Weitere Informationen zu suchen, nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference,"auf die [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__sidt](../intrinsics/sidt.md)