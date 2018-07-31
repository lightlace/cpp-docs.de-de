---
title: Änderungen, die Sie möglicherweise, um den Standardcode (MFC-Datenzugriff vornehmen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 29b5373bd9fb638e7ee4d20cba0c64b9354be70f
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339197"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Mögliche Änderungen am Standardcode (MFC-Datenzugriff)
Die [MFS-Anwendungsassistenten](../mfc/reference/database-support-mfc-application-wizard.md) schreibt eine Recordset-Klasse, der alle Datensätze in einer einzelnen Tabelle auswählt. Dieses Verhalten können Sie häufig auf eine oder mehrere der folgenden Arten ändern:  
  
-   Legen Sie einen Filter oder eine Sortierreihenfolge für das Recordset fest. Führen Sie dies in `OnInitialUpdate` nach des Recordset-Objekts, jedoch bevor erstellt seine `Open` Memberfunktion aufgerufen wird. Weitere Informationen finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) und [Recordset: Sortieren von Datensätzen (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Parametrisieren Sie das Recordset. Geben Sie den tatsächlichen Laufzeit-Parameterwert nach dem Filter an. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Übergeben Sie eine benutzerdefinierte SQL-Zeichenfolge, die [öffnen](../mfc/reference/crecordset-class.md#open) Member-Funktion. Eine Erläuterung, was Sie mit diesem Verfahren erreichen können, finden Sie unter [SQL: Anpassen eines Recordsets SQL-Anweisung (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)