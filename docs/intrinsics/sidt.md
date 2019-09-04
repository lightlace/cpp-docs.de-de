---
title: __sidt
ms.date: 09/02/2019
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: d6b685da0e02373307a3149c5b7b28213f37ad40
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222325"
---
# <a name="__sidt"></a>__sidt

**Microsoft-spezifisch**

Speichert den Wert des Interrupt Deskriptor Table Register (IDTR) an der angegebenen Speicheradresse.

## <a name="syntax"></a>Syntax

```C
void __sidt(void * Destination);
```

### <a name="parameters"></a>Parameter

*Entwickelt*\
in Ein Zeiger auf den Speicherort, an dem der IDTR gespeichert wird.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__sidt`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die `__sidt` -Funktion entspricht der `SIDT` -Computeranweisung. Weitere Informationen finden Sie im Dokument "Intel Architecture Software Developer es Manual, Volume 2: Anweisungs Satz Verweis "auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__lidt](../intrinsics/lidt.md)
