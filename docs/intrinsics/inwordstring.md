---
title: __inwordstring | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __inwordstring
- __inwordstring_cpp
dev_langs:
- C++
helpviewer_keywords:
- __inwordstring intrinsic
- rep insw instruction
ms.assetid: 6de37939-017a-4740-9e3d-7de78a30daba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 969d57d01915ecfcf20c29b08d71c438206c45b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440525"
---
# <a name="inwordstring"></a>__inwordstring

**Microsoft-spezifisch**

Liest Daten aus den angegebenen Port mit der `rep insw` Anweisung.

## <a name="syntax"></a>Syntax

```
void __inwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der gelesen werden.

*Buffer*<br/>
[out] Die vom Port gelesenen Daten werden hier geschrieben.

*Anzahl*<br/>
[in] Die Anzahl von Wörtern, der zu lesenden Daten.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__inwordstring`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)