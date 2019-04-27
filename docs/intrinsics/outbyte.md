---
title: __outbyte
ms.date: 11/04/2016
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: 234892369572a2ee315687f5d70533a0c8cf4b59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262969"
---
# <a name="outbyte"></a>__outbyte

**Microsoft-spezifisch**

Generiert die `out` -Anweisung, die mit 1 Byte gemäß sendet `Data` der e/a-Port anhand des `Port`.

## <a name="syntax"></a>Syntax

```
void __outbyte(
   unsigned short Port,
   unsigned char Data
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der die Daten zu senden.

*Data*<br/>
[in] Das Byte, die über den angegebenen Port gesendet werden.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__outbyte`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)