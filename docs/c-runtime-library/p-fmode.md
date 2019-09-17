---
title: __p__fmode
ms.date: 11/04/2016
api_name:
- __p__fmode
api_location:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: 6f7676fc5c9958be3d0567e6bf22a11367094150
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939983"
---
# <a name="__p__fmode"></a>__p__fmode

Verweist auf die globale Variable `_fmode`, die den Standard *Datei-Commit-Modus* für E/A-Dateivorgänge angibt.

## <a name="syntax"></a>Syntax

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Rückgabewert

Zeiger auf die globale Variable `_fmode`.

## <a name="remarks"></a>Anmerkungen

Die `__p__fmode`-Funktion steht nur für die interne Verwendung zur Verfügung und sollte nicht vom Benutzercode aufgerufen werden.

Der Dateiübersetzungsmodus gibt entweder `binary`- oder `text`-Übersetzungen für [_open](../c-runtime-library/reference/open-wopen.md)- und [_pipe](../c-runtime-library/reference/pipe.md)-E/A-Vorgänge an. Weitere Informationen finden Sie unter [_fmode](../c-runtime-library/fmode.md).

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__p\__fmode|stdlib.h|