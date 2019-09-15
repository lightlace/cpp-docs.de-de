---
title: terminate (CRT)
ms.date: 11/04/2016
api_name:
- terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- terminate
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
ms.openlocfilehash: b76ce42817fa1a6b79ef32965fcfa550a508e88d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946199"
---
# <a name="terminate-crt"></a>terminate (CRT)

Ruft [Abbruch](abort.md) oder eine Funktion auf, die Sie mit **Set_terminate**angeben.

## <a name="syntax"></a>Syntax

```C
void terminate( void );
```

## <a name="remarks"></a>Hinweise

Die Funktion " **Beenden** " wird C++ mit Ausnahmebehandlung verwendet und wird in den folgenden Fällen aufgerufen:

- Ein übereinstimmender Catch-Handler kann nicht für eine ausgelöste C++.Ausnahme gefunden werden.

- Eine Ausnahme wird während der Stapelentladung von einer Destruktorfunktion ausgelöst.

- Der Stapel ist nach dem Auslösen einer Ausnahme beschädigt.

**Beendigungs Aufrufe werden** standardmäßig [abgebrochen](abort.md) . Sie können diesen Standardwert ändern, indem Sie eine eigene Beendigungs Funktion schreiben und **Set_terminate** mit dem Namen ihrer Funktion als Argument aufrufen. **Beenden** Ruft die letzte Funktion auf, die als Argument für **Set_terminate**angegeben wurde. Weitere Informationen finden Sie unter [Nicht behandelte C++-Ausnahmen](../../cpp/unhandled-cpp-exceptions.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**terminate**|\<eh.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```cpp
// crt_terminate.cpp
// compile with: /EHsc
#include <eh.h>
#include <process.h>
#include <iostream>
using namespace std;

void term_func();

int main()
{
    int i = 10, j = 0, result;
    set_terminate( term_func );
    try
    {
        if( j == 0 )
            throw "Divide by zero!";
        else
            result = i/j;
    }
    catch( int )
    {
        cout << "Caught some integer exception.\n";
    }
    cout << "This should never print.\n";
}

void term_func()
{
    cout << "term_func() was called by terminate().\n";

    // ... cleanup tasks performed here

    // If this function does not exit, abort is called.

    exit(-1);
}
```

```Output
term_func() was called by terminate().
```

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
