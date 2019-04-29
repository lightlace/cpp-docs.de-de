---
title: _set_new_mode
ms.date: 11/04/2016
apiname:
- _set_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: 0228170e4ab5b55b4b061fa61a412766de77a063
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356601"
---
# <a name="setnewmode"></a>_set_new_mode

Legt einen neuen handlermodus für **Malloc**.

## <a name="syntax"></a>Syntax

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Parameter

*newhandlermode*<br/>
Neuen handlermodus für **Malloc**; gültiger Wert ist 0 oder 1.

## <a name="return-value"></a>Rückgabewert

Gibt die vorheriger Handler festgelegt für **Malloc**. Ein Rückgabewert 1 gibt an, dass bei einem Fehler bei der speicherbelegung **Malloc** vorher: die neue Handlerroutine; der Rückgabewert 0 gibt an, dass dies nicht der Fall. Wenn die *Newhandlermode* Argument ist nicht gleich 0 oder 1, wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die C++-Funktion **_set_new_mode** legt den neuen Handlermodus für [malloc](malloc.md) fest. Der neue handlermodus gibt an, ob bei einem Fehler **Malloc** besteht darin, rufen Sie die neue Handlerroutine mit [_set_new_handler](set-new-handler.md). In der Standardeinstellung **Malloc** Ruft die neue Handlerroutine nicht bei einem Fehler, um Speicher zu belegen. Sie können dieses Standardverhalten überschreiben, damit, wenn **"malloc"** ein Fehler auftritt, bei der speicherbelegung **"malloc"** die neue Handlerroutine aufruft, in der gleichen Weise wie die **neue** Operator ist Wenn dieser aus demselben Grund fehlschlägt. Weitere Informationen finden Sie unter den Operatoren [new](../../cpp/new-operator-cpp.md) und [delete](../../cpp/delete-operator-cpp.md) in der *C++-Sprachreferenz*. Um den Standardwert zu überschreiben, rufen Sie

```cpp
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit Newmode.obj (siehe [Link Options (Linkoptionen)](../../c-runtime-library/link-options.md)) her.

Diese Funktion überprüft seine Parameter. Wenn *Newhandlermode* wird alles außer 0 oder 1, um die Funktion den Handler für ungültige Parameter, als aufgerufen im beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, <strong>_set_new_mode</strong> -1 zurück und setzt **Errno** zu `EINVAL`.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
