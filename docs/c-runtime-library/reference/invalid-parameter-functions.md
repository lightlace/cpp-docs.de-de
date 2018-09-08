---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26e66b6ad47af521bb5188860d7d987e9d3b5f6b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100836"
---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

Diese Funktionen werden von der C-Laufzeitbibliothek verwendet, um ungültige Parameter zu behandeln, die an CRT-Bibliotheksfunktionen übergeben werden. Ihr Code verwendet diese Funktionen möglicherweise auch zur Unterstützung der Standard- oder anpassbaren Behandlung der ungültigen Parameter.

## <a name="syntax"></a>Syntax

```C
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

## <a name="parameters"></a>Parameter

*Ausdruck*<br/>
Eine Zeichenfolge mit dem Quellcode-Parameterausdruck, der nicht gültig ist.

*function_name*<br/>
Der Name der Funktion, die den Handler aufgerufen hat.

*file_name*<br/>
Die Quellcodedatei, in der der Handler aufgerufen wurde.

*Zeilennummer*<br/>
Die Zeilennummer im Quellcode, in der der Handler aufgerufen wurde.

*Reserviert*<br/>
Nicht verwendet.

## <a name="return-value"></a>Rückgabewert

Die Funktionen geben keinen Wert zurück. Die **_invalid_parameter_noinfo_noreturn** und **_invoke_watson** Funktionen werden nicht zurück an den Aufrufer, und klicken Sie in einigen Fällen **_invalid_parameter** und **_invalid_parameter_noinfo** möglicherweise nicht an den Aufrufer zurück.

## <a name="remarks"></a>Hinweise

Wenn Funktionen der C-Laufzeitbibliothek ungültige Parameter übergeben, rufen die Bibliotheksfunktionen einen *Handler für ungültige Parameter* auf, eine Funktion, die möglicherweise vom Programmierer angegeben wird, um mehrere Aufgaben auszuführen. Es kann dem Benutzer möglicherweise das Problem melden, in ein Protokoll schreiben, einen Debugger anhalten, das Programm beenden oder gar nichts machen. Wenn keine Funktion, wird dem Programmierer, ein Standardhandler angegeben wird, **_invoke_watson**, aufgerufen wird.

In der Standardeinstellung, wenn ungültige Parameter im Debugcode identifiziert wird CRT-Bibliotheksfunktionen rufen Sie die Funktion **_invalid_parameter** mithilfe von ausführlichen Parametern. Im nichtdebugcode die **_invalid_parameter_noinfo** Funktion aufgerufen wird, wird die **_invalid_parameter** funktionieren mithilfe von leeren Parametern. Wenn die nichtdebug-CRT-Bibliotheksfunktion eine programmterminierung benötigt die **_invalid_parameter_noinfo_noreturn** Funktion aufgerufen wird, wird die **_invalid_parameter** -Funktion mithilfe von leeren Parameter, gefolgt von einem Aufruf der **_invoke_watson** Funktion, um die programmterminierung zu erzwingen.

Die **_invalid_parameter** -Funktion überprüft, ob ein ungültiger parametertyphandler festgelegt wurde, und wenn dies der Fall ist, ruft er. Beispielsweise wird die Funktion zurückgegebene, wenn ein benutzerdefinierter lokaler Threadhandler durch einen Aufruf von [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) im aktuellen Thread festgelegt wurde. Andernfalls wird sie aufgerufen, wenn ein benutzerdefinierter globaler ungültiger Parametertyphandler durch einen Aufruf von [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) festgelegt wurde; danach springt die Funktion zurück. Andernfalls der Standardhandler **_invoke_watson** aufgerufen wird. Das Standardverhalten des **_invoke_watson** besteht darin, das Programm beendet. Benutzerdefinierte Handler werden möglicherweise beendet oder zurückgegeben. Es wird empfohlen, dass benutzerdefinierte Handler das Programm beenden, es sei denn, die Wiederherstellung ist sicher.

Wenn der standardmäßige Handler **_invoke_watson** aufgerufen wird, wenn der Prozessor unterstützt eine [__fastfail](../../intrinsics/fastfail.md) -Vorgang mithilfe eines Parameters, der Aufruf erfolgte **FAST_FAIL_INVALID_ARG** und der Prozess beendet wird. Andernfalls wird eine Fast-Fail-Ausnahme ausgelöst, die durch einen angefügten Debugger abgefangen wird. Wenn der Vorgang zugelassen wird, wird Sie durch einen Aufruf der Windows beendet **TerminateProcess** -Funktion mit einem ausnahmecodestatus **STATUS_INVALID_CRUNTIME_PARAMETER**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Parametervalidierung](../../c-runtime-library/parameter-validation.md)<br/>
