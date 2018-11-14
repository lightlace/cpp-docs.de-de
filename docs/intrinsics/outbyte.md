---
title: __outbyte
ms.date: 11/04/2016
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: fa17e4859e861a9be46b4ad32b7ad090f6c3dbc6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326549"
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