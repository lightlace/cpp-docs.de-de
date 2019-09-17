---
title: __p__commode
ms.date: 11/04/2016
api_name:
- __p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: 930eb45e8069bdd71b5a7986e229b229318d0be8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944117"
---
# <a name="__p__commode"></a>__p__commode

Verweist auf die globale Variable `_commode`, die den Standard *Datei-Commit-Modus* für E/A-Dateivorgänge angibt.

## <a name="syntax"></a>Syntax

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Rückgabewert

Zeiger auf die globale Variable `_commode`.

## <a name="remarks"></a>Anmerkungen

Die `__p__commode`-Funktion steht nur für die interne Verwendung zur Verfügung und sollte nicht vom Benutzercode aufgerufen werden.

Der Datei-Commit-Modus gibt an, wenn wichtige Daten auf den Datenträger geschrieben werden. Weitere Informationen finden Sie unter [fflush](../c-runtime-library/reference/fflush.md).

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__p\__commode|internal.h|