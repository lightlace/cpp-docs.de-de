---
title: _CrtSetReportHook
ms.date: 11/04/2016
api_name:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
ms.openlocfilehash: 77c1e499c66a76027e872783e256754ef72e465d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938510"
---
# <a name="_crtsetreporthook"></a>_CrtSetReportHook

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

**_CrtSetReportHook** ermöglicht es einer Anwendung, eine eigene Berichtsfunktion im Debugbibliothek-Bericht Erstellungs Prozess der C-Laufzeit zu verwenden. Folglich wird bei jedem Aufruf von [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) zum Generieren eines Debugberichts die Berichtsfunktion der Anwendung zuerst aufgerufen. Diese Funktion ermöglicht es einer Anwendung, Vorgänge wie das Filtern von debugberichten auszuführen, sodass Sie sich auf bestimmte Zuordnungs Typen konzentrieren oder einen Bericht an Ziele senden kann, die mit **_CrtDbgReport**nicht verfügbar sind. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetReportHook** während der Vorverarbeitung entfernt.

Eine stabilere Version von **_CrtSetReportHook**finden Sie unter [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md).

Die **_CrtSetReportHook** -Funktion installiert die neue Client definierte Berichtsfunktion, die in *reportHook* angegeben ist, und gibt den vorherigen Client definierten Hook zurück. Das folgende Beispiel zeigt, wie ein Prototyp einer clientdefinierten Hookfunktion für Berichte entwickelt werden soll:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Wenn *reportType* der debugberichtstyp ( **_CRT_WARN**, **_CRT_ERROR**oder **_CRT_ASSERT**) ist, ist *Message* die vollständig assemblierte debugbenutzernachricht, die im Bericht enthalten sein soll, und **ReturnValue** ist der Wert. wird von der Client definierten Berichtsfunktion angegeben, die von **_CrtDbgReport**zurückgegeben werden soll. Eine vollständige Beschreibung der verfügbaren Berichtstypen finden Sie in der [_CrtSetReportMode](crtsetreportmode.md)-Funktion.

Wenn die Client definierte Berichtsfunktion die Debugmeldung vollständig verarbeitet, sodass keine weitere Berichterstellung erforderlich ist, sollte die Funktion **true**zurückgeben. Wenn die Funktion " **false**" zurückgibt, wird " **_CrtDbgReport** " aufgerufen, um den Debugbericht mithilfe der aktuellen Einstellungen für den Berichtstyp, den Modus und die Datei zu generieren. Außerdem kann die Anwendung durch Angeben des **_CrtDbgReport** -Rückgabewerts in **ReturnValue**auch steuern, ob eine debugpause auftritt. Eine umfassende Beschreibung der Konfiguration und Generierung des debugberichts finden Sie unter **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md)und **_CrtDbgReport**.

Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Debug Hook Function Writing (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Wenn die Anwendung mit **/CLR** kompiliert wird und die Berichterstattungs Funktion aufgerufen wird, nachdem die Anwendung beendet wurde, löst die CLR eine Ausnahme aus, wenn die Berichterstattungs Funktion eine CRT-Funktion aufruft.

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
