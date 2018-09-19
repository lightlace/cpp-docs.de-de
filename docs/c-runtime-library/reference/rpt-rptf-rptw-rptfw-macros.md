---
title: _RPT-, _RPTF-, _RPTW- und _RPTFW-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69347ab698661346b8d598dda1bb007d071a21f8
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104146"
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros

Verfolgt den Status einer Anwendung durch Generieren eines Debugberichts (nur in der Debugversion). Beachten Sie, dass *n* gibt die Anzahl der Argumente im *Args* und 0, 1, 2, 3, 4 oder 5 sein kann.

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

*reportType*<br/>
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**, oder **_CRT_ASSERT**.

*format*<br/>
Formatsteuerelementzeichenfolge, mit der die Benutzermeldung erstellt wird.

*args*<br/>
Von verwendete optionale ersatzargumente *Format*.

## <a name="remarks"></a>Hinweise

Alle diese Makros nehmen die *ReportType* und *Format* Parameter. Darüber hinaus können sie auch bis zu vier zusätzliche Argumente annehmen, gekennzeichnet durch die zum Makronamen angefügte Zahl. Z. B. **_RPT0** und **_RPTF0** akzeptieren keine zusätzliche Argumente, **_RPT1** und **_RPTF1** dauern *arg1*, **_RPT2** und **_RPTF2** dauern *arg1* und **arg2**und so weiter.

Die **_RPT** und **_RPTF** Makros ähneln den [Printf](printf-printf-l-wprintf-wprintf-l.md) Funktion, da sie während des Debuggens Fortschritt einer Anwendung verwendet werden können. Diese Makros sind jedoch flexibler als **Printf** da sie nicht eingeschlossen werden müssen **#ifdef** Anweisungen, die sie verhindern, die in der Verkaufsversion einer Anwendung aufgerufen. Diese Flexibilität wird erreicht, indem die [_DEBUG](../../c-runtime-library/debug.md) Makro; die **_RPT** und **_RPTF** Makros sind nur verfügbar, wenn die **_DEBUG** Flag ist definiert. Wenn **_DEBUG** ist nicht definiert ist, werden Aufrufe dieser Makros während der vorverarbeitung entfernt.

Die **_RPTW** und **_RPTFW** -Makros sind Breitzeichenversionen dieser Makros. Sie verhalten sich wie **Wprintf** und Breitzeichen-Zeichenfolgen als Argumente.

Die **_RPT** -Makros rufen die [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) Funktion, um einen Debugbericht mit einer benutzermeldung zu generieren. Die **_RPTW** -Makros rufen die **_CrtDbgReportW** Funktion, die den gleichen Berichts mit Breitzeichen zu generieren. Die **_RPTF** und **_RPTFW** -Makros erstellen einen Debugbericht mit der Quelle-Datei und Zeilennummer, in denen das Berichtsmakro, zusätzlich zur benutzermeldung aufgerufen wurde. Die benutzermeldung wird erstellt, indem Sie ersetzen die **Arg**[*n*]-Argumente in der *Format* string "," über die gleichen Regeln die [Printf](printf-printf-l-wprintf-wprintf-l.md)Funktion.

**_CrtDbgReport** oder **_CrtDbgReportW** generiert den Debugbericht und bestimmt seine Ziele basierend auf den aktuellen berichtsmodi und der Datei definiert für *ReportType*. Die Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden verwendet, um die Ziele für jeden Berichtstyp zu definieren.

Wenn ein **_RPT** -Makro aufgerufen wird und weder **_CrtSetReportMode** noch **_CrtSetReportFile** war aufgerufen wird, werden Fehlermeldungen wie folgt angezeigt.

|Berichtstyp|Ausgabeziel|
|-----------------|------------------------|
|**_CRT_WARN**|Warnung wird nicht angezeigt.|
|**_CRT_ERROR**|Ein Popupfenster. So als ob `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` angegeben worden wäre.|
|**_CRT_ASSERT**|Identisch mit **_CRT_ERROR**.|

Wenn das Ziel ein debugmeldungsfenster und der Benutzer wählt die **wiederholen** Schaltfläche **_CrtDbgReport** oder **_CrtDbgReportW** gibt 1 zurück, verursacht diese Makros zum Starten der Debugger, sofern die just-in-Time-Debuggen (JIT) aktiviert ist. Weitere Informationen zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Zwei andere Makros sind vorhanden, die einen Debugbericht generieren. Das [_ASSERT](assert-asserte-assert-expr-macros.md)-Makro generiert einen Bericht, jedoch nur, wenn das Ausdrucksargument zu FALSE ausgewertet wird. [_ASSERTE](assert-asserte-assert-expr-macros.md) ist genau wie **_ASSERT**, jedoch den fehlgeschlagenen Ausdruck im generierten Bericht enthält.

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
