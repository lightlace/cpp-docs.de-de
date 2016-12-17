---
title: "Verwenden von manuellen Accessoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Accessoren [C++], Manuelle"
  - "Befehlsbehandlung, OLE DB-Vorlagen"
  - "Manuelle Accessoren"
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von manuellen Accessoren
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei der Behandlung eines unbekannten Befehls sollten vier Schritte ausgeführt werden:  
  
-   Bestimmen der Parameter  
  
-   Ausführen des Befehls  
  
-   Bestimmen der Ausgabespalten  
  
-   Überprüfen, ob mehrere Rowsets zurückgegeben werden  
  
 Wenn Sie hierfür die OLE DB\-Consumervorlagen verwenden möchten, verwenden Sie die `CManualAccessor`\-Klasse, und führen Sie die folgenden Schritte aus:  
  
1.  Öffnen Sie ein `CCommand`\-Objekt mit `CManualAccessor` als Vorlagenparameter.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Fragen Sie die Sitzung nach der **IDBSchemaRowset**\-Schnittstelle ab, und verwenden Sie das Rowset für die Prozeduren\-Parameter.  Wenn die **IDBSchemaRowset**\-Schnittstelle nicht verfügbar ist, starten Sie eine Abfrage nach der `ICommandWithParameters`\-Schnittstelle.  Rufen Sie für Informationen `GetParameterInfo` auf.  Wenn keine der Schnittstellen verfügbar ist, können Sie davon ausgehen, dass keine Parameter vorhanden sind.  
  
3.  Rufen Sie für jeden Parameter `AddParameterEntry` auf, um die Parameter hinzuzufügen und sie festzulegen.  
  
4.  Öffnen Sie das Rowset, legen Sie den Bindungsparameter jedoch auf **false** fest.  
  
5.  Rufen Sie `GetColumnInfo` auf, um die Ausgabespalten abzurufen.  Verwenden Sie `AddBindEntry`, um die Ausgabespalten zum Binden hinzuzufügen.  
  
6.  Rufen Sie `GetNextResult` auf um zu bestimmen, ob weitere Rowsets verfügbar sind.  Wiederholen Sie die Schritte 2 bis 5.  
  
 Ein Beispiel für einen manuellen Accessor finden Sie unter **CDBListView::CallProcedure** im Beispiel [DBVIEWER](assetId:///07620f99-c347-4d09-9ebc-2459e8049832).  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)