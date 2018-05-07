---
title: Momentaufnahme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 309c81e8d370b61ba3a44d9253cda4fa9b84b6cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="snapshot"></a>Momentaufnahme
Eine Momentaufnahme ist ein Recordset, eine statische Ansicht der Daten enthält, wie sie zu dem Zeitpunkt vorhanden waren, die die Momentaufnahme erstellt wurde. Beim Öffnen der Momentaufnahme und verschieben Sie alle Datensätze, der Satz von Datensätzen, die es enthält, und ändern Sie deren Werte nicht, bis Sie die Momentaufnahme durch Aufrufen von neu erstellen **Requery**.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf die MFC-ODBC-Klassen. Wenn Sie statt der MFC-ODBC-Klassen der MFC-DAO-Klassen verwenden, finden Sie unter [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open) für eine Beschreibung des Recordsets Snapshot-Typ.  
  
 Sie können Momentaufnahmen aktualisierbar oder schreibgeschützt sind, mit den Datenbankklassen erstellen. Im Gegensatz zu einem Dynaset aktualisierbarer Snapshot spiegelt keine Änderungen zum Aufzeichnen von anderen Benutzern vorgenommene Werte wider, jedoch reflektiert, Update- und Löschvorgänge, die von Ihrer Anwendung vorgenommen werden. Hinzugefügte Datensätze zu einer Momentaufnahme werden nicht für die Momentaufnahme sichtbar erst nach dem Aufruf **Requery**.  
  
> [!TIP]
>  Eine Momentaufnahme handelt es sich um eine statische ODBC-Cursor. Statische Cursor werden erhalte nicht tatsächlich eine Zeile mit Daten, bis Sie an diesen Datensatz einen Bildlauf durchführen. Um sicherzustellen, dass alle Datensätze sofort abgerufen werden, können Sie einen Bildlauf zum Ende des Recordsets und führen Sie einen Bildlauf zu dem ersten Datensatz, der angezeigt werden soll. Beachten Sie jedoch, dass einen Bildlauf zum Ende herabgesetzt und Leistung beeinträchtigt werden kann.  
  
 Momentaufnahmen sind besonders hilfreich bei der die Daten bleiben während der Vorgänge, wie beim Generieren eines Berichts oder Berechnungen durchgeführt werden. In jedem Fall kann die Datenquelle erheblich aus der Momentaufnahme voneinander abweichen, damit Sie ihn von Zeit zu Zeit neu erstellen möchten.  
  
 Unterstützung von Momentaufnahmen basiert auf der ODBC-Cursorbibliothek der statische Cursor und positionierte Updates (erforderlich für Updateability) für eine beliebige Ebene-1-Treiber. Die Cursorbibliothek DLL muss für diese Unterstützung im Arbeitsspeicher geladen werden. Bei der Erstellung einer `CDatabase` Objekt, und rufen die `OpenEx` Memberfunktion ist, müssen Sie angeben der **dwOptions** -Option von der `dwOptions` Parameter. Beim Aufrufen der **öffnen** Memberfunktion, die Cursorbibliothek standardmäßig geladen wird. Wenn Sie anstelle von Momentaufnahmen Dynasets verwenden, möchten Sie nicht dazu führen, dass die Cursorbibliothek geladen werden soll.  
  
 Momentaufnahmen sind nur verfügbar, wenn die ODBC-Cursorbibliothek geladen war die `CDatabase` Objekt erstellt wurde, oder der ODBC-Treiber, die Sie verwenden die statische Cursor unterstützt.  
  
> [!NOTE]
>  Für einige ODBC-Treiber möglicherweise Momentaufnahmen (statische Cursor) nicht aktualisierbar. Überprüfen Sie die Dokumentation des Treibers für Cursortypen unterstützt und die parallelitätstypen, die sie unterstützen. Um mit aktualisierbaren Momentaufnahmen zu garantieren, sicherstellen, dass die Cursorbibliothek in den Arbeitsspeicher zu laden, bei der Erstellung einer `CDatabase` Objekt. Weitere Informationen finden Sie unter [ODBC: die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Wenn Sie Momentaufnahmen und Dynasets verwenden möchten, müssen Sie diese auf zwei unterschiedlichen Grundlage `CDatabase` Objekte (zwei unterschiedliche Verbindungen).  
  
 Weitere Informationen über gemeinsame Eigenschaften von Snapshots und Recordsets finden Sie unter [Recordset (ODBC)](../../data/odbc/recordset-odbc.md). Weitere Informationen zu ODBC und Momentaufnahmen, einschließlich der ODBC-Cursorbibliothek finden Sie unter [ODBC](../../data/odbc/odbc-basics.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)