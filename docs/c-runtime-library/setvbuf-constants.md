---
title: setvbuf-Konstanten
ms.date: 11/04/2016
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
ms.openlocfilehash: 8936789f4e3c9349e9d79616c8506c044dc79f70
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220399"
---
# <a name="setvbuf-constants"></a>setvbuf-Konstanten

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Hinweise

Diese Konstanten stellen den Puffertyp für `setvbuf` dar.

Die möglichen Werte werden mit den folgenden Manifestkonstanten angegeben:

|Konstante|Bedeutung|
|--------------|-------------|
|`_IOFBF`|Vollständige Pufferung: Der im Aufruf von `setvbuf` angegebene Puffer wird verwendet, und seine Größe ist wie im `setvbuf`-Aufruf angegeben. Wenn der Zeiger auf den Puffer **NULL** ist, wird der automatisch zugeordnete Puffer mit der angegebenen Größe verwendet.|
|`_IOLBF`|Wie in `_IOFBF`.|
|`_IONBF`|Unabhängig von Argumenten im Aufruf von `setvbuf` wird kein Puffer verwendet.|

## <a name="see-also"></a>Siehe auch

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
