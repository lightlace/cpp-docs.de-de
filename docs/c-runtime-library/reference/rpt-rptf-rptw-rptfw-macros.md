---
title: _RPT-, _RPTF-, _RPTW- und _RPTFW-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1692789ff2dac85e6ca33aa6b05ced6a01f30cba
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros

Verfolgt den Status einer Anwendung durch Generieren eines Debugberichts (nur in der Debugversion). Beachten Sie, dass *n* gibt die Anzahl von Argumenten in *Args* und 0, 1, 2, 3, 4 oder 5 sein können.

## <a name="syntax"></a>Syntax

```C
_RPT
      n
      (
   reportType,
   format,
...[args]
);
_RPTFn(
   reportType,
   format,
   [args]
);
_RPTWn(
   reportType,
   format
   [args]
);
_RPTFWn(
   reportType,
   format
   [args]
);
```

### <a name="parameters"></a>Parameter

*Definition* Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**, oder **_CRT_ASSERT**.

*Format* formatsteuerzeichenfolge verwendet, um die Meldung für den Benutzer zu erstellen.

*Args* ersatzargumente verwendeten *Format*.

## <a name="remarks"></a>Hinweise

Nehmen Sie alle diese Makros den *Definition* und *Format* Parameter. Darüber hinaus können sie auch bis zu vier zusätzliche Argumente annehmen, gekennzeichnet durch die zum Makronamen angefügte Zahl. Beispielsweise **_RPT0** und **_RPTF0** akzeptieren keine zusätzliche Argumente **_RPT1** und **_RPTF1** dauern *arg1*, **_RPT2** und **_RPTF2** dauern *arg1* und **arg2**und so weiter.

Die **_RPT** und **_RPTF** Makros ähneln den [Printf](printf-printf-l-wprintf-wprintf-l.md) funktionieren, da sie während des Debugprozesses Fortschritt einer Anwendung verwendet werden können. Diese Makros sind jedoch flexibler als **Printf** , da sie nicht in eingeschlossen werden müssen **#ifdef** Anweisungen nicht zu verhindern, dass in einer Verkaufsversion einer Anwendung aufgerufen. Diese Flexibilität wird erreicht, indem die [_DEBUG](../../c-runtime-library/debug.md) Makro; das **_RPT** und **_RPTF** Makros sind nur verfügbar, wenn die **_DEBUG** Flag ist definiert. Wenn **_DEBUG** ist nicht definiert ist, werden Aufrufe dieser Makros während der vorverarbeitung entfernt.

Die **_RPTW** und **_RPTFW** Makros sind Breitzeichenversionen dieser Makros. Sie entsprechen **"wprintf"** und Breitzeichen-Zeichenfolgen als Argumente nehmen.

Die **_RPT** Makros Aufruf der [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) Funktion generiert einen Debugbericht mit einer Meldung für den Benutzer. Die **_RPTW** Makros Aufruf der **_CrtDbgReportW** Funktion zum Generieren von des gleichen Berichts mit Breitzeichen. Die **_RPTF** und **_RPTFW** Makros einen Debugbericht mit der Quelle und die Zeilennummer Anzahl, in das Berichtsmakro, außerdem auf die Meldung für den Benutzer aufgerufen wurde, erstellen. Die Meldung für den Benutzer wird erstellt, durch das Ersetzen der **Arg**[*n*] Argumente in der *Format* "string", mit den gleichen Regeln definiert werden, indem die [Printf](printf-printf-l-wprintf-wprintf-l.md)Funktion.

**_CrtDbgReport** oder **_CrtDbgReportW** generiert den Debugbericht und bestimmt seine Ziele basierend auf den aktuellen berichtsmodi und der Datei für definiert *Definition*. Die Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden verwendet, um die Ziele für jeden Berichtstyp zu definieren.

Wenn ein **_RPT** Makro wird aufgerufen, und weder **_CrtSetReportMode** noch **_CrtSetReportFile** wurde aufgerufen wird, werden Fehlermeldungen wie folgt angezeigt.

|Berichtstyp|Ausgabeziel|
|-----------------|------------------------|
|**_CRT_WARN**|Warnung wird nicht angezeigt.|
|**_CRT_ERROR**|Ein Popupfenster. So als ob `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` angegeben worden wäre.|
|**_CRT_ASSERT**|Identisch mit **_CRT_ERROR**.|

Wenn das Ziel ein debugmeldungsfenster und der Benutzer wählt die **wiederholen** Schaltfläche, **_CrtDbgReport** oder **_CrtDbgReportW** gibt 1 zurück, verursacht diese Makros starten der Debugger, sofern die Just-in-Time (JIT)-Debuggen aktiviert ist. Weitere Informationen zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Zwei andere Makros sind vorhanden, die einen Debugbericht generieren. Das [_ASSERT](assert-asserte-assert-expr-macros.md)-Makro generiert einen Bericht, jedoch nur, wenn das Ausdrucksargument zu FALSE ausgewertet wird. [_ASSERTE](assert-asserte-assert-expr-macros.md) wird genau wie **_ASSERT**, jedoch den fehlgeschlagenen Ausdruck in der generierte Bericht enthält.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-----------|---------------------|
|**_RPT** Makros|\<crtdbg.h>|
|**_RPTF** Makros|\<crtdbg.h>|
|**_RPTW** Makros|\<crtdbg.h>|
|**_RPTFW** Makros|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

Obwohl sie Makros sind und durch Einschließen von <crtdbg.h> verfügbar gemacht werden, muss die Anwendung mit einer Debugversion der C-Laufzeitbibliothek verlinkt werden, da diese Makros andere Laufzeitfunktionen aufrufen.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie im Thema [_ASSERT](assert-asserte-assert-expr-macros.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
