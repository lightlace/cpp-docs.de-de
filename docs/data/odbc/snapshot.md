---
title: Momentaufnahme
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
ms.openlocfilehash: 99e1d76f8d65def326b0514f3219cef43f695220
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512672"
---
# <a name="snapshot"></a>Momentaufnahme

Eine Momentaufnahme ist ein Recordset, eine statische Ansicht der Daten enthält, wie sie zu dem Zeitpunkt vorhanden waren, die die Momentaufnahme erstellt wurde. Beim Öffnen der Momentaufnahme und verschieben alle Datensätze, die Gruppe von Datensätzen, die sie enthält, und ändern Sie deren Werte nicht, bis Sie durch Aufrufen die Momentaufnahme wiederherstellen `Requery`.

> [!NOTE]
>  Dieses Thema bezieht sich auf die MFC-ODBC-Klassen. Wenn Sie die MFC-DAO-Klassen anstelle von MFC-ODBC-Klassen verwenden, finden Sie unter [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open) eine Beschreibung der Recordsets vom Typ Snapshot.

Sie können Momentaufnahmen aktualisierbar oder schreibgeschützt sind, mit den Datenbankklassen erstellen. Im Gegensatz zu einem Dynaset aktualisierbarer Snapshot spiegelt keine Änderungen zum Aufzeichnen von Werten, die von anderen Benutzern vorgenommene wider, aber es spiegelt wider, Aktualisierungen und Löschvorgänge, die Ihre Anwendung erstellt hat. Hinzugefügte Datensätze zu einer Momentaufnahme werden werden nicht sichtbar, in die Momentaufnahme bis zum Aufruf von `Requery`.

> [!TIP]
>  Eine Momentaufnahme handelt es sich um eine statische ODBC-Cursor. Statische Cursor erhalte nicht tatsächlich eine Zeile mit Daten, bis Sie zu diesem Datensatz wechseln. Um sicherzustellen, dass sofort alle Datensätze abgerufen werden, können Sie einen Bildlauf zum Ende des Recordset und scrollen Sie zu den ersten Datensatz aus, die, den Sie anzeigen möchten. Beachten Sie jedoch, einen Bildlauf bis zum Ende ist der Mehraufwand verbunden und Leistung beeinträchtigt werden kann.

Momentaufnahmen sind besonders hilfreich, wenn Sie die Daten, die fixiert bleiben, während Ihre-Vorgängen, als wenn Sie einen Bericht oder Berechnungen benötigen. Trotzdem kann die Datenquelle erheblich von der Momentaufnahme, voneinander abweichen, sollten Sie möglicherweise von Zeit zu Zeit neu erstellt.

Unterstützung von basiert auf der ODBC-Cursorbibliothek, der statische Cursor und positionierte Updates (erforderlich für aktualisierbarkeit) für alle-Ebene-1-Treiber. Die Cursorbibliothek DLL muss für diese Unterstützung im Arbeitsspeicher geladen werden. Beim Erstellen einer `CDatabase` Objekt, und rufen die `OpenEx` Member-Funktion, die Sie angeben müssen die `CDatabase::useCursorLib` Möglichkeit, die *DwOptions* Parameter. Wenn Sie beim Aufrufen der `Open` Member-Funktion, die Cursorbibliothek standardmäßig geladen wird. Wenn Sie anstelle von Momentaufnahmen Dynasets verwenden, möchten Sie nicht dazu führen, dass die Cursorbibliothek geladen werden.

Momentaufnahmen sind nur verfügbar, wenn die ODBC-Cursorbibliothek geladen war die `CDatabase` Objekt erstellt wurde, oder der ODBC-Treiber, die Sie verwenden die statische Cursor unterstützt.

> [!NOTE]
>  Für einige ODBC-Treiber können Momentaufnahmen (statische Cursor) nicht aktualisiert werden. Überprüfen Sie die Dokumentation des Treibers für die unterstützten Cursortypen und die parallelitätstypen, die sie unterstützen. Um aktualisierbaren Momentaufnahmen zu gewährleisten, stellen Sie sicher, dass Sie die Cursorbibliothek in den Arbeitsspeicher geladen, bei der Erstellung einer `CDatabase` Objekt. Weitere Informationen finden Sie unter [ODBC: die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!NOTE]
>  Wenn Sie sowohl Momentaufnahmen und Dynasets verwenden möchten, müssen Sie diese auf zwei unterschiedlichen Grundlage `CDatabase` Objekte (zwei verschiedene Verbindungen).

Weitere Informationen über gemeinsame Eigenschaften von Snapshots und Recordsets finden Sie unter [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md). Weitere Informationen zu ODBC und Momentaufnahmen, einschließlich der ODBC-Cursorbibliothek, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md).

## <a name="see-also"></a>Siehe auch

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)