---
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 24778b761ada56830b155a2fc65e90f54ba729ed
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217511"
---
# <a name="__lidt"></a>__lidt

**Microsoft-spezifisch**

Lädt das interruptdeskriptortabellenregister (IDTR) mit dem Wert an der angegebenen Speicheradresse.

## <a name="syntax"></a>Syntax

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Quelle*|in Zeiger auf den Wert, der in den IDTR kopiert werden soll.|

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__lidt`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die `__lidt` -Funktion entspricht der `LIDT` -Computer Anweisung und ist nur im Kernel Modus verfügbar. Weitere Informationen finden Sie im Dokument "Intel Architecture Software Developer es Manual, Volume 2: Anweisungs Satz Verweis "auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
