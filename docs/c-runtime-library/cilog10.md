---
title: _CIlog10 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _CIlog10
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- CIlog10
- _CIlog10
dev_langs:
- C++
helpviewer_keywords:
- _CIlog10 intrinsic
- CIlog10 intrinsic
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d78967c8cff8933ac16af9333bb4e000f686f6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078594"
---
# <a name="cilog10"></a>_CIlog10

Führt eine `log10`-Operation mit dem obersten Wert im Stapel durch.

## <a name="syntax"></a>Syntax

```
void __cdecl _CIlog10();
```

## <a name="remarks"></a>Hinweise

Diese Version der `log10`-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Die Funktion beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.

Der resultierende Wert wird oben auf dem Stapel abgelegt.

## <a name="requirements"></a>Anforderungen
 **Plattform:** x86

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)