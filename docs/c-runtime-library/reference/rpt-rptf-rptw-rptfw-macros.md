---
title: _RPT-, _RPTF-, _RPTW- und _RPTFW-Makros
ms.date: 11/04/2016
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
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 567fe0a68f5adad6f5d90ef3da9d673a75bb83a6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949086"
---
# <a name="_rpt-_rptf-_rptw-_rptfw-macros"></a>_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros

Verfolgt den Status einer Anwendung durch Generieren eines Debugberichts (nur in der Debugversion). Beachten Sie, dass *n* die Anzahl der Argumente in *args* angibt und den Wert 0, 1, 2, 3, 4 oder 5 aufweisen kann.

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
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**oder **_CRT_ASSERT**.

*format*<br/>
Formatsteuerelementzeichenfolge, mit der die Benutzermeldung erstellt wird.

*args*<br/>
Die von *Format*verwendeten Ersetzungs Argumente.

## <a name="remarks"></a>Hinweise

Alle diese Makros übernehmen den Report *Type* -Parameter und den *Format* -Parameter. Darüber hinaus können sie auch bis zu vier zusätzliche Argumente annehmen, gekennzeichnet durch die zum Makronamen angefügte Zahl. **_RPT0** und **_RPTF0** nehmen z. b. keine weiteren Argumente an, **_RPT1** und **_RPTF1** nehmen *arg1*, **_RPT2** und **_RPTF2** nehmen *arg1* und **arg2**an, usw.

Die Makros **_RPT** und **_RPTF** ähneln der [printf](printf-printf-l-wprintf-wprintf-l.md) -Funktion, da Sie verwendet werden können, um den Fortschritt einer Anwendung während des Debugvorgangs zu verfolgen. Diese Makros sind jedoch flexibler als **printf** , da Sie nicht in **#ifdef** -Anweisungen eingeschlossen werden müssen, um zu verhindern, dass Sie in einem Einzelhandels Build einer Anwendung aufgerufen werden. Diese Flexibilität wird durch die Verwendung des [_DEBUG](../../c-runtime-library/debug.md) -Makros erreicht. die **_RPT** -und **_RPTF** -Makros sind nur verfügbar, wenn das **_DEBUG** -Flag definiert ist. Wenn **_DEBUG** nicht definiert ist, werden Aufrufe dieser Makros während der Vorverarbeitung entfernt.

Die Makros **_RPTW** und **_RPTFW** sind breit Zeichen Versionen dieser Makros. Sie ähneln **wprintf** und nehmen Zeichen folgen mit breit Zeichen als Argumente.

Die **_RPT** -Makros rufen die [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) -Funktion auf, um einen Debugbericht mit einer Benutzer Meldung zu generieren. Die **_RPTW** -Makros rufen die **_CrtDbgReportW** -Funktion auf, um den gleichen Bericht mit breit Zeichen zu generieren. Die Makros **_RPTF** und **_RPTFW** erstellen einen Debugbericht mit der Quelldatei und der Zeilennummer, in der das Berichts Makro zusätzlich zur Benutzer Meldung aufgerufen wurde. Die Benutzer Meldung wird erstellt, indem die Argument " **arg**[*n*]" durch die gleichen Regeln, die von der [printf](printf-printf-l-wprintf-wprintf-l.md) -Funktion definiert wurden, in der *Format* Zeichenfolge ersetzt werden.

**_CrtDbgReport** oder **_CrtDbgReportW** generiert den Debugbericht und bestimmt seine Ziele basierend auf den aktuellen Berichts Modi und der für Report *Type*definierten Datei. Die Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden verwendet, um das Ziel für jeden Berichtstyp zu definieren.

Wenn ein **_RPT** -Makro aufgerufen wird und weder **_CrtSetReportMode** noch **_CrtSetReportFile** aufgerufen wurde, werden Meldungen wie folgt angezeigt.

|Berichtstyp|Ausgabeziel|
|-----------------|------------------------|
|**_CRT_WARN**|Warnung wird nicht angezeigt.|
|**_CRT_ERROR**|Ein Popupfenster. So als ob `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` angegeben worden wäre.|
|**_CRT_ASSERT**|Identisch mit **_CRT_ERROR**.|

Wenn das Ziel ein debugmeldungsfenster ist und der Benutzer die Schaltfläche **wiederholen** auswählt, gibt **_CrtDbgReport** oder **_CrtDbgReportW** 1 zurück. Dies bewirkt, dass diese Makros den Debugger starten, vorausgesetzt, dass just-in-time (JIT)-Debugging aktiviert ist. Weitere Informationen zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Zwei andere Makros sind vorhanden, die einen Debugbericht generieren. Das [_ASSERT](assert-asserte-assert-expr-macros.md)-Makro generiert einen Bericht, jedoch nur, wenn das Ausdrucksargument zu FALSE ausgewertet wird. [_ASSERTE](assert-asserte-assert-expr-macros.md) entspricht **_ASSERT**, aber schließt den fehlerhaften Ausdruck in den generierten Bericht ein.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-----------|---------------------|
|**_RPT** -Makros|\<crtdbg.h>|
|**_RPTF** -Makros|\<crtdbg.h>|
|**_RPTW** -Makros|\<crtdbg.h>|
|**_RPTFW** -Makros|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

Obwohl sie Makros sind und durch Einschließen von <crtdbg.h> verfügbar gemacht werden, muss die Anwendung mit einer Debugversion der C-Laufzeitbibliothek verlinkt werden, da diese Makros andere Laufzeitfunktionen aufrufen.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie im Thema [_ASSERT](assert-asserte-assert-expr-macros.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
