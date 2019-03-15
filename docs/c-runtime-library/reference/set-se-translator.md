---
title: _set_se_translator
ms.date: 02/21/2018
apiname:
- _set_se_translator
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
- _set_se_translator
- set_se_translator
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
ms.openlocfilehash: 18ee500d7b884d1934c29dc91d9bcb03d507680d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808377"
---
# <a name="setsetranslator"></a>_set_se_translator

Legen Sie eine pro-Thread-Callback-Funktion zum Übersetzen von Win32-Ausnahmen (C-strukturierte Ausnahmen) in C++-typisierte Ausnahmen.

## <a name="syntax"></a>Syntax

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>Parameter

*seTransFunction*<br/>
Zeiger auf eine strukturierte C-Ausnahmeübersetzerfunktion, die Sie schreiben.

## <a name="return-value"></a>Rückgabewert

Gibt ein Zeiger auf die vorherige übersetzerfunktion registriert **_set_se_translator**, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; Dieser Wert kann sein **"nullptr"**.

## <a name="remarks"></a>Hinweise

Die **_set_se_translator** Funktion bietet eine Möglichkeit zum Verarbeiten von Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen. Jede C-Ausnahme von C++ behandelt werden können **catch** Handler, definieren Sie zunächst eine C-Ausnahme-Wrapperklasse, die verwendet oder daraus abgeleitet wurden, einen bestimmten Klassentyp in eine C-Ausnahme zugeordnet werden kann. Um diese Klasse zu verwenden, installieren Sie eine benutzerdefinierte C-Ausnahmeübersetzungsfunktion, die bei jedem Auslösen einer C-Ausnahme vom internen Mechanismus für die Ausnahmebehandlung aufgerufen wird. In der übersetzerfunktion können Sie beliebige typisierte Ausnahmen, die von einem übereinstimmenden C++ abgefangen werden kann auslösen **catch** Handler.

Verwenden Sie [/EHa](../../build/reference/eh-exception-handling-model.md) Verwendung **_set_se_translator**.

Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen **_set_se_translator** mit dem Namen Ihrer Übersetzungsfunktion als Argument. Die Translator-Funktion, die Sie schreiben wird einmal für jeden Funktionsaufruf im Stapel mit aufgerufen **versuchen** Blöcke. Es gibt keine standardmäßige Übersetzerfunktion.

Ihre Übersetzerfunktion sollte lediglich eine C++-typisierte Ausnahme auslösen. Wenn sich die Funktion nicht auf die Auslösung beschränkt (z.B. in eine Protokolldatei schreibt), verhält sich Ihr Programm möglicherweise nicht wie erwartet, da die Anzahl von Aufrufen der Übersetzerfunktion plattformabhängig ist.

In einer Multithreadumgebung werden die Übersetzerfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Übersetzerfunktion installieren. Daher ist jeder Thread für die eigene Übersetzungsbehandlung verantwortlich. **_set_se_translator** bezieht sich auf einen Thread eine andere DLL kann eine unterschiedliche Übersetzungsfunktion installieren.

Die *SeTransFunction* Funktion, die Sie schreiben, muss eine nativ kompilierte Funktion (nicht mit/CLR kompiliert) sein. Es muss eine Ganzzahl ohne Vorzeichen und ein Zeiger auf eine Win32-dauern **_EXCEPTION_POINTERS** Struktur als Argumente. Die Argumente sind die Rückgabewerte von Aufrufen der Win32-API **GetExceptionCode** und **GetExceptionInformation** -Funktion.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

Für **_set_se_translator**, sind Auswirkungen bei der dynamischen Verknüpfung mit der CRT; eine andere DLL im Prozess möglicherweise Aufrufen **_set_se_translator** und ersetzt Ihren Handler durch einen eigenen.

Bei Verwendung **_set_se_translator** aus verwaltetem Code (Code mit/CLR kompiliert) oder gemischten systemeigenen und verwalteten Code, denken Sie daran, dass der Konvertierer in systemeigenem Code nur generierte Ausnahmen auswirkt. Alle verwalteten Ausnahmen, die in verwaltetem Code generiert wurden (z.B. beim Auslösen von `System::Exception`), werden nicht über die Übersetzerfunktion weitergeleitet. Mithilfe der Win32-Funktion in verwaltetem Code ausgelöste Ausnahmen **RaiseException** oder durch eine Systemausnahme wie eine Division durch Null-Ausnahme über den Übersetzer weitergeleitet werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_se_translator**|\<eh.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```cpp
// crt_settrans.cpp
// compile with: cl /W4 /EHa crt_settrans.cpp
#include <stdio.h>
#include <windows.h>
#include <eh.h>
#include <exception>

class SE_Exception : public std::exception
{
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception( unsigned int n ) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

void SEFunc()
{
    __try
    {
        printf( "In __try, about to force exception\n" );
        int x = 5;
        int y = 0;
        int *p = &y;
        *p = x / *p;
    }
    __finally
    {
        printf( "In __finally\n" );
    }
}

void trans_func(unsigned int u, EXCEPTION_POINTERS*)
{
    throw SE_Exception(u);
}

int main()
{
    auto original = _set_se_translator(trans_func);
    try
    {
        SEFunc();
    }
    catch(SE_Exception& e)
    {
        printf("Caught a __try exception, error %8.8x.\n", e.getSeNumber());
    }
    _set_se_translator(original);
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example"></a>Beispiel

Obwohl die Funktionalität von bereitgestellten **_set_se_translator** ist in verwaltetem Code nicht verfügbar ist, es ist möglich, verwenden Sie diese Zuordnung in nativem Code, auch wenn sich der native Code in einer Kompilierung unter der **"/ CLR"** zu wechseln, solange der native Code mithilfe von angegeben wird `#pragma unmanaged`. Wenn eine strukturierte Ausnahme in verwaltetem Code ausgelöst wird, die zugeordnet werden soll, muss der Code, der generiert und behandelt die Ausnahme markiert werden `#pragma unmanaged`. Der folgende Code veranschaulicht eine mögliche Verwendung. Weitere Informationen finden Sie unter [Pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>
#include <exception>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception {
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw SE_Exception(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(SE_Exception& e)
    {
        printf("Caught SE_Exception, error %8.8x\n", e.getSeNumber());
    }
    catch(...)
    {
        printf("Caught unexpected SEH exception.\n");
    }
}
#pragma managed

int main() {
    auto original = _set_se_translator(my_trans_func);
    DoTest();
    _set_se_translator(original);
}
```

```Output
Caught SE_Exception, error c0000094
```

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
