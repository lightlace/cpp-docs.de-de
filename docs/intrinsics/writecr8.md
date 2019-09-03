---
title: __writecr8
ms.date: 09/02/2019
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: c8df13c15b5cd8a51b77d65ad930a1852809ee30
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219237"
---
# <a name="__writecr8"></a>__writecr8

**Microsoft-spezifisch**

Schreibt den Wert `Data` in das CR8-Register.

## <a name="syntax"></a>Syntax

```C
void writecr8(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Parameter

*Vorrats*\
in Der Wert, der in das CR8-Register geschrieben werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writecr8`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die `__writecr8` systeminterne Funktion ist nur im Kernel Modus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
