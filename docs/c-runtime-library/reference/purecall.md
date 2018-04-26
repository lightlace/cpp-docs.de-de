---
title: _purecall | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfcd454aa6a4053ff30eef27b9c9c7d3d8bf7b34
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="purecall"></a>_purecall

Der standardmäßige rein virtuelle Fehlerhandler für Funktionsaufrufe. Der Compiler generiert Code zum Aufrufen dieser Funktion, wenn eine rein virtuelle Memberfunktion aufgerufen wird.

## <a name="syntax"></a>Syntax

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Hinweise

Die **_purecall** Funktion ist eine Microsoft-spezifische Implementierungsdetail des Microsoft Visual C++-Compilers. Diese Funktion soll nicht direkt von Ihrem Code aufgerufen werden, und sie hat keine öffentliche Header-Deklaration. Es ist hier dokumentiert, da es sich um einen öffentlichen Export der C-Laufzeitbibliothek handelt.

Ein Aufruf an eine rein virtuelle Funktion ist ein Fehler, da sie keine Implementierung hat. Der Compiler generiert Code zum Aufrufen der **_purecall** fehlerhandlerfunktion, wenn eine reine virtuelle Funktion aufgerufen wird. Standardmäßig **_purecall** wird das Programm beendet. Vor der Beendigung, die **_purecall** -Funktion aufruft, eine **_purecall_handler** funktioniert, wenn eine für den Prozess festgelegt wurde. Sie können Ihre eigene Fehlerhandlerfunktion für rein virtuelle Funktionsaufrufe installieren, um sie für das Debuggen und für Berichtszwecke abzufangen. Um einen eigenen Fehlerhandler verwenden zu können, erstellen Sie eine Funktion mit der **_purecall_handler** Signatur, verwenden Sie dann [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) auf den aktuellen Handler zu vereinfachen.

## <a name="requirements"></a>Anforderungen

Die **_purecall** Funktion verfügt nicht über eine Kopfzeile-Deklaration. Die **_purecall_handler** Typedef ist definiert \<stdlib.h >.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
