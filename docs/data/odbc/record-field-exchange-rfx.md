---
title: Datensatzfeldaustausch (RFX)
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
ms.openlocfilehash: f612f4be726707681ffbddff88ccc6b8a672e427
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522407"
---
# <a name="record-field-exchange-rfx"></a>Datensatzfeldaustausch (RFX)

Die MFC-ODBC-Datenbankklassen automatisiert das Verschieben von Daten zwischen der Datenquelle und ein [Recordset](../../data/odbc/recordset-odbc.md) Objekt. Beim Ableiten einer Klasse von [CRecordset](../../mfc/reference/crecordset-class.md) und Abrufens von Zeilen nicht verwenden, werden Daten mit den Datensatzfeldaustausch (RFX)-Mechanismus übertragen.

> [!NOTE]
>  Wenn Sie implementiert haben, in einer abgeleiteten gesammelte `CRecordset` -Klasse, das Framework verwendet den Bulk Datensatzfeldaustausch (Bulk-RFX)-Mechanismus zum Übertragen von Daten. Weitere Informationen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX ähnelt Dialogdatenaustausch (DDX). Verschieben von Daten zwischen einer Datenquelle und den Felddatenmembern eines Recordset-Objekts erfordert mehrere Aufrufe des Recordsets [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) und beträchtliche Interaktion zwischen dem Framework und [ODBC](../../data/odbc/odbc-basics.md). Der RFX-Mechanismus ist typsicher und erspart Ihnen das Aufrufen von ODBC-Funktionen wie z. B. `::SQLBindCol`. Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

RFX ist größtenteils transparent. Wenn Sie mit der MFC-Anwendungs-Assistenten die Recordset-Klassen deklarieren oder **Klasse hinzufügen** (siehe [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)), RFX ist automatisch in diese integriert. Recordset-Klasse von der Basisklasse abgeleitet werden `CRecordset` vom Framework bereitgestellt. MFC-Anwendung-Assistenten können Sie eine anfängliche Recordsetklasse zu erstellen. **Fügen Sie Klasse** können Sie weitere Recordset-Klassen hinzufügen, wenn Sie sie benötigen. Weitere Informationen und Beispiele finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Wenn Sie möchten, müssen Sie manuell eine kleine Menge von RFX-Code in drei Fällen hinzufügen:

- Verwenden Sie parametrisierte Abfragen. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

- Führen Sie Joins (mit einem Recordset für die Spalten aus zwei oder mehr Tabellen aus). Weitere Informationen finden Sie unter [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

- Binden Sie Datenspalten der dynamisch. Dies ist weniger gebräuchlich als Parametrisierung. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

Wenn Sie ein besseres Verständnis von RFX benötigen, finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

Die folgenden Themen erläutern die Details der Verwendung des Recordset-Objekte:

- [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md)

- [Datensatzfeldaustausch: Verwenden der RFX-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>Siehe auch

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC-ODBC-nutzen](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Datenbankunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)