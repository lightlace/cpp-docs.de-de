---
title: _CItan | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CItan
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _CItan
- CItan
dev_langs:
- C++
helpviewer_keywords:
- CItan intrinsic
- _CItan intrinsic
ms.assetid: d1ea3113-50a2-45a6-b6bc-680fcdcc0928
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcbd7f4258447df6f60f464b4c0a24080155fa9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387976"
---
# <a name="citan"></a>_CItan

Berechnet den Tangens des obersten Werts im Gleitkommastapel.

## <a name="syntax"></a>Syntax

```C
void __cdecl _CItan();
```

## <a name="remarks"></a>Hinweise

Diese Version der [tan](../c-runtime-library/reference/tan-tanf-tanl.md)-Funktion verfügt über eine spezielle Aufrufkonvention, die der Compiler versteht. Die Funktion beschleunigt die Ausführung, da sie das Generieren von Kopien verhindert und bei der Registerzuweisung hilft.

Der resultierende Wert wird oben auf dem Gleitkommastapel abgelegt.

## <a name="requirements"></a>Anforderungen

**Plattform:** x86

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)<br/>
