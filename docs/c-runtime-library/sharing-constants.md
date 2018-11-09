---
title: Freigeben von Konstanten
ms.date: 11/04/2016
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
ms.openlocfilehash: e1dc7879403072113c8b81658165c377a1bf4527
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532817"
---
# <a name="sharing-constants"></a>Freigeben von Konstanten

Konstanten für Dateifreigabemodi.

## <a name="syntax"></a>Syntax

```

#include <share.h>

```

## <a name="remarks"></a>Hinweise

Das *shflag*-Argument, das aus einem oder mehreren Manifestkonstanten besteht, bestimmt den Freigabemodus. Diese können mit den *oflag*-Argumenten kombiniert werden (finden Sie unter [Dateikonstanten](../c-runtime-library/file-constants.md)).

In der folgenden Tabelle werden die Konstanten und ihre Bedeutungen aufgelistet:

|Konstante|Bedeutung|
|--------------|-------------|
|`_SH_DENYRW`|Verweigert den Lese- und Schreibzugriff auf eine Datei.|
|`_SH_DENYWR`|Verweigert den Schreibzugriff auf eine Datei.|
|`_SH_DENYRD`|Verweigert den Lesezugriff auf eine Datei.|
|`_SH_DENYNO`|Erlaubt Lese- und Schreibzugriff.|
|`_SH_SECURE`|Legt sicheren Modus fest (freigegebenes Lesen, exklusiver Schreibzugriff).|

## <a name="see-also"></a>Siehe auch

[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)