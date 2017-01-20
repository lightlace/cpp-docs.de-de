---
title: "Features von Datensatzansichts-Klassen (MFC-Datenzugriff)"
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
  - "Datensatzansichtsklassen"
  - "Datensatzansichten, Klassen"
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Features von Datensatzansichts-Klassen (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit der [CFormView](../mfc/reference/cformview-class.md)\-Klasse können Sie eine formularbasierte Datenzugriffsprogrammierung ausführen, die Klassen [CRecordView](../mfc/reference/crecordview-class.md) und [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) sind in der Regel jedoch besser für die Ableitung geeignet.  Neben ihren `CFormView`\-Funktionen bieten `CRecordView` und `CDaoRecordView` Folgendes:  
  
-   Dialogdatenaustausch \(DDX\) zwischen den Formularsteuerelementen und dem zugehörigen Recordset\-Objekt.  
  
-   Die Befehle "Erste verschieben", "Nächste verschieben", "Vorherige verschieben" und "Letzte verschieben" verarbeiten, um durch die Datensätze in dem zugehörigen Recordset\-Objekt zu navigieren.  
  
-   Änderungen am aktuellen Datensatz aktualisieren, wenn der Benutzer zu einem anderen Datensatz wechselt.  
  
 Weitere Informationen über die Navigation finden Sie unter [Datensatzansichten: Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## Siehe auch  
 [Datensatzansichten \(MFC\-Datenzugriff\)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)