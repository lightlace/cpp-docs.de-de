---
title: _purecall
ms.date: 11/04/2016
api_name:
- _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: 5d62ec30731ce26c4683afc88474d4bddb63a697
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950156"
---
# <a name="_purecall"></a>_purecall

Der standardmäßige rein virtuelle Fehlerhandler für Funktionsaufrufe. Der Compiler generiert Code zum Aufrufen dieser Funktion, wenn eine rein virtuelle Memberfunktion aufgerufen wird.

## <a name="syntax"></a>Syntax

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Hinweise

Die **_purecall** -Funktion ist ein Microsoft-spezifisches Implementierungsdetail des Microsoft C++ -Compilers. Diese Funktion soll nicht direkt von Ihrem Code aufgerufen werden, und sie hat keine öffentliche Header-Deklaration. Es ist hier dokumentiert, da es sich um einen öffentlichen Export der C-Laufzeitbibliothek handelt.

Ein Aufruf an eine rein virtuelle Funktion ist ein Fehler, da sie keine Implementierung hat. Der Compiler generiert Code zum Aufrufen der **_purecall** -Fehlerhandlerfunktion, wenn eine rein virtuelle Funktion aufgerufen wird. Standardmäßig wird das Programm von **_purecall** beendet. Vor dem Beenden Ruft die **_purecall** -Funktion eine **_purecall_handler** -Funktion auf, wenn eine für den Prozess festgelegt wurde. Sie können Ihre eigene Fehlerhandlerfunktion für rein virtuelle Funktionsaufrufe installieren, um sie für das Debuggen und für Berichtszwecke abzufangen. Um einen eigenen Fehlerhandler zu verwenden, erstellen Sie eine Funktion, die über die **_purecall_handler** -Signatur verfügt, und verwenden Sie dann [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) , um Sie als aktuellen Handler festzulegen.

## <a name="requirements"></a>Anforderungen

Die **_purecall** -Funktion hat keine Header Deklaration. **_Purecall_handler** typedef wird in \<STDLIB. h > definiert.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
