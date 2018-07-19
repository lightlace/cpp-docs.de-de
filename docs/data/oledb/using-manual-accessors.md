---
title: Verwenden von manuellen Accessoren | Microsoft Docs
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
ms.openlocfilehash: ee82a780690c6d5eba7b30debdc592a26ef2cbcc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105903"
---
# <a name="using-manual-accessors"></a>Verwenden von manuellen Zugriffsmethoden
Es gibt vier Dinge bei der Behandlung eines unbekannten Befehls aus:  
  
-   Bestimmen Sie die Parameter  
  
-   Führen Sie den Befehl  
  
-   Bestimmen der Ausgabespalten  
  
-   Feststellen Sie, ob mehrere Rowsets zurückgegeben werden  
  
 Verwenden Sie hierzu mit der OLE DB-Consumervorlagen der `CManualAccessor` Klasse, und gehen Sie folgendermaßen vor:  
  
1.  Öffnen einer `CCommand` -Objekt mit `CManualAccessor` als Vorlagenparameter.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Fragen Sie die Sitzung für die **IDBSchemaRowset** Schnittstelle, und verwenden Sie das Verfahren Parameter-Rowset. Wenn die **IDBSchemaRowset** Schnittstelle ist nicht verfügbar ist, Abfragen für die `ICommandWithParameters` Schnittstelle. Rufen Sie `GetParameterInfo` Informationen. Wenn keine der Schnittstellen verfügbar ist, können Sie davon ausgehen, dass keine Parameter vorhanden sind.  
  
3.  Rufen Sie für jeden Parameter `AddParameterEntry` fügen Sie die Parameter und setzen Sie sie.  
  
4.  Öffnen Sie das Rowset, aber so festgelegt, den Bind-Parameter **"false"**.  
  
5.  Rufen Sie `GetColumnInfo` Ausgabespalten abgerufen. Verwendung `AddBindEntry` so die Bindung die Ausgabespalte hinzu.  
  
6.  Rufen Sie `GetNextResult` zu bestimmen, ob weitere Rowsets verfügbar sind. Wiederholen Sie die Schritte 2 bis 5.  
  
 Ein Beispiel für einen manuellen Accessor finden Sie unter **CDBListView:: CallProcedure** in der [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)