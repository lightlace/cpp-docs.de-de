---
title: "COleDBRecordView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDBRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDBRecordView-Klasse"
  - "MFC, OLE DB"
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# COleDBRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
## Syntax  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](../Topic/COleDBRecordView::COleDBRecordView.md)|Erstellt ein `COleDBRecordView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](../Topic/COleDBRecordView::OnGetRowset.md)|Gibt einen `HRESULT`\-Standardwert zurück.|  
|[COleDBRecordView::OnMove](../Topic/COleDBRecordView::OnMove.md)|Aktualisiert den aktuellen Datensatz \(falls geändert\) auf der Datenquelle und wird dann an die angegebenen Datensatz \(nächster, vorheriger, erster oder letzter\).|  
  
## Hinweise  
 Die Ansicht ist eine Formularansicht, die direkt mit einem `CRowset`\-Objekt verbunden ist.  Die Ansicht wird von einer Dialogfeldvorlagenressource erstellt und die Felder des `CRowset`\-Objekts in den Steuerelementen der Dialogfeldvorlage angezeigt werden.  Das Objekt `COleDBRecordView` verwendet den Dialogdatenaustausch \(DDX\) und die Navigationsfunktionen Funktionen, die in `CRowset` erstellt wird, um das Verschieben von Daten zwischen den Steuerelementen auf dem Formular und den Feldern des Rowsets zu automatisieren.  `COleDBRecordView` stellt auch eine Standardimplementierung für einen Wechsel zum ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren des aktuell.  
  
 Sie können DDX\-Funktionen mit **COleDbRecordView** verwenden, um Daten direkt aus dem Datenbankrecordset zu beziehen und sie in einem Dialogfeld\-Steuerelement anzuzeigen.  Sie sollten mit **COleDbRecordView** die **DDX\_\***\-Methoden \(z. B. `DDX_Text`\), jedoch nicht die **DDX\_Field\***\-Funktionen \(z. B. `DDX_FieldText`\) verwenden.  `DDX_FieldText` funktioniert nicht mit **COleDbRecordView**, da `DDX_FieldText` ein zusätzliches Argument vom Typ **CRecordset\*** \(für `CRecordView`\) oder **CDaoRecordset\*** akzeptiert \(für `CDaoRecordView`\).  
  
> [!NOTE]
>  Wenn Sie mit den Datenzugriffsobjekten \(DAO\) Klasse anstelle der OLE DB\-Consumervorlagenklassen, Verwendungsklasse [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) stattdessen arbeiten.  Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView` registriert die Position des Benutzers im Rowset nachverfolgt, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann.  Wenn der Benutzer zu einem Ende des Rowsets wechselt, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte wie Menüelemente oder Symbolleisten\-Schaltflächen \- zum Verschieben weiter in die gleiche Richtung.  
  
 Weitere Informationen zu Rowsetklassen, finden Sie im [Verwenden von OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md) Artikel.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## Anforderungen  
 **Header:**  afxoledb.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)