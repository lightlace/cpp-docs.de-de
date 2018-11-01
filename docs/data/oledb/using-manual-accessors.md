---
title: Verwenden von manuellen Zugriffsmethoden
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: 8b969b7bb939d8e7d2217234795b564e8d137208
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651762"
---
# <a name="using-manual-accessors"></a>Verwenden von manuellen Zugriffsmethoden

Es gibt vier Schritte erforderlich, bei der Verarbeitung eines unbekannten Befehls:

- Ermitteln der Parameter

- Führen Sie den Befehl

- Bestimmen Sie die Ausgabespalten

- Überprüfen Sie, ob mehrere Rowsets zurückgegeben werden

Dies ist mit dem OLE DB-Consumervorlagen verwenden Sie die `CManualAccessor` Klasse, und gehen Sie folgendermaßen vor:

1. Öffnen einer `CCommand` Objekt mit `CManualAccessor` als Vorlagenparameter.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. Fragen Sie die Sitzung für die `IDBSchemaRowset` -Schnittstelle und verwenden Sie die Prozedur Parameter-Rowset. Wenn die `IDBSchemaRowset` Schnittstelle nicht verfügbar ist, Abfragen für die `ICommandWithParameters` Schnittstelle. Rufen Sie `GetParameterInfo` Informationen. Wenn keine der Schnittstellen verfügbar ist, können Sie davon ausgehen, dass keine Parameter vorhanden sind.

1. Rufen Sie für jeden Parameter `AddParameterEntry` , fügen Sie die Parameter, und legen Sie sie.

1. Öffnen Sie das Rowset, aber legen den Bindungsparameter auf **"false"**.

1. Rufen Sie `GetColumnInfo` Ausgabespalten abrufen. Verwendung `AddBindEntry` so die Bindung der Ausgabespalte hinzu.

1. Rufen Sie `GetNextResult` zu bestimmen, ob weitere Rowsets verfügbar sind. Wiederholen Sie Schritte 2 bis 5.

Ein Beispiel für einen manuellen Accessor finden Sie unter `CDBListView::CallProcedure` in die [DBVIEWER](https://github.com/Microsoft/VCSamples) Beispiel.

## <a name="see-also"></a>Siehe auch

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)