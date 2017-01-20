---
title: "CRecordView Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecordView-Klasse"
  - "ODBC-Recordsets, viewing records"
  - "Datensätze, viewing ODBC"
  - "Ansichten, ODBC"
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
caps.latest.revision: 25
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
## Syntax  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRecordView::CRecordView](../Topic/CRecordView::CRecordView.md)|Erstellt ein `CRecordView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRecordView::IsOnFirstRecord](../Topic/CRecordView::IsOnFirstRecord.md)|Gibt Wert ungleich 0 zurück, wenn der aktuelle Datensatz der erste Datensatz im zugeordneten Recordset ist.|  
|[CRecordView::IsOnLastRecord](../Topic/CRecordView::IsOnLastRecord.md)|Gibt Wert ungleich 0 zurück, wenn der aktuelle Datensatz der letzte Datensatz im zugeordneten Recordset ist.|  
|[CRecordView::OnGetRecordset](../Topic/CRecordView::OnGetRecordset.md)|Gibt einen Zeiger auf ein Objekt einer Klasse zurück, die von `CRecordset` abgeleitet wird.  Klassen\-Assistent überschreibt diese Funktion für Sie und erstellt das Recordset.|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)||  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)|Wenn der aktuelle Datensatz geändert wurde, aktualisiert ihn auf der Datenquelle, dann wird in den angegebenen Datensatz \(nächsten, vorherigen, erste oder letzte\).|  
  
## Hinweise  
 Die Ansicht ist eine Formularansicht, die direkt mit einem `CRecordset`\-Objekt verbunden ist.  Die Ansicht wird von einer Dialogfeldvorlagenressource erstellt und die Felder des `CRecordset`\-Objekts in den Steuerelementen der Dialogfeldvorlage angezeigt werden.  Das Objekt `CRecordView` verwendet den Dialogdatenaustausch \(DDX\) und Datensatzfeldaustausch \(RFX\) um das Verschieben von Daten zwischen den Steuerelementen auf dem Formular und den Feldern des Recordsets zu automatisieren.  `CRecordView` stellt auch eine Standardimplementierung für einen Wechsel zum ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren des aktuell.  
  
> [!NOTE]
>  Wenn Sie mit den Datenzugriffsobjekten \(DAO\) Klasse anstatt die Klassen der Open Database Connectivity \(ODBC\), Verwendungsklasse [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) stattdessen arbeiten.  Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Die häufigste Möglichkeit, die Datensatzansicht zu erstellen ist mit dem Anwendungs\-Assistenten.  Tge\-Anwendungs\-Assistent erstellt die Datensatzansichts\-Klasse und die zugeordnete Recordset\-Klasse als Teil der Skelettstarter\-Anwendung.  Wenn Sie nicht die Datensatzansichts\-Klasse mithilfe des Anwendungs\-Assistenten erstellen, können Sie sie mit Klassen\-Assistent später erstellen.  Wenn Sie einfach ein einzelnes Formular benötigen, ist der Anwendungs\-Assistenten\-Ansatz einfacher.  Klassen\-Assistent können Sie entscheiden, um eine Datensatzansicht im Entwicklungsprozess später zu verwenden.  Verwenden des Klassen\-Assistenten, eine Datensatzansicht und ein Recordset getrennt ist und sie dann herzustellen der flexibelste Ansatz, da er Ihnen mehr Kontrolle gibt, wenn er die Recordset\-Klasse und benennt sein. H\-\/.CPPdateien.  Mit dieser Methode können Sie auch mehrere Datensatzansichten auf derselben Recordset\-Klasse haben.  
  
 Um sie zu erleichtern erstellt damit Endbenutzer zum Verschieben von Datensätzen unterstützen in der Datensatzansicht, der Anwendungs\-Assistent Ressourcen des Menüs \(und optional Symbolleiste\) für einen Wechsel zum ersten, Folgendes, wenn oder letzten Datensatz.  Wenn Sie eine Datensatzansichts\-Klasse mit Klassen\-Assistent erstellen, müssen Sie diese Ressourcen selbst erstellen mit dem Menü und den Bitmap\-Editoren.  
  
 Informationen über die Standardimplementierung zum Verschieben von Datensätzen unterstützen, finden Sie unter `IsOnFirstRecord` und `IsOnLastRecord` und der Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView` registriert die Position des Benutzers im Recordset nachverfolgt, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann.  Wenn der Benutzer zu einem Ende des Recordsets wechselt, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte wie Menüelemente oder Symbolleisten\-Schaltflächen \- zum Verschieben weiter in die gleiche Richtung.  
  
 Weitere Informationen zum Deklarieren und Verwenden der Datensatzansicht und Recordset\-Klassen, finden Sie unter "Entwerfen und Erstellen einer Datensatzansicht" im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  Weitere Informationen dazu, wie Datensatzansichten funktionieren und wie sie verwendet, finden Sie im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## Anforderungen  
 **Header:**  afxdb.h  
  
## Siehe auch  
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)