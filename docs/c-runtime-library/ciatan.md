---
title: _CIatan
ms.date: 11/04/2016
apiname:
- _CIatan
apilocation:
- msvcr120.dll
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- _CIatan
- CIatan
helpviewer_keywords:
- CIatan intrinsic
- _CIatan intrinsic
ms.assetid: 3baa0429-fe46-4bab-8b00-868e2186dc8c
ms.openlocfilehash: 8633ad1bda149e6e03f88b6fd646648f055c81c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471161"
---
# <a name="ciatan"></a>_CIatan

Berechnet den Arkustangens des obersten Werts im Stapel.

## <a name="syntax"></a>Syntax

```
void __cdecl _CIatan();
```

## <a name="remarks"></a>Hinweise

Diese Version der `atan`-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Sie beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.

Der resultierende Wert wird oben auf dem Stapel abgelegt.

## <a name="requirements"></a>Anforderungen

**Plattform:** x86

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)