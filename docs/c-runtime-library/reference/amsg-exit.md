---
title: _amsg_exit
ms.date: 11/04/2016
api_name:
- _amsg_exit
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: 2d577bfcf0584ef982ab43ff98674d0cfadd14ba
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939695"
---
# <a name="_amsg_exit"></a>_amsg_exit

Gibt eine angegebene Laufzeit-Fehlermeldung aus und schließt Ihre Anwendung mit dem Fehlercode 255.

## <a name="syntax"></a>Syntax

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>Parameter

*rterrnum*<br/>
Die Identifikationsnummer einer systemdefinierten Laufzeit-Fehlermeldung.

## <a name="remarks"></a>Hinweise

Diese Funktion gibt für Konsolenanwendungen die Laufzeit-Fehlermeldung in **stderr** aus. Für Windows-Anwendungen zeigt sie die Meldung in einem Meldungsfeld an. Im Debugmodus haben Sie die Möglichkeit, den Debugger aufzurufen, bevor Sie die Anwendung beenden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|_amsg_exit|internal.h|