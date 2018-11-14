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
ms.openlocfilehash: ecc7e5fc5afaf1d6d97f3ab46be3b1ed3001d8e5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519541"
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