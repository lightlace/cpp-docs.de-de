---
title: _set_se_translator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d4a5c9e86023ea47f23b648cad1a4dffedf905b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411519"
---
# <a name="setsetranslator"></a>_set_se_translator

Legen Sie eine Rückruffunktion threadspezifisches zum Übersetzen von Win32-Ausnahmen (C-strukturierte Ausnahmen) in C++-typisierte Ausnahmen.

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

Gibt ein Zeiger auf die vorherige Translator-Funktion, indem Sie registriert **_set_se_translator**, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine previous-Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherstellen; Mögliche Werte sind **Nullptr**.

## <a name="remarks"></a>Hinweise

Die **_set_se_translator** -Funktion bietet eine Möglichkeit zum Verarbeiten von Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen. Jede C-Ausnahme von C++ behandelt werden sollen **catch** Handler, definieren Sie zunächst eine C-Ausnahme-Wrapperklasse, die verwendet oder abgeleitet, einen bestimmten Klassentyp eine C-Ausnahme zugeordnet werden kann. Um diese Klasse zu verwenden, installieren Sie eine benutzerdefinierte C-Ausnahmeübersetzungsfunktion, die bei jedem Auslösen einer C-Ausnahme vom internen Mechanismus für die Ausnahmebehandlung aufgerufen wird. Innerhalb der Translator-Funktion, Sie können eine beliebige typisierte Ausnahme, die von übereinstimmenden C++ abgefangen werden kann auslösen **catch** Handler.

Verwenden Sie [/EHa](../../build/reference/eh-exception-handling-model.md) Verwendung **_set_se_translator**.

Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen **_set_se_translator** mit den Namen Ihrer Übersetzungsfunktion als Argument. Der Konvertierer-Funktion, den Sie schreiben wird einmal für jeden Funktionsaufruf im Stapel mit **versuchen** blockiert. Es gibt keine standardmäßige Übersetzerfunktion.

Ihre Übersetzerfunktion sollte lediglich eine C++-typisierte Ausnahme auslösen. Wenn sich die Funktion nicht auf die Auslösung beschränkt (z.B. in eine Protokolldatei schreibt), verhält sich Ihr Programm möglicherweise nicht wie erwartet, da die Anzahl von Aufrufen der Übersetzerfunktion plattformabhängig ist.

In einer Multithreadumgebung werden die Übersetzerfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Übersetzerfunktion installieren. Daher ist jeder Thread für die eigene Übersetzungsbehandlung verantwortlich. **_set_se_translator** bezieht sich auf einen Thread eine andere DLL eine anderen Übersetzungsfunktion installieren kann.

Die *SeTransFunction* -Funktion, die Sie schreiben muss eine nativ kompilierte Funktion (nicht mit/CLR kompiliert). Muss dauert eine Ganzzahl ohne Vorzeichen und einen Zeiger auf eine Win32- **_EXCEPTION_POINTERS** Struktur als Argumente. Die Argumente sind die Rückgabewerte der Aufrufe der Win32-API **GetExceptionCode** und **GetExceptionInformation** bzw. Funktionen.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

Für **_set_se_translator**, gibt es Auswirkungen auf die beim Verknüpfen von dynamisch mit der CRT: eine andere DLL im Prozess möglicherweise Aufrufen **_set_se_translator** , und Ersetzen Sie den Handler, ein eigenes.

Bei Verwendung **_set_se_translator** aus verwaltetem Code (Code, der mit "/ CLR" kompiliert) oder gemischten systemeigenen und verwalteten Code, beachten Sie, dass das Konvertierungsprogramm generierte in systemeigenen Code nur Ausnahmen beeinflusst werden. Alle verwalteten Ausnahmen, die in verwaltetem Code generiert wurden (z.B. beim Auslösen von `System::Exception`), werden nicht über die Übersetzerfunktion weitergeleitet. In verwaltetem Code mithilfe von Win32-Funktion ausgelöste Ausnahmen **RaiseException** oder aufgrund einer Systemausnahme, wie eine Division durch Null-Ausnahme über das Konvertierungsprogramm weitergeleitet.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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

class SE_Exception
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

Obwohl die Funktionalität von bereitgestellten **_set_se_translator** ist in verwaltetem Code nicht verfügbar ist, es ist möglich, verwenden diese Zuordnung in systemeigenem Code, selbst wenn der systemeigene Code in einer Kompilierung unter ist die **"/ CLR"** wechseln, solange der systemeigene Code mithilfe von angegeben wird `#pragma unmanaged`. Wenn eine strukturierte Ausnahme in verwaltetem Code ausgelöst wird, die zugeordnet werden soll, muss der Code, der generiert und die Ausnahme behandelt markiert werden `#pragma unmanaged`. Der folgende Code veranschaulicht eine mögliche Verwendung. Weitere Informationen finden Sie unter [Pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class CMyException{
private:
    unsigned int nSE;
public:
    CMyException() : nSE{ 0 } {}
    CMyException(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw CMyException(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(CMyException e)
    {
        printf("Caught CMyException.\n");
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
Caught CMyException, error c0000094
```

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
