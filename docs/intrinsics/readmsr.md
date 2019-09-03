---
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 4398b9d42369e3a914dbec1ed2d14cafecf58483
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222338"
---
# <a name="__readmsr"></a>__readmsr

**Microsoft-spezifisch**

Generiert die `rdmsr` -Anweisung, die das modellspezifische Register liest, das `register` von angegeben wird, und gibt den Wert zurück.

## <a name="syntax"></a>Syntax

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>Parameter

*sich*\
in Das modellspezifische Register, das gelesen werden soll.

## <a name="return-value"></a>Rückgabewert

Der Wert im angegebenen Register.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Funktion ist nur im Kernel Modus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

Weitere Informationen finden Sie in der AMD-Dokumentation.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
