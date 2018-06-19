---
title: _amsg_exit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbb7f46bb4f3c942fd1c9e1a1d45c1ccf48739f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392795"
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

|Routine|Erforderlicher Header|
|-------------|---------------------|
|_amsg_exit|internal.h|