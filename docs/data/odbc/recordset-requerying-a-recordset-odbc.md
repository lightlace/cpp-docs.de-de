---
title: 'Recordset: Erneutes Abfragen eines Recordsets (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d228fb97cad2fba426aa6415564d3b7f60363b5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062679"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>Recordset: Erneutes Abfragen eines Recordsets (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

In diesem Thema wird erläutert, wie Sie einem Recordset-Objekt erneut Abfragen (d. h. aktualisieren) selbst aus der Datenbank, und wenn Sie möchten möglicherweise, dass Sie mit der [Requery](../../mfc/reference/crecordset-class.md#requery) Member-Funktion.

Die Hauptgründe für erneutes Abfragen eines Recordsets sind:

- Schalten Sie das Recordset, das auf dem neuesten Stand in Bezug auf Datensätze, die von Ihnen oder durch andere Benutzer hinzugefügt und Datensätze, die von anderen Benutzern (diejenigen, die Sie löschen, werden bereits in das Recordset übernommen) gelöscht.

- Aktualisieren Sie das Recordset basierend auf die Parameterwerte ändern.

##  <a name="_core_bringing_the_recordset_up_to_date"></a> Aktualisieren des Recordsets bis Datum

In vielen Fällen möchten Sie das Recordset-Objekt, um es anzuzeigen requery auf dem neuesten Stand. In einer Mehrbenutzer-Datenbank-Umgebung können andere Benutzer die Daten während der Lebensdauer eines Recordsets ändern. Weitere Informationen zu wann das Recordset von anderen Benutzern vorgenommene Änderungen widerspiegelt, und wenn Recordsets anderer Benutzer die Änderung zu reflektieren, finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) und [Dynaset](../../data/odbc/dynaset.md).

##  <a name="_core_requerying_based_on_new_parameters"></a> Erneutes Abfragen basierend auf neuen Parametern

Eine andere häufige – und ebenso wichtig – Verwendung von [Requery](../../mfc/reference/crecordset-class.md#requery) besteht darin, wählen Sie einen neuen Satz von Datensätzen auf Grundlage der Parameterwerte ändern.

> [!TIP]
>  Die Geschwindigkeit der Abfrage wird wahrscheinlich erheblich schneller, wenn Sie aufrufen `Requery` mit geänderten Parameterwerten aufrufen, als `Open` erneut aus.

##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> Erneutes Abfragen Dynasets Visual Studio. Momentaufnahmen

Da Dynasets vorgesehen sind, um eine Gruppe von Datensätzen mit dynamischen, auf dem neuesten Stand Daten darzustellen, sollten Sie Dynasets requery häufig, wenn Sie entsprechend anderer Benutzer hinzufügen möchten. Momentaufnahmen sind auf der anderen Seite nützlich, da Sie sicher auf ihre statischen Inhalte verlassen können, während Sie Berichte, Berechnen von Gesamtergebnissen und so weiter. Dennoch können Sie manchmal sowie eine Momentaufnahme erneut abfragen möchten. In einer mehrbenutzerumgebung verlieren momentaufnahmedaten Synchronisierung mit der Datenquelle, wie andere Benutzer die Datenbank zu ändern.

#### <a name="to-requery-a-recordset-object"></a>Um einem Recordset-Objekt erneut abzufragen.

1. Rufen Sie die [Requery](../../mfc/reference/crecordset-class.md#requery) -Memberfunktion des Objekts.

Alternativ können Sie schließen und öffnen das ursprüngliche Recordset. In beiden Fällen stellt das neue Recordset den aktuellen Zustand der Datenquelle dar.

Ein Beispiel finden Sie unter [Datensatzansichten: Füllen eines Listenfelds aus einem zweiten Recordset](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).

> [!TIP]
>  Zur Optimierung `Requery` Leistung zu vermeiden, Ändern des Recordsets [Filter](../../data/odbc/recordset-filtering-records-odbc.md) oder [Sortierreihenfolge](../../data/odbc/recordset-sorting-records-odbc.md). Ändern Sie nur den Parameterwert vor dem Aufruf `Requery`.

Wenn die `Requery` rufen ein Fehler auftritt, können Sie den Aufruf wiederholen, Ihre Anwendung sollte, andernfalls ordnungsgemäß beenden. Ein Aufruf von `Requery` oder `Open` für eine beliebige Anzahl von Gründen fehlschlagen. Möglicherweise tritt auf, ein Netzwerkfehler aufgetreten; Alternativ dazu können Sie während des Aufrufs, nach der Veröffentlichung der vorhandenen Daten, aber bevor die neuen Daten abgerufen werden, ein anderer Benutzer möglicherweise erhalten Sie exklusiven Zugriff. oder in der Tabelle, von der das Recordset abhängig ist, kann gelöscht werden.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)