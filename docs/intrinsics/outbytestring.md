---
title: __outbytestring
ms.date: 09/02/2019
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: 31caf17db5d56efccd6b30200994b1080356b4c1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217174"
---
# <a name="__outbytestring"></a>__outbytestring

**Microsoft-spezifisch**

Generiert die `rep outsb` -Anweisung, die die ersten `Count` Bytes von Daten, auf die `Buffer` von verwiesen wird, an `Port`den von angegebenen Port sendet.

## <a name="syntax"></a>Syntax

```C
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parameter

*Port*\
in Der Port, an den die Daten gesendet werden sollen.

*Ert*\
in Die Daten, die über den angegebenen Port gesendet werden sollen.

*Countdown*\
in Die Anzahl der Daten bytes, die gesendet werden sollen.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__outbytestring`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
