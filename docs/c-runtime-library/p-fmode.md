---
title: __p__fmode
ms.date: 11/04/2016
apiname:
- __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: 59687cca87d283682c4b7231b5f8c1a55ff512db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579714"
---
# <a name="pfmode"></a>__p__fmode

Verweist auf die globale Variable `_fmode`, die den Standard *Datei-Commit-Modus* für E/A-Dateivorgänge angibt.

## <a name="syntax"></a>Syntax

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Rückgabewert

Zeiger auf die globale Variable `_fmode`.

## <a name="remarks"></a>Hinweise

Die `__p__fmode`-Funktion steht nur für die interne Verwendung zur Verfügung und sollte nicht vom Benutzercode aufgerufen werden.

Der Dateiübersetzungsmodus gibt entweder `binary`- oder `text`-Übersetzungen für [_open](../c-runtime-library/reference/open-wopen.md)- und [_pipe](../c-runtime-library/reference/pipe.md)-E/A-Vorgänge an. Weitere Informationen finden Sie unter [_fmode](../c-runtime-library/fmode.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__p\__fmode|stdlib.h|