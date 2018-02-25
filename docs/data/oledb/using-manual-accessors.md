---
title: Verwenden von manuellen Accessoren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e7d6bd8f0228103e4899e6bc24f6d67af0f3fdb4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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