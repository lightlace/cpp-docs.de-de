---
title: __inbytestring
ms.date: 09/02/2019
f1_keywords:
- __inbytestring
- __inbytestring_cpp
helpviewer_keywords:
- rep insb instruction
- __inbytestring intrinsic
ms.assetid: fe549556-e7a3-4af3-8ebf-8a7dc3cb233b
ms.openlocfilehash: cb6e811c809c6069c47415e87804641f30a3897b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217809"
---
# <a name="__inbytestring"></a>__inbytestring

**Microsoft-spezifisch**

Liest Daten mithilfe der `rep insb` -Anweisung aus dem angegebenen Port.

## <a name="syntax"></a>Syntax

```C
void __inbytestring(
   unsigned short Port,
   unsigned char* Buffer,
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
|`__inbytestring`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
