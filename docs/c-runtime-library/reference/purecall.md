---
title: _purecall
ms.date: 11/04/2016
apiname:
- _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: df6dde91ccb952e66eb77c841b2b1ace12756b8c
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446630"
---
# <a name="purecall"></a>_purecall

Der standardmäßige rein virtuelle Fehlerhandler für Funktionsaufrufe. Der Compiler generiert Code zum Aufrufen dieser Funktion, wenn eine rein virtuelle Memberfunktion aufgerufen wird.

## <a name="syntax"></a>Syntax

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Hinweise

Die **_purecall** Funktion ist ein Microsoft-spezifisches Implementierungsdetail des Microsoft C++ Compiler. Diese Funktion soll nicht direkt von Ihrem Code aufgerufen werden, und sie hat keine öffentliche Header-Deklaration. Es ist hier dokumentiert, da es sich um einen öffentlichen Export der C-Laufzeitbibliothek handelt.

Ein Aufruf an eine rein virtuelle Funktion ist ein Fehler, da sie keine Implementierung hat. Der Compiler generiert Code zum Aufrufen der **_purecall** fehlerhandlerfunktion, wenn eine reine virtuelle Funktion aufgerufen wird. In der Standardeinstellung **_purecall** das Programm beendet. Vor dem Beenden der **_purecall** -Funktion aufruft, ein **_purecall_handler** ausgeführt werden, wenn eine für den Prozess festgelegt wurde. Sie können Ihre eigene Fehlerhandlerfunktion für rein virtuelle Funktionsaufrufe installieren, um sie für das Debuggen und für Berichtszwecke abzufangen. Um Ihren eigenen Fehlerhandler zu verwenden, erstellen Sie eine Funktion mit der **_purecall_handler** Signatur verwenden [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) , es sich um den aktuellen Handler festzulegen.

## <a name="requirements"></a>Anforderungen

Die **_purecall** Funktion verfügt nicht über eine Header-Deklaration. Die **_purecall_handler** -Typedefinition ist in \<stdlib.h >.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
