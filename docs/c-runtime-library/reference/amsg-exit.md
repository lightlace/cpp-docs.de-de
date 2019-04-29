---
title: _amsg_exit
ms.date: 11/04/2016
apiname:
- _amsg_exit
apilocation:
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
apitype: DLLExport
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: 87cd08a6c60a1e29b8a8e15edbfdd69d338d875d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335619"
---
# <a name="amsgexit"></a>_amsg_exit

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