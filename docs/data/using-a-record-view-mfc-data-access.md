---
title: "Verwenden einer Datensatzansicht (MFC-Datenzugriff) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datensatzansichten, Anpassen des Standardcodes"
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden einer Datensatzansicht (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie Sie normalerweise den Standardcode für Datensatzansichten anpassen können, den der Assistent für Sie schreibt.  Normalerweise möchten Sie die Datensatzauswahl mit einem [Filter](../data/odbc/recordset-filtering-records-odbc.md) oder mit [Parametern](../data/odbc/recordset-parameterizing-a-recordset-odbc.md) einschränken oder die Datensätze [sortieren](../data/odbc/recordset-sorting-records-odbc.md) und die SQL\-Anweisung anpassen.  
  
 Diese Informationen gelten sowohl für [CRecordView](../mfc/reference/crecordview-class.md) \(ODBC\) als auch [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) \(DAO\).  
  
 Die Verwendung von `CRecordView` bzw. `CDaoRecordView` ähnelt der Verwendung von [CFormView](../mfc/reference/cformview-class.md).  Grundsätzlich wird die Datensatzansicht zum Anzeigen und ggf. zum Aktualisieren der Datensätze eines einzelnen Recordsets verwendet.  Darüber hinaus können Sie weitere Recordsets verwenden, wie unter [Datensatzansichten: Füllen eines Listenfelds aus einem zweiten Recordset](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md) beschrieben.  
  
## Siehe auch  
 [Datensatzansichten \(MFC\-Datenzugriff\)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)