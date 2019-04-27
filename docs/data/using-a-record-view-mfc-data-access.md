---
title: Verwenden einer Datensatzansicht (MFC-Datenzugriff)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
ms.openlocfilehash: 9d64fc26e1c78bad0431bc9b10dd5117c4866159
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152916"
---
# <a name="using-a-record-view--mfc-data-access"></a>Verwenden einer Datensatzansicht (MFC-Datenzugriff)

In diesem Thema wird erläutert, wie Sie normalerweise den Standardcode für Datensatzansichten anpassen können, den der Assistent für Sie schreibt. In der Regel, der Sie die Datensatzauswahl mit einschränken möchten eine [Filter](../data/odbc/recordset-filtering-records-odbc.md) oder [Parameter](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), z. B. [sortieren](../data/odbc/recordset-sorting-records-odbc.md) die Datensätzen, die SQL-Anweisung anpassen.

Mithilfe von `CRecordView` ist ähnlich wie die Verwendung von [CFormView](../mfc/reference/cformview-class.md). Grundsätzlich wird die Datensatzansicht zum Anzeigen und ggf. zum Aktualisieren der Datensätze eines einzelnen Recordsets verwendet. Darüber hinaus möchten Sie möglicherweise weitere Recordsets verwenden, wie in beschrieben [Datensatzansichten: Füllen eines Listenfelds aus einem zweiten Recordset](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).

## <a name="see-also"></a>Siehe auch

[Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)<br/>
[Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)