---
title: __inwordstring
ms.date: 09/02/2019
f1_keywords:
- __inwordstring
- __inwordstring_cpp
helpviewer_keywords:
- __inwordstring intrinsic
- rep insw instruction
ms.assetid: 6de37939-017a-4740-9e3d-7de78a30daba
ms.openlocfilehash: a6f67e15bc5eef9fbe9cc8d12e95afcdf869e3b1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221878"
---
# <a name="__inwordstring"></a>__inwordstring

**Microsoft-spezifisch**

Liest Daten mithilfe der `rep insw` -Anweisung aus dem angegebenen Port.

## <a name="syntax"></a>Syntax

```C
void __inwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parameter

*Port*\
in Der Port, von dem gelesen werden soll.

*Ert*\
vorgenommen Die vom Port gelesenen Daten werden hier geschrieben.

*Countdown*\
in Die Anzahl der Wörter der zu lesenden Daten.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__inwordstring`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
