---
title: TZNAME_MAX
ms.date: 10/22/2018
f1_keywords:
- TZNAME_MAX
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
ms.openlocfilehash: 1d55f88717613b735cbfd04c5790f05544e1d4c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547913"
---
# <a name="tznamemax"></a>TZNAME_MAX

**Veraltet**. Die maximale zulässige Zeichenfolgenlänge für eine Zeitzonennamens-Variable. Dieses Makro wurde in Visual Studio 2012 und früheren Versionen in \<limits.h> definiert. In Visual Studio 2013 und höheren Versionen ist es nicht definiert. Verwenden Sie [_get_tzname](../c-runtime-library/reference/get-tzname.md), um die für den Zeitzonennamen erforderliche Länge abzurufen.

## <a name="syntax"></a>Syntax

```
#include <limits.h>
```

## <a name="see-also"></a>Siehe auch

[Umgebungskonstanten](../c-runtime-library/environmental-constants.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
