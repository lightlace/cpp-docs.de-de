---
title: __outbyte
ms.date: 09/02/2019
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: 18792010c45ffb648e9555ccb73f8614c3e3e6ea
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217192"
---
# <a name="__outbyte"></a>__outbyte

**Microsoft-spezifisch**

Generiert die `out` -Anweisung, die ein Byte sendet, `Data` das durch den durch angegebenen e `Port`/a-Port angegeben wird.

## <a name="syntax"></a>Syntax

```C
void __outbyte(
   unsigned short Port,
   unsigned char Data
);
```

### <a name="parameters"></a>Parameter

*Port*\
in Der Port, an den die Daten gesendet werden sollen.

*Vorrats*\
in Das Byte, das an den angegebenen Port gesendet werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__outbyte`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
