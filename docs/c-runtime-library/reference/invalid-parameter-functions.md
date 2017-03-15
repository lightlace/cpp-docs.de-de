---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 49ae87567cd311e271a0ab50d7112a4a8f0c1b4a
ms.lasthandoff: 02/24/2017

---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
Diese Funktionen werden von der C-Laufzeitbibliothek verwendet, um ungültige Parameter zu behandeln, die an CRT-Bibliotheksfunktionen übergeben werden. Ihr Code verwendet diese Funktionen möglicherweise auch zur Unterstützung der Standard- oder anpassbaren Behandlung der ungültigen Parameter.

## <a name="syntax"></a>Syntax
```
extern "C" void __cdecl 
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);  

extern "C" void __cdecl 
_invalid_parameter_noinfo(void);  

extern "C" __declspec(noreturn) void __cdecl 
_invalid_parameter_noinfo_noreturn(void);  

extern "C" __declspec(noreturn) void __cdecl 
_invoke_watson(  
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="return-value"></a>Rückgabewert
Die Funktionen geben keinen Wert zurück. Die `_invalid_parameter_noinfo_noreturn`- und `_invoke_watson`-Funktionen gehen nicht an den Aufrufer zurück, und in einigen Fällen gehen `_invalid_parameter` und `_invalid_parameter_noinfo` möglicherweise nicht an den Aufrufer zurück.

## <a name="parameters"></a>Parameter
`expression`  
Eine Zeichenfolge mit dem Quellcode-Parameterausdruck, der nicht gültig ist.

`function_name`  
Der Name der Funktion, die den Handler aufgerufen hat.

`file_name`  
Die Quellcodedatei, in der der Handler aufgerufen wurde.

`line_number`  
Die Zeilennummer im Quellcode, in der der Handler aufgerufen wurde.

`reserved`  
Nicht verwendet.

## <a name="remarks"></a>Hinweise
Wenn Funktionen der C-Laufzeitbibliothek ungültige Parameter übergeben, rufen die Bibliotheksfunktionen einen *Handler für ungültige Parameter* auf, eine Funktion, die möglicherweise vom Programmierer angegeben wird, um mehrere Aufgaben auszuführen. Es kann dem Benutzer möglicherweise das Problem melden, in ein Protokoll schreiben, einen Debugger anhalten, das Programm beenden oder gar nichts machen. Wenn keine Funktion durch den Programmierer angegeben wird, wird ein Standardhandler, `_invoke_watson`, aufgerufen.

Wenn standardmäßig ein ungültiger Parameter im Debugcode identifiziert wird, rufen Funktionen der CRT-Bibliothek die Funktion `_invalid_parameter` mithilfe von ausführlichen Parametern auf. Im Nichtdebugcode wird die `_invalid_parameter_noinfo`-Funktion aufgerufen, welche die `_invalid_parameter`-Funktion mithilfe von leeren Parametern aufruft. Wenn die Nichtdebug-CRT-Bibliotheksfunktion eine Programmterminierung benötigt, wird die `_invalid_parameter_noinfo_noreturn`-Funktion aufgerufen, welche die `_invalid_parameter`-Funktion mithilfe von leeren Parametern aufruft, gefolgt von einem Aufruf der `_invoke_watson`-Funktion, um die Programmterminierung zu erzwingen.

Die `_invalid_parameter`-Funktion überprüft, ob ein benutzerdefinierter ungültiger Parametertyphandler festgelegt wurde, und wenn ja, ruft sie ihn auf. Beispielsweise wird die Funktion zurückgegebene, wenn ein benutzerdefinierter lokaler Threadhandler durch einen Aufruf von [set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) im aktuellen Thread festgelegt wurde. Andernfalls wird sie aufgerufen, wenn ein benutzerdefinierter globaler ungültiger Parametertyphandler durch einen Aufruf von [set_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) festgelegt wurde; danach springt die Funktion zurück. Andernfalls wird der standardmäßige Handler `_invoke_watson` aufgerufen. Das Standardverhalten von `_invoke_watson` ist das Beenden des Programms. Benutzerdefinierte Handler werden möglicherweise beendet oder zurückgegeben. Es wird empfohlen, dass benutzerdefinierte Handler das Programm beenden, es sei denn, die Wiederherstellung ist sicher. 

Wenn der Standardhandler `_invoke_watson` aufgerufen wird, wird der Prozessor, falls dieser eine [__fastfail](../../intrinsics/fastfail.md)-Operation unterstützt, mithilfe eines Parameters von `FAST_FAIL_INVALID_ARG` aufgerufen, und der Vorgang wird fortgesetzt. Andernfalls wird eine Fast-Fail-Ausnahme ausgelöst, die durch einen angefügten Debugger abgefangen wird. Wenn der Vorgang fortgesetzt werden kann, wird er durch einen Aufruf der Windows `TerminateProcess`-Funktion mit einem Ausnahmecodestatus `STATUS_INVALID_CRUNTIME_PARAMETER` beendet. 

## <a name="requirements"></a>Anforderungen  
|Funktion|Erforderlicher Header|  
|--------------|------------------|  
|`_invalid_parameter`, `_invalid_parameter_noinfo`, `_invalid_parameter_noinfo_noreturn`, `_invoke_watson`|\<corecrt.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)  
 [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)  
 [Parametervalidierung](../../c-runtime-library/parameter-validation.md)

