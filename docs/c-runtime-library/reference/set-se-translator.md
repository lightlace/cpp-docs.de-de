---
title: "_set_se_translator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_se_translator"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_se_translator"
  - "set_se_translator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_se_translator-Funktion"
  - "Ausnahmebehandlung, Ändern"
  - "set_se_translator-Funktion"
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _set_se_translator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Behandelt Win32\-Ausnahmen \(C\-strukturierte Ausnahmen\) als C\+\+\-typisierte Ausnahmen.  
  
## Syntax  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### Parameter  
 `seTransFunction`  
 Zeiger auf die Übersetzerfunktion Wechselstrom\-strukturierterAusnahme, die Sie schreiben.  
  
## Rückgabewert  
 Gibt einen Zeiger zur vorherigen Übersetzerfunktion zurück, die von `_set_se_translator` registriert wird, dass die vorherige Funktion später wiederhergestellt werden kann.  Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; Dieser Wert kann NULL sein.  
  
## Hinweise  
 Die `_set_se_translator`\-Funktion bietet eine Möglichkeit, Win32\-Ausnahmen \(C\-strukturierte Ausnahmen\) als C\+\+\-Typausnahmen zu behandeln.  Um von Handler eine C\+\+\-Headerdatei `catch` behandelt werden C\-Ausnahme zuzulassen jedem, definieren Sie zuerst Wechselstrom\-Ausnahmewrapperklasse der verwendet werden oder berechnet werden kann aus, um einen speziellen Klassentyp Wechselstrom\-Ausnahme zuzuschreiben.  Um diese Klasse zu verwenden, installieren Sie eine benutzerdefinierte C\-Ausnahmeübersetzerfunktion die von der internen Wechselstrom\-Ausnahme des Mechanismus für die Ausnahmenbehandlung jedes Mal ausgelöst wird aufgerufen wird.  Innerhalb der Übersetzerfunktion können Sie typisierte jede Ausnahme auslösen, die von einem entsprechenden Handler C\+\+ `catch` abgefangen werden kann.  
  
 Sie müssen [\/EHa](../../build/reference/eh-exception-handling-model.md) verwenden, wenn Sie `_set_se_translator` verwenden.  
  
 Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen Sie `_set_se_translator`  mit dem Namen der Übersetzungsfunktion als Argument auf.  Die Übersetzerfunktion, die Sie schreiben, wird einmal für jeden Funktionsaufruf im Stapel aufgerufen, der Blöcke `try`  verfügt.  Es gibt keine Standardübersetzerfunktion.  
  
 die Übersetzerfunktion sollte nicht länger als Aktionen auslösen Eingabe eine C\+\+\-Ausnahme.  Wenn alle sie zusätzlich zum Auslösen bewirkt \(wie das Schreiben in eine Protokolldatei\), Vorkommnisse kann das Programm nicht wie erwartet, da die Häufigkeit, die die Übersetzerfunktion aufgerufen wird, plattformabhängig ist.  
  
 In einer Multithreadumgebung werden Übersetzerfunktionen separat für jeden Thread beibehalten.  Anforderungen der neue Threads, eine eigene Übersetzerfunktion zu installieren.  Daher ist jeder Thread verantwortlich für die eigene Übersetzungsbehandlung.  `_set_se_translator`  entspricht einem Thread vorgesehen; eine andere DLL kann eine andere Übersetzungsfunktion installieren.  
  
 Die `seTransFunction`\-Funktion, die Sie schreiben, muss eine Eingeboren\-kompilierte Funktion sein \(kompiliert nicht mit \/clr\).  Sie muss eine ganze Zahl ohne Vorzeichen und einen Zeiger auf eine Struktur Win32\- `_EXCEPTION_POINTERS` als Argumente verwenden.  Die Argumente werden Rückgabewerte von Aufrufen der Win32\-API `GetExceptionCode` und `GetExceptionInformation`\-Funktionen, bzw.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 Für `_set_se_translator` gibt es Auswirkungen, wenn es sich dynamisch mit CRT verknüpft; eine andere DLL im Prozess `_set_se_translator` aufrufen und hat möglicherweise den Handler durch eigene.  
  
 Wenn Sie in verwaltetem Code `_set_se_translator` \(der Code kompiliert mit \/clr\) oder gemischtem systemeigenen und verwalteten Code verwenden, beachten Sie, dass der die Ausnahmen Übersetzer auswirkt, die nur im systemeigenen Code generiert werden.  Keine verwalteten Ausnahmen, die in verwaltetem Code generiert werden \(z, wenn eine `System::Exception` ausgelöst wird\), werden nicht durch die Übersetzerfunktion weitergeleitet.  Ausnahmen, die in verwaltetem Code mithilfe der Win32\-Funktion `RaiseException` ausgelöst werden oder über eine Systemausnahme wie eine Division durch nullausnahme verursacht sind, werden durch den Übersetzer weitergeleitet.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_set_se_translator`|\<eh.h\>|  
  
 Die Funktionalität, die von `_set_se_translator` bereitgestellt wird, nicht in Code verfügbar, der mit der [\/clr: rein](../../build/reference/clr-common-language-runtime-compilation.md)\-Compileroption kompiliert wird.  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
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
  
  **In trans\_func.**  
**In schließlich**  
**Fing \_\_try eine Ausnahme mit SE\_Exception ab.**   
## Beispiel  
 Obwohl die Funktionalität, die von `_set_se_translator` bereitgestellt wird, nicht in verwalteten Code verfügbar ist, ist es möglich, diese Zuordnung im systemeigenen Code zu verwenden, auch wenn dieser Code systemeigene einer Kompilierung unter dem Schalter `/clr` ist, solange der systemeigene Code mithilfe von `#pragma unmanaged` angegeben wird.  Wenn eine strukturierte Ausnahme in verwaltetem Code ausgelöst wird, der zugeordnet werden soll, müssen der Code, der generiert und die Steuerpunkte die Ausnahme mit `pragma` gekennzeichnet werden.  Im folgenden Code wird eine mögliche Verwendung an.  Weitere Informationen finden Sie unter [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
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
  
  **Übersetzung der strukturierten Ausnahmehandlers zu eine C\+\+\-Ausnahme.**  
**Abgefangenes CMyException.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)