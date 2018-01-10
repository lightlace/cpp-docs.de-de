---
title: _set_se_translator | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_se_translator
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
dev_langs: C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7ce46b8db587337b7a9c98279efd4b89ffa8f9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setsetranslator"></a>_set_se_translator
Behandelt Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `seTransFunction`  
 Zeiger auf eine strukturierte C-Ausnahmeübersetzerfunktion, die Sie schreiben.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die vorherige Übersetzerfunktion zurück, die von `_set_se_translator` registriert wurde, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann NULL sein.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_set_se_translator` bietet eine Möglichkeit zur Behandlung von Win32-Ausnahmen (strukturierte C-Ausnahmen) als C++-typisierte Ausnahmen. Damit jede C-Ausnahme von einem C++-`catch`-Handler behandelt wird, definieren Sie zunächst eine Wrapperklasse für eine C-Ausnahme definieren, die verwendet oder abgeleitet werden kann, um einer C-Ausnahme einen speziellen Klassentyp zuzuordnen. Um diese Klasse zu verwenden, installieren Sie eine benutzerdefinierte C-Ausnahmeübersetzungsfunktion, die bei jedem Auslösen einer C-Ausnahme vom internen Mechanismus für die Ausnahmebehandlung aufgerufen wird. In der Übersetzerfunktion können Sie beliebige typisierte Ausnahmen auslösen, die von einem übereinstimmenden C++-`catch`-Handler abgefangen werden kann.  
  
 Verwenden Sie [/EHa](../../build/reference/eh-exception-handling-model.md), wenn Sie `_set_se_translator` verwenden.  
  
 Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen Sie `_set_se_translator` mit dem Namen der Übersetzungsfunktion als Argument auf. Die Übersetzerfunktion, die Sie schreiben, wird einmal für jeden Funktionsaufruf im Stapel mit `try`-Blöcken aufgerufen. Es gibt keine standardmäßige Übersetzerfunktion.  
  
 Ihre Übersetzerfunktion sollte lediglich eine C++-typisierte Ausnahme auslösen. Wenn sich die Funktion nicht auf die Auslösung beschränkt (z.B. in eine Protokolldatei schreibt), verhält sich Ihr Programm möglicherweise nicht wie erwartet, da die Anzahl von Aufrufen der Übersetzerfunktion plattformabhängig ist.  
  
 In einer Multithreadumgebung werden die Übersetzerfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Übersetzerfunktion installieren. Daher ist jeder Thread für die eigene Übersetzungsbehandlung verantwortlich. `_set_se_translator` ist für einen Thread spezifisch; eine andere DLL kann eine unterschiedliche Übersetzungsfunktion installieren.  
  
 Die `seTransFunction`-Funktion, die Sie schreiben, muss eine nativ kompilierte Funktion sein (nicht mit /clr kompiliert). Als Argumente sind eine ganze Zahl ohne Vorzeichen und ein Zeiger auf eine Win32-`_EXCEPTION_POINTERS`-Struktur erforderlich. Die Argumente sind die Rückgabewerte von Aufrufen der `GetExceptionCode`- und `GetExceptionInformation`-Funktion der Win32-API.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 Für `_set_se_translator` sind Auswirkungen bei der dynamischen Verknüpfung mit der CRT gegeben; eine andere DLL im Prozess ruft möglicherweise `_set_se_translator` auf und ersetzt Ihren Handler durch einen eigenen.  
  
 Bei Verwendung `_set_se_translator` aus verwaltetem Code (Code mit /clr kompiliert) oder gemischtem nativem und verwaltetem Code beachten Sie, dass der Übersetzer sich nur auf Ausnahmen auswirkt, die in nativem Code generiert werden. Alle verwalteten Ausnahmen, die in verwaltetem Code generiert wurden (z.B. beim Auslösen von `System::Exception`), werden nicht über die Übersetzerfunktion weitergeleitet. Mithilfe der Win32-Funktion `RaiseException` oder durch eine Systemausnahme wie eine Division durch Null-Ausnahme in verwaltetem Code ausgelöste Ausnahmen werden nicht über den Übersetzer weitergeleitet.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_se_translator`|\<eh.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_settrans.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
void SEFunc();  
void trans_func( unsigned int, EXCEPTION_POINTERS* );  
  
class SE_Exception  
{  
private:  
    unsigned int nSE;  
public:  
    SE_Exception() {}  
    SE_Exception( unsigned int n ) : nSE( n ) {}  
    ~SE_Exception() {}  
    unsigned int getSeNumber() { return nSE; }  
};  
int main( void )  
{  
    try  
    {  
        _set_se_translator( trans_func );  
        SEFunc();  
    }  
    catch( SE_Exception e )  
    {  
        printf( "Caught a __try exception with SE_Exception.\n" );  
    }  
}  
void SEFunc()  
{  
    __try  
    {  
        int x, y=0;  
        x = 5 / y;  
    }  
    __finally  
    {  
        printf( "In finally\n" );  
    }  
}  
void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )  
{  
    printf( "In trans_func.\n" );  
    throw SE_Exception();  
}  
```  
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
```  
  
## <a name="example"></a>Beispiel  
 Obwohl die von `_set_se_translator` bereitgestellte Funktionalität in verwaltetem Code nicht verfügbar ist, es ist möglich, diese Zuordnung in nativem Code zu verwenden, auch wenn sich der native Code in einer Kompilierung unter dem `/clr`-Switch befindet, solange der native Code mithilfe von `#pragma unmanaged` angegeben wird. Wenn eine strukturierte Ausnahme in verwaltetem Code ausgelöst wird, der zugeordnet werden soll, muss der Code, der die Ausnahme generiert und behandelt, mit dem `pragma` gekennzeichnet werden. Der folgende Code veranschaulicht eine mögliche Verwendung. Weitere Informationen finden Sie unter [Pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
```  
// crt_set_se_translator_clr.cpp  
// compile with: /clr  
#include <windows.h>  
#include <eh.h>  
#include <assert.h>  
#include <stdio.h>  
  
int thrower_func(int i) {  
   int j = i/0;  
  return 0;  
}  
  
class CMyException{  
};  
  
#pragma unmanaged  
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS pExp )  
{  
printf("Translating the structured exception to a C++"  
             " exception.\n");  
throw CMyException();  
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
  
int main(int argc, char** argv) {  
    _set_se_translator(my_trans_func);  
    DoTest();  
    return 0;  
}  
```  
  
```Output  
Translating the structured exception to a C++ exception.  
Caught CMyException.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)