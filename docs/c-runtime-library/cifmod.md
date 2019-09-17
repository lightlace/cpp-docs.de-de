---
title: _CIfmod
ms.date: 11/04/2016
api_name:
- _CIfmod
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CIfmod
- CIfmod
helpviewer_keywords:
- CIfmod intrinsic
- _CIfmod intrinsic
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
ms.openlocfilehash: ca869a3033e4186ff6029a832c22bc4149ea1010
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944644"
---
# <a name="_cifmod"></a>_CIfmod

Berechnet den Gleitkommarest für die beiden obersten Werte im Stapel.

## <a name="syntax"></a>Syntax

```
void __cdecl _CIfmod();
```

## <a name="remarks"></a>Anmerkungen

Diese Version der `fmod`-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Sie beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.

Der resultierende Wert wird oben auf dem Stapel abgelegt.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattform:** x86

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)
