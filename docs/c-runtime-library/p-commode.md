---
title: __p__commode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
dev_langs:
- C++
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f610b26c79201f3431b6263a002b59df7456cfe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082442"
---
# <a name="pcommode"></a>__p__commode

Verweist auf die globale Variable `_commode`, die den Standard *Datei-Commit-Modus* für E/A-Dateivorgänge angibt.

## <a name="syntax"></a>Syntax

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Rückgabewert

Zeiger auf die globale Variable `_commode`.

## <a name="remarks"></a>Hinweise

Die `__p__commode`-Funktion steht nur für die interne Verwendung zur Verfügung und sollte nicht vom Benutzercode aufgerufen werden.

Der Datei-Commit-Modus gibt an, wenn wichtige Daten auf den Datenträger geschrieben werden. Weitere Informationen finden Sie unter [fflush](../c-runtime-library/reference/fflush.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__p\__commode|internal.h|