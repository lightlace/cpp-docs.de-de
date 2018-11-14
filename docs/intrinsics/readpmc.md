---
title: __readpmc
ms.date: 11/04/2016
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: 059d9344fa329e69666abaca4d73122ab29f8d2a
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326432"
---
# <a name="readpmc"></a>__readpmc

**Microsoft-spezifisch**

Generiert die `rdpmc` -Anweisung, die mit der Leistungsüberwachung anhand des Leistungsindikators liest `counter`.

## <a name="syntax"></a>Syntax

```
unsigned __int64 __readpmc(
   unsigned long counter
);
```

#### <a name="parameters"></a>Parameter

*Leistungsindikator*<br/>
[in] Der Leistungsindikator zu lesen.

## <a name="return-value"></a>Rückgabewert

Der Wert des angegebenen Leistungsindikators.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readpmc`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminterne Funktion ist im Kernel-Modus ist nur verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)