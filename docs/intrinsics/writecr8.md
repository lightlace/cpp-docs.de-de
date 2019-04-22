---
title: __writecr8
ms.date: 11/04/2016
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: 44b009e68f3dd7825bc064e5f9f4ee8d03d7fb4a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024763"
---
# <a name="writecr8"></a>__writecr8

**Microsoft-spezifisch**

Schreibt den Wert `Data` dem CR8-Register.

## <a name="syntax"></a>Syntax

```
void writecr8(
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Parameter

*Data*<br/>
[in] Der Wert, der registriert wird, CR8 geschrieben werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writecr8`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)