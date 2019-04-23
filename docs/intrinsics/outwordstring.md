---
title: __outwordstring
ms.date: 11/04/2016
f1_keywords:
- __outwordstring
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
ms.openlocfilehash: d7141dd7f9f1f81e905952959e392a23d141f4e4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030367"
---
# <a name="outwordstring"></a>__outwordstring

**Microsoft-spezifisch**

Generiert die `rep outsw` -Anweisung, die sendet `Count` Wörter, die beginnend bei `Buffer` der e/a-Port anhand des `Port`.

## <a name="syntax"></a>Syntax

```
void __outwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der die Daten zu senden.

*Buffer*<br/>
[in] Ein Zeiger auf Daten, die über den angegebenen Port gesendet werden.

*Anzahl*<br/>
[in] Die Anzahl von Wörtern zu senden.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__outwordstring`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)