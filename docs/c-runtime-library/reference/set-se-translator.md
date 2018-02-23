---
title: _set_se_translator | Microsoft-Dokumentation
ms.custom: 
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b5eec59acfe65189368a9b0555c3065b7159aae
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2018
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

*seTransFunction*  
Zeiger auf eine strukturierte C-Ausnahmeübersetzerfunktion, die Sie schreiben.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorherige Übersetzerfunktion zurück, die von `_set_se_translator` registriert wurde, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine previous-Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherstellen; Mögliche Werte sind **Nullptr**.

## <a name="remarks"></a>Hinweise

Die Funktion `_set_se_translator` bietet eine Möglichkeit zur Behandlung von Win32-Ausnahmen (strukturierte C-Ausnahmen) als C++-typisierte Ausnahmen. Damit jede C-Ausnahme von einem C++-`catch`-Handler behandelt wird, definieren Sie zunächst eine Wrapperklasse für eine C-Ausnahme definieren, die verwendet oder abgeleitet werden kann, um einer C-Ausnahme einen speziellen Klassentyp zuzuordnen. Um diese Klasse zu verwenden, installieren Sie eine benutzerdefinierte C-Ausnahmeübersetzungsfunktion, die bei jedem Auslösen einer C-Ausnahme vom internen Mechanismus für die Ausnahmebehandlung aufgerufen wird. In der Übersetzerfunktion können Sie beliebige typisierte Ausnahmen auslösen, die von einem übereinstimmenden C++-`catch`-Handler abgefangen werden kann.

Verwenden Sie [/EHa](../../build/reference/eh-exception-handling-model.md), wenn Sie `_set_se_translator` verwenden.

Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen `_set_se_translator` mit den Namen Ihrer Übersetzungsfunktion als Argument. Die Übersetzerfunktion, die Sie schreiben, wird einmal für jeden Funktionsaufruf im Stapel mit `try`-Blöcken aufgerufen. Es gibt keine standardmäßige Übersetzerfunktion.

Ihre Übersetzerfunktion sollte lediglich eine C++-typisierte Ausnahme auslösen. Wenn sich die Funktion nicht auf die Auslösung beschränkt (z.B. in eine Protokolldatei schreibt), verhält sich Ihr Programm möglicherweise nicht wie erwartet, da die Anzahl von Aufrufen der Übersetzerfunktion plattformabhängig ist.

In einer Multithreadumgebung werden die Übersetzerfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Übersetzerfunktion installieren. Daher ist jeder Thread für die eigene Übersetzungsbehandlung verantwortlich. `_set_se_translator` ist für einen Thread spezifisch; eine andere DLL kann eine unterschiedliche Übersetzungsfunktion installieren.

Die *SeTransFunction* -Funktion, die Sie schreiben muss eine nativ kompilierte Funktion (nicht mit/CLR kompiliert). Als Argumente sind eine ganze Zahl ohne Vorzeichen und ein Zeiger auf eine Win32-`_EXCEPTION_POINTERS`-Struktur erforderlich. Die Argumente sind die Rückgabewerte von Aufrufen der `GetExceptionCode`- und `GetExceptionInformation`-Funktion der Win32-API.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

Für `_set_se_translator` sind Auswirkungen bei der dynamischen Verknüpfung mit der CRT gegeben; eine andere DLL im Prozess ruft möglicherweise `_set_se_translator` auf und ersetzt Ihren Handler durch einen eigenen.

Bei Verwendung `_set_se_translator` aus verwaltetem Code (Code mit /clr kompiliert) oder gemischtem nativem und verwaltetem Code beachten Sie, dass der Übersetzer sich nur auf Ausnahmen auswirkt, die in nativem Code generiert werden. Alle verwalteten Ausnahmen, die in verwaltetem Code generiert wurden (z.B. beim Auslösen von `System::Exception`), werden nicht über die Übersetzerfunktion weitergeleitet. Mithilfe der Win32-Funktion `RaiseException` oder durch eine Systemausnahme wie eine Division durch Null-Ausnahme in verwaltetem Code ausgelöste Ausnahmen werden nicht über den Übersetzer weitergeleitet.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`_set_se_translator`|\<eh.h>|

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

Obwohl die von `_set_se_translator` bereitgestellte Funktionalität in verwaltetem Code nicht verfügbar ist, es ist möglich, diese Zuordnung in nativem Code zu verwenden, auch wenn sich der native Code in einer Kompilierung unter dem `/clr`-Switch befindet, solange der native Code mithilfe von `#pragma unmanaged` angegeben wird. Wenn eine strukturierte Ausnahme in verwaltetem Code ausgelöst wird, die zugeordnet werden soll, muss der Code, der generiert und die Ausnahme behandelt markiert werden `#pragma unmanaged`. Der folgende Code veranschaulicht eine mögliche Verwendung. Weitere Informationen finden Sie unter [Pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

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

[Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)  
[set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)  
[set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)  
[terminate](../../c-runtime-library/reference/terminate-crt.md)  
[unexpected](../../c-runtime-library/reference/unexpected-crt.md)  
