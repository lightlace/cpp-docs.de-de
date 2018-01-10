---
title: Funktionen des Datensatzes anzeigen Klassen (MFC-Datenzugriff) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c975aac0459a13a3fb95fdec3dff1a648b0efec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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