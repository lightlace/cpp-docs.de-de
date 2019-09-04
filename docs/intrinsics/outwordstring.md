---
title: __outwordstring
ms.date: 09/02/2019
f1_keywords:
- __outwordstring
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
ms.openlocfilehash: 3cc5b0ae2101c86e3dc899b7924ec2524f0ea6e7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217118"
---
# <a name="__outwordstring"></a>__outwordstring

**Microsoft-spezifisch**

Generiert die `rep outsw` -Anweisung, die *Anzahl* Wörter startet, beginnend beim *Puffer* , den durch den *Port*angegebenen e/a-Port.

## <a name="syntax"></a>Syntax

```C
void __outwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parameter

*Port*\
in Der Port, an den die Daten gesendet werden sollen.

*Ert*\
in Ein Zeiger auf die Daten, die über den angegebenen Port gesendet werden sollen.

*Countdown*\
in Die Anzahl der zu sendenden Wörter.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__outwordstring`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
