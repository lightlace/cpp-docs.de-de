---
title: "CDaoRecordView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsassistenten [C++], creating record views"
  - "Gebundene Steuerelemente [C++], displaying database data"
  - "CDaoRecordView-Klasse"
  - "Steuerelemente [MFC], Datenbindung"
  - "Datenbindung [C++], DAO views"
  - "Datengebundene Steuerelemente [C++], DAO-Steuerelemente"
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
## Syntax  
  
```  
  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoRecordView::CDaoRecordView](../Topic/CDaoRecordView::CDaoRecordView.md)|Erstellt ein `CDaoRecordView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoRecordView::IsOnFirstRecord](../Topic/CDaoRecordView::IsOnFirstRecord.md)|Gibt Wert ungleich 0 zurück, wenn der aktuelle Datensatz der erste Datensatz im zugeordneten Recordset ist.|  
|[CDaoRecordView::IsOnLastRecord](../Topic/CDaoRecordView::IsOnLastRecord.md)|Gibt Wert ungleich 0 zurück, wenn der aktuelle Datensatz der letzte Datensatz im zugeordneten Recordset ist.|  
|[CDaoRecordView::OnGetRecordset](../Topic/CDaoRecordView::OnGetRecordset.md)|Gibt einen Zeiger auf ein Objekt einer Klasse zurück, die von `CDaoRecordset` abgeleitet wird.  Klassen\-Assistent überschreibt diese Funktion für Sie und erstellt das Recordset.|  
|[CDaoRecordView::OnMove](../Topic/CDaoRecordView::OnMove.md)|Wenn der aktuelle Datensatz geändert wurde, aktualisiert ihn auf der Datenquelle, dann wird in den angegebenen Datensatz \(nächsten, vorherigen, erste oder letzte\).|  
  
## Hinweise  
 Die Ansicht ist eine Formularansicht, die direkt mit einem `CDaoRecordset`\-Objekt verbunden ist.  Die Ansicht wird von einer Dialogfeldvorlagenressource erstellt und die Felder des `CDaoRecordset`\-Objekts in den Steuerelementen der Dialogfeldvorlage angezeigt werden.  Das Objekt `CDaoRecordView` verwendet den Dialogdatenaustausch \(DDX\) und DAO\-Datensatzfeldaustausch \(DFX\) um das Verschieben von Daten zwischen den Steuerelementen auf dem Formular und den Feldern des Recordsets zu automatisieren.  `CDaoRecordView` stellt auch eine Standardimplementierung für einen Wechsel zum ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle für den Datensatz in der Ansicht nur aktualisieren.  
  
> [!NOTE]
>  Die DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage Open Database Connectivity \(ODBC\) unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben das Präfix "CDao".  Sie können auf ODBC\-Datenquellen mit den DAO\-Klassen noch zugreifen; DAO\-Klassen bieten im Allgemeinen überlegene Funktionen, da sie das Microsoft Jet\-Datenbankmodul verwenden.  
  
 Die häufigste Möglichkeit, die Datensatzansicht zu erstellen ist mit dem Anwendungs\-Assistenten.  Der Anwendungs\-Assistent erstellt die Datensatzansichts\-Klasse und die zugeordnete Recordset\-Klasse als Teil der Skelettstarter\-Anwendung.  
  
 Wenn Sie einfach ein einzelnes Formular benötigen, ist der Anwendungs\-Assistenten\-Ansatz einfacher.  Klassen\-Assistent können Sie entscheiden, um eine Datensatzansicht im Entwicklungsprozess später zu verwenden.  Wenn Sie nicht die Datensatzansichts\-Klasse mithilfe des Anwendungs\-Assistenten erstellen, können Sie sie mit Klassen\-Assistent später erstellen.  Verwenden des Klassen\-Assistenten, eine Datensatzansicht und ein Recordset getrennt ist und sie dann herzustellen der flexibelste Ansatz, da er Ihnen mehr Kontrolle gibt, wenn er die Recordset\-Klasse und benennt sein. H\-\/.CPPdateien.  Mit dieser Methode können Sie auch mehrere Datensatzansichten auf derselben Recordset\-Klasse haben.  
  
 Um sie zu erleichtern erstellt damit Endbenutzer zum Verschieben von Datensätzen unterstützen in der Datensatzansicht, der Anwendungs\-Assistent Ressourcen des Menüs \(und optional Symbolleiste\) für einen Wechsel zum ersten, Folgendes, wenn oder letzten Datensatz.  Wenn Sie eine Datensatzansichts\-Klasse mit Klassen\-Assistent erstellen, müssen Sie diese Ressourcen selbst erstellen mit dem Menü und den Bitmap\-Editoren.  
  
 Informationen über die Standardimplementierung zum Verschieben von Datensätzen unterstützen, finden Sie unter `IsOnFirstRecord` und `IsOnLastRecord` und den Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md), der auf `CRecordView` und `CDaoRecordView` gilt.  
  
 `CDaoRecordView` registriert die Position des Benutzers im Recordset nachverfolgt, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann.  Wenn der Benutzer zu einem Ende des Recordsets wechselt, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte wie Menüelemente oder Symbolleisten\-Schaltflächen \- zum Verschieben weiter in die gleiche Richtung.  
  
 Weitere Informationen zum Deklarieren und Verwenden der Datensatzansicht und Recordset\-Klassen, finden Sie unter "Entwerfen und Erstellen einer Datensatzansicht" im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  Weitere Informationen dazu, wie Datensatzansichten funktionieren und wie sie verwendet, finden Sie im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  Alle Artikel, die oben erwähnten, gelten für `CRecordView` und `CDaoRecordView` zu.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## Anforderungen  
 **Header:**  afxdao.h  
  
## Siehe auch  
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)