---
title: Funktionen des Datensatzes anzeigen Klassen (MFC-Datenzugriff) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9b6717c0ef1167e01df2f5e8de14408b23a9dbb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Features von Datensatzansichts-Klassen (MFC-Datenzugriff)
Formularbasierte formularbasierte datenzugriffsprogrammierung mit Klasse möglich [CFormView](../mfc/reference/cformview-class.md), aber [CRecordView](../mfc/reference/crecordview-class.md) ist im Allgemeinen eine bessere Klasse ableiten. Zusätzlich zu seiner `CFormView` Funktionen `CRecordView`:  
  
-   Bietet Dialogdatenaustausch (DDX) zwischen den Formularsteuerelementen und dem zugehörigen Recordset-Objekt.  
  
-   Verarbeitet die Befehle "Erste verschieben, Nächste verschieben, vorherige verschieben und letzte verschieben" zum Navigieren durch die Datensätze in dem zugehörigen Recordset-Objekt.  
  
-   Aktualisiert Änderungen in den aktuellen Datensatz, wenn der Benutzer zu einem anderen Datensatz wechselt.  
  
 Weitere Informationen über die Navigation finden Sie unter [Datensatzansichten: Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)