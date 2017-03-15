---
title: "Verwenden von OLE&#160;DB-Datensatzansichten | Microsoft Docs"
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
  - "COleDBRecordView-Klasse, Übersicht"
  - "MFC, Datensatzansichten"
  - "OLE DB-Datensatzansichten"
  - "OLE DB, Datensatzansichten"
  - "Datensatzansichten, Datensatzansichtsobjekte"
  - "Rowsets, Datensatzansichten"
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden von OLE&#160;DB-Datensatzansichten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie OLE DB\-Rowsetdaten in einer MFC\-Anwendung anzeigen möchten, sollten Sie die MFC\-Klasse [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md) verwenden.  Ein mithilfe von `COleDBRecordView` erstelltes Datensatzansichtsobjekt erlaubt es Ihnen, Datenbankdatensätze in MFC\-Steuerelementen anzuzeigen.  Die Datensatzansicht ist eine Dialogformularansicht mit direkter Verbindung zu einem aus der `CRowset`\-Vorlagenklasse erstellten OLE DB\-Rowset\-Objekt.  Es ist sehr einfach, ein Handle für das Rowset\-Objekt zu beziehen:  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 In der Ansicht werden die Felder des `CRowset`\-Objekts in den Steuerelementen des Dialogfelds angezeigt.  Das `COleDBRecordView`\-Objekt verwendet den Dialogdatenaustausch \(DDX, Dialog Data Exchange\) und die Navigationsfunktionen von `CRowset` \(**MoveFirst**, `MoveNext`, `MovePrev` und `MoveLast`\), um das Verschieben der Daten zwischen den Steuerelementen auf dem Formular und den Feldern des Rowsets zu automatisieren.  `COleDBRecordView` registriert die Position des Benutzers im Rowset, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann, und stellt vor dem Wechseln zum nächsten Datensatz eine [OnMove](../Topic/COleDBRecordView::OnMove.md)\-Methode zum Aktualisieren des aktuellen Datensatzes zur Verfügung.  
  
 Sie können DDX\-Funktionen mit **COleDbRecordView** verwenden, um Daten direkt aus dem Datenbankrecordset zu beziehen und sie in einem Dialogfeld\-Steuerelement anzuzeigen.  Sie sollten mit **COleDbRecordView** die **DDX\_\***\-Methoden \(z. B. `DDX_Text`\), jedoch nicht die **DDX\_Field\***\-Funktionen \(z. B. `DDX_FieldText`\) verwenden.  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)   
 [COleDBRecordView Class](../../mfc/reference/coledbrecordview-class.md)