---
title: TZNAME_MAX | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- TZNAME_MAX
dev_langs:
- C++
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc44ff3178493132c1b8d5dc168cee6be4c5bc56
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990151"
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
