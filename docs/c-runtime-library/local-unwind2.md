---
title: _local_unwind2
ms.date: 11/04/2016
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: 8ae5c3937c9dedc54f0a936b91963419d59f79cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535407"
---
# <a name="localunwind2"></a>_local_unwind2

Interne CRT-Funktion. Führt alle Beendigungshandler aus, die in der angegebenen Bereichtabelle aufgelistet sind.

## <a name="syntax"></a>Syntax

```
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>Parameter

*xr*<br/>
[in]: Ein Registrierungseintrag, der mit einer Bereichtabelle verbunden ist.

*stop*<br/>
[in]: Die lexikalische Ebene, die darauf hinweist, wo `_local_unwind2` aufhören sollte.

## <a name="remarks"></a>Hinweise

Diese Methode wird nur von der Laufzeitumgebung verwendet. Rufen Sie die Methode nicht in Ihrem Code auf.

Wenn diese Methode Beendigungshandler ausführt, beginnt sie an der aktuellen lexikalischen Ebene und arbeitet sich die lexikalischen Ebenen hoch, bis sie die Ebene erreicht, die von `stop` angegeben wird. Sie führt keine Beendigungshandler auf der Ebene aus, die von `stop` angegeben ist.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)