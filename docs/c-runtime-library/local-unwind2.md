---
title: _local_unwind2
ms.date: 11/04/2016
api_name:
- _local_unwind2
api_location:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: 64ed92af32caaf579e7c6951250e3bf692d1cf43
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944207"
---
# <a name="_local_unwind2"></a>_local_unwind2

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

## <a name="remarks"></a>Anmerkungen

Diese Methode wird nur von der Laufzeitumgebung verwendet. Rufen Sie die Methode nicht in Ihrem Code auf.

Wenn diese Methode Beendigungshandler ausführt, beginnt sie an der aktuellen lexikalischen Ebene und arbeitet sich die lexikalischen Ebenen hoch, bis sie die Ebene erreicht, die von `stop` angegeben wird. Sie führt keine Beendigungshandler auf der Ebene aus, die von `stop` angegeben ist.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
