---
title: Verwenden von manuellen Zugriffsmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c732bcf45f2dfbd4927366670aed6bfbdcfb4721
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679986"
---
# <a name="using-manual-accessors"></a>Verwenden von manuellen Zugriffsmethoden
Es gibt vier Schritte erforderlich, bei der Verarbeitung eines unbekannten Befehls:  
  
-   Ermitteln der Parameter  
  
-   Führen Sie den Befehl  
  
-   Bestimmen Sie die Ausgabespalten  
  
-   Überprüfen Sie, ob mehrere Rowsets zurückgegeben werden  
  
 Verwenden Sie dazu mit der OLE DB-Consumervorlagen der `CManualAccessor` Klasse, und gehen Sie folgendermaßen vor:  
  
1.  Öffnen einer `CCommand` Objekt mit `CManualAccessor` als Vorlagenparameter.  
  
    ```cpp  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Fragen Sie die Sitzung für die `IDBSchemaRowset` -Schnittstelle und verwenden Sie die Prozedur Parameter-Rowset. Wenn die `IDBSchemaRowset` Schnittstelle ist nicht verfügbar ist, Abfragen für die `ICommandWithParameters` Schnittstelle. Rufen Sie `GetParameterInfo` Informationen. Wenn keine der Schnittstellen verfügbar ist, können Sie davon ausgehen, dass keine Parameter vorhanden sind.  
  
3.  Rufen Sie für jeden Parameter `AddParameterEntry` , fügen Sie die Parameter, und legen Sie sie.  
  
4.  Öffnen Sie das Rowset, aber legen den Bindungsparameter auf **"false"**.  
  
5.  Rufen Sie `GetColumnInfo` Ausgabespalten abrufen. Verwendung `AddBindEntry` so die Bindung der Ausgabespalte hinzu.  
  
6.  Rufen Sie `GetNextResult` zu bestimmen, ob weitere Rowsets verfügbar sind. Wiederholen Sie Schritte 2 bis 5.  
  
 Ein Beispiel für einen manuellen Accessor finden Sie unter `CDBListView::CallProcedure` in die [DBVIEWER](https://github.com/Microsoft/VCSamples) Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)