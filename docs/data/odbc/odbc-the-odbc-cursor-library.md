---
title: 'ODBC: Die ODBC-Cursorbibliothek'
ms.date: 11/04/2016
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
ms.openlocfilehash: 862303a0dc66fbd49bfcba83336ab29dfc7145c0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032231"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: Die ODBC-Cursorbibliothek

In diesem Thema wird beschrieben, die ODBC-Cursorbibliothek und erläutert, wie sie. Weitere Informationen finden Sie unter:

- [Cursor-Bibliothek und auf Ebene 1 ODBC-Treiber](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [Positionierte Updates und Timestamp-Spalten](#_core_positioned_updates_and_timestamp_columns)

- [Verwenden die Cursorbibliothek](#_core_using_the_cursor_library)

Die ODBC-Cursorbibliothek ist eine Dynamic Link Library (DLL), die zwischen der ODBC-Treiber-Manager und der Treiber befindet. In der ODBC-Terminologie verwaltet ein Treiber ein Cursors, zum Nachverfolgen seiner Position im Recordset. Der Cursor markiert die Position in das Recordset, Sie haben bereits ein Bildlauf durchgeführt, den aktuellen Datensatz.

##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> Cursor-Bibliothek und auf Ebene 1 ODBC-Treiber

Die ODBC-Cursorbibliothek-Ebene-1-Treiber bietet die folgenden neuen Funktionen:

- Vorwärts und rückwärts scrollen. Ebene 2-Treiber ist die Cursorbibliothek nicht erforderlich, da sie bereits bildlauffähig sind.

- Unterstützung für Momentaufnahmen. Die Cursorbibliothek verwaltet einen Puffer mit der Momentaufnahme-Datensätzen. Dieser Puffer spiegelt wider, löschungen und Änderungen an der Datensätze, aber nicht die Hinzufügungen, löschungen oder Änderungen anderer Benutzer Ihres Programms. Aus diesem Grund ist die Momentaufnahme nur so aktuell wie die Cursorbibliothek Puffer. Der Puffer ist nicht reflektiert auch eigene Erweiterungen bis zum Aufruf von `Requery`. Dynasets verwenden Sie die Cursorbibliothek nicht.

Die Cursorbibliothek erhalten Sie Momentaufnahmen (statische Cursor), auch wenn sie vom Treiber nicht unterstützt werden. Wenn der Treiber bereits static-Cursor unterstützt, müssen Sie nicht zum Laden der Cursorbibliothek um Unterstützung zu erhalten. Wenn Sie die Cursorbibliothek verwenden, können Sie nur Momentaufnahmen und Forward-only-Recordsets. Wenn der Treiber Dynasets (KEYSET_DRIVEN-Cursor unterstützt), und Sie sie verwenden möchten, müssen Sie die Cursorbibliothek nicht verwenden. Wenn Sie sowohl Momentaufnahmen und Dynasets verwenden möchten, müssen Sie diese auf zwei unterschiedlichen Grundlage `CDatabase` Objekte (zwei verschiedene Verbindungen), es sei denn, der Treiber beide unterstützt.

##  <a name="_core_positioned_updates_and_timestamp_columns"></a> Positionierte Updates und Timestamp-Spalten

> [!NOTE]
>  Auf ODBC-Datenquellen können Sie über die MFC-ODBC-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC-Datenzugriffsobjekt-Klassen (DAO-Klassen).

> [!NOTE]
>  Wenn der ODBC-Treiber unterstützt `SQLSetPos`MFC verwendet, falls verfügbar, in diesem Thema gilt nicht für Sie.

Positionierte Updates unterstützt die meisten auf Ebene 1-Treiber nicht. Solche Treiber abhängig von der Cursorbibliothek, das die Funktionen auf Ebene 2-Treiber in dieser Hinsicht emulieren. Die Cursorbibliothek emuliert positioniertes Update unterstützen, indem Sie ein gesuchtes Update für die unveränderliche Felder.

In einigen Fällen kann ein Recordset eine Timestamp-Spalte als eines dieser unveränderlichen Felder enthalten. In MFC-Recordsets mit Tabellen, die Timestamp-Spalten enthalten zwei Aspekte zu beachten.

Das erste Problem betrifft die aktualisierbare Momentaufnahmen für Tabellen mit Timestamp-Spalten. Wenn die Tabelle, die an die die Momentaufnahme gebunden ist eine Timestamp-Spalte enthält, sollten Sie aufrufen `Requery` nach dem Aufruf von `Edit` und `Update`. Wenn dies nicht der Fall ist, wird Sie möglicherweise nicht in der Lage, erneut denselben Datensatz zu bearbeiten. Beim Aufruf `Edit` und dann `Update`, mit der Datenquelle wird der Datensatz geschrieben, und die Timestamp-Spalte wird aktualisiert. Wenn Sie nicht aufrufen `Requery`, die Timestamp-Wert für den Datensatz in der Momentaufnahme mit dem entsprechenden Zeitstempel für die Datenquelle nicht mehr übereinstimmt. Wenn Sie versuchen, den Datensatz erneut zu aktualisieren, kann die Datenquelle des Updates aufgrund des Konflikts unterbinden.

Das zweite Problem bezieht sich auf die Einschränkungen der Klasse [CTime](../../atl-mfc-shared/reference/ctime-class.md) bei Verwendung mit der `RFX_Date` Funktion, um das Datum und die Daten in oder aus einer Tabelle zu übertragen. Verarbeitung der `CTime` Objekt erzwingt Mehraufwand in Form von sehr fortgeschrittene Verarbeitung während der Datenübertragung. Der Datumsbereich des `CTime` Objekte möglicherweise für einige Anwendungen auch zu beschränken. Eine neue Version der `RFX_Date` -Funktion erfordert einen ODBC *TIMESTAMP_STRUCT* -Parameter anstelle des eine `CTime` Objekt. Weitere Informationen finden Sie unter `RFX_Date` in [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in die *MFC-Referenz*.

##  <a name="_core_using_the_cursor_library"></a> Verwenden die Cursorbibliothek

Wenn Sie mit einer Datenquelle verbinden – durch den Aufruf [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) oder [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) – Sie können angeben, ob die Cursor-Bibliothek für die Datenquelle verwendet. Wenn Sie Momentaufnahmen für diese Datenquelle erstellen, geben Sie die `CDatabase::useCursorLib` option die `dwOptions` Parameter, um `OpenEx` , oder geben Sie "true", für die *bUseCursorLib* Parameter, um `Open` (der Standardwert ist "TRUE"). Wenn der ODBC-Treiber Dynasets unterstützt, und Sie Dynasets für die Datenquelle öffnen möchten, verwenden Sie nicht die Cursor-Bibliothek (es maskiert einige Treiberfunktionen für Dynasets erforderlich). In diesem Fall geben Sie keine `CDatabase::useCursorLib` in `OpenEx` , oder geben Sie "false" für die *bUseCursorLib* Parameter im `Open`.

## <a name="see-also"></a>Siehe auch

[Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)