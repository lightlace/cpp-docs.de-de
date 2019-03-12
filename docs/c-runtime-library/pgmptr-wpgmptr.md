---
title: _pgmptr, _wpgmptr
ms.date: 11/04/2016
f1_keywords:
- pgmptr
- _pgmptr
- wpgmptr
- _wpgmptr
helpviewer_keywords:
- wpgmptr function
- _wpgmptr function
- _pgmptr function
- pgmptr function
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
ms.openlocfilehash: 6991dfe90e58352b26d7c914e1601a68674b8a5b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749866"
---
# <a name="pgmptr-wpgmptr"></a>_pgmptr, _wpgmptr

Der Pfad der ausführbaren Datei. Veraltet; verwenden Sie [_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) und [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).

## <a name="syntax"></a>Syntax

```
extern char *_pgmptr;
extern wchar_t *_wpgmptr;
```

## <a name="remarks"></a>Anmerkungen

Wenn ein Programm über den Befehlsinterpreter (Cmd.exe) ausgeführt wird, wird `_pgmptr` automatisch mit dem vollständigen Pfad der ausführbaren Datei initialisiert. Wenn Hello.exe sich beispielsweise in C:\BIN und C:\BIN sich im Pfad befindet, wird `_pgmptr` auf C:\BIN\Hello.exe festgelegt, wenn Sie Folgendes ausführen:

```
C> hello
```

Wenn ein Programm nicht über die Befehlszeile ausgeführt wird, könnte `_pgmptr` mit dem Programmnamen (dem Basisnamen der Datei ohne Dateinamenerweiterung) oder einem Dateinamen, relativen Pfad oder vollständigen Pfad initialisiert werden.

`_wpgmptr` ist das Breitzeichen-Gegenstück von `_pgmptr` für die Verwendung mit Programmen, die `wmain` verwenden.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="requirements"></a>Anforderungen

|Variable|Erforderlicher Header|
|--------------|---------------------|
|`_pgmptr`, `_wpgmptr`|\<stdlib.h>|

## <a name="example"></a>Beispiel

Das folgende Programm veranschaulicht die Verwendung von `_pgmptr`.

```
// crt_pgmptr.c
// compile with: /W3
// The following program demonstrates the use of _pgmptr.
//
#include <stdio.h>
#include <stdlib.h>
int main( void )
{
   printf("The full path of the executing program is : %Fs\n",
     _pgmptr); // C4996
   // Note: _pgmptr is deprecated; use _get_pgmptr instead
}
```

Sie könnten `_wpgmptr` durch Ändern von `%Fs` in `%S` und `main` in `wmain` verwenden.

## <a name="see-also"></a>Siehe auch

[Globale Variablen](../c-runtime-library/global-variables.md)
