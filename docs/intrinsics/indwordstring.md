---
title: __indwordstring
ms.date: 09/02/2019
f1_keywords:
- __indwordstring
- __indwordstring_cpp
helpviewer_keywords:
- __indwordstring intrinsic
- rep insd instruction
ms.assetid: 96a1cf33-f691-4916-99e4-fa849b61e3a9
ms.openlocfilehash: b0b160ba00b1c0b7aa6bffc913e4cb56d503c2ff
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217835"
---
# <a name="__indwordstring"></a>__indwordstring

**Microsoft-spezifisch**

Liest Daten mithilfe der `rep insd` -Anweisung aus dem angegebenen Port.

## <a name="syntax"></a>Syntax

```C
void __indwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parameter

*Port*\
in Der Port, von dem gelesen werden soll.

*Ert*\
vorgenommen Die vom Port gelesenen Daten werden hier geschrieben.

*Countdown*\
in Die Anzahl der Daten bytes, die gelesen werden sollen.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__indwordstring`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
