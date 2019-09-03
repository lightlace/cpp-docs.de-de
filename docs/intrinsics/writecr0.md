---
title: __writecr0
ms.date: 09/02/2019
f1_keywords:
- _writecr0
helpviewer_keywords:
- _writecr0 intrinsic
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
ms.openlocfilehash: 1f00796242ae352d32935c2551d50f2d93d734ec
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219304"
---
# <a name="__writecr0"></a>__writecr0

**Microsoft-spezifisch**

Schreibt den Wert `Data` in das CR0-Register.

## <a name="syntax"></a>Syntax

```C
void writecr0(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Parameter

*Vorrats*\
in Der Wert, der in das CR0-Register geschrieben werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writecr0`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
