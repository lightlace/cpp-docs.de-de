---
title: Verwenden einer Datensatzansicht (MFC-Datenzugriff) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d37f40169330fe878eee326628bd26bef9ca8d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="using-a-record-view--mfc-data-access"></a>Verwenden einer Datensatzansicht (MFC-Datenzugriff)
In diesem Thema wird erläutert, wie Sie normalerweise den Standardcode für Datensatzansichten anpassen können, den der Assistent für Sie schreibt. In der Regel das Datensatzauswahl mit werden sollen eine [Filter](../data/odbc/recordset-filtering-records-odbc.md) oder [Parameter](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), vielleicht [sortieren](../data/odbc/recordset-sorting-records-odbc.md) Datensätze, die SQL-Anweisung anpassen.  
  
 Mit `CRecordView` ist nahezu identisch mit der Verwendung [CFormView](../mfc/reference/cformview-class.md). Grundsätzlich wird die Datensatzansicht zum Anzeigen und ggf. zum Aktualisieren der Datensätze eines einzelnen Recordsets verwendet. Darüber hinaus möchten Sie möglicherweise weitere Recordsets verwenden, wie in beschrieben [Datensatzansichten: Füllen eines Listenfelds aus einem zweiten Recordset](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)