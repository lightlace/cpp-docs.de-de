---
title: _CrtSetReportHook
ms.date: 11/04/2016
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
ms.openlocfilehash: 7dcb916ea920751618ffa6a4afbcde8df5e35cba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478337"
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook

Installiert eine clientdefinierte Berichtsfunktion, indem sie mit dem Debug-Berichterstellungsprozess der C-Laufzeit verknüpft wird (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>Parameter

*reportHook*<br/>
Die neue clientdefinierte Berichtsfunktion, die mit dem Debug-Berichterstellungsprozess der C-Laufzeit verknüpft werden soll.

## <a name="return-value"></a>Rückgabewert

Gibt die vorherige clientdefinierte Berichtsfunktion zurück.

## <a name="remarks"></a>Hinweise

**_CrtSetReportHook** ermöglicht einer Anwendung, seiner eigenen Funktion der C-Laufzeit-Bibliothek Berichterstellungsprozess zu verwenden. Folglich wird bei jedem Aufruf von [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) zum Generieren eines Debugberichts die Berichtsfunktion der Anwendung zuerst aufgerufen. Diese Funktionalität ermöglicht einer Anwendung, führen Sie Vorgänge wie das Filtern von debugberichten, damit sie können auf bestimmte Zuordnungstypen konzentrieren oder einen Bericht an nicht verfügbare Ziele senden, mit **_CrtDbgReport**. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetReportHook** werden während der vorverarbeitung entfernt.

Eine robustere Version **_CrtSetReportHook**, finden Sie unter [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md).

Die **_CrtSetReportHook** -Funktion installiert die neue clientdefinierte Berichtsfunktion, die im angegebenen *ReportHook* und gibt Sie die vorherige clientdefinierte Hookfunktion zurück. Das folgende Beispiel zeigt, wie ein Prototyp einer clientdefinierten Hookfunktion für Berichte entwickelt werden soll:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

wo *ReportType* ist der debugberichtstyp (**_CRT_WARN**, **_CRT_ERROR**, oder **_CRT_ASSERT**), *Nachricht* ist die vollständig assemblierte debugbenutzermeldung im Bericht enthalten sein soll und **ReturnValue** ist der Wert von der clientdefinierten Berichtsfunktion, die von zurückgegeben werden sollen **_ CrtDbgReport**. Eine vollständige Beschreibung der verfügbaren Berichtstypen finden Sie in der [_CrtSetReportMode](crtsetreportmode.md)-Funktion.

Wenn die clientdefinierte Berichtsfunktion vollständig über die Debugmeldung behandelt, sodass kein weiterer Bericht erforderlich ist, klicken Sie dann die Funktion sollte zurückgeben **"true"**. Wenn die Funktion gibt **"false"**, **_CrtDbgReport** aufgerufen, um den Debugbericht mithilfe der aktuellen Einstellungen für den Berichtstyp, Modus und -Datei zu generieren. Darüber hinaus durch Angabe der **_CrtDbgReport** -Rückgabewert in **ReturnValue**, die Anwendung kann auch steuern, ob ein Debugabbruch auftritt. Eine vollständige Beschreibung der Konfiguration und generiert der Debugbericht, finden Sie unter **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md), und **_CrtDbgReport**.

Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Debug Hook Function Writing (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Wenn Ihre Anwendung kompiliert wird, mit **"/ CLR"** und die Berichtsfunktion wird aufgerufen, nachdem die Anwendung beendet wurde main, die CLR wird eine Ausnahme ausgelöst, wenn die Berichtsfunktion eine CRT-Funktion aufruft.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
