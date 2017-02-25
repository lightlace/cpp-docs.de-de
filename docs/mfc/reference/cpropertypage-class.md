---
title: "CPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPage class"
  - "Dialogfelder, Registerkarten"
  - "Eigenschaftenseiten, CPropertyPage class"
  - "Registerkarten-Dialogfelder"
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die einzelnen Seiten eines Eigenschaftenblatts dar; andernfalls wird als ein Dialogfeld im Registerformat.  
  
## Syntax  
  
```  
class CPropertyPage : public CDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](../Topic/CPropertyPage::CPropertyPage.md)|Erstellt ein `CPropertyPage`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](../Topic/CPropertyPage::CancelToClose.md)|Ändert die Schaltfläche OK, um den Abschluss zu lesen und die Abbruchschaltfläche deaktiviert, nach einer nicht behebbaren Änderung auf der Seite eines modalen Eigenschaftenblatts.|  
|[CPropertyPage::Construct](../Topic/CPropertyPage::Construct.md)|Erstellt ein `CPropertyPage`\-Objekt.  Verwenden Sie `Construct`, wenn Sie die zur Laufzeit Parameter angeben möchten oder wenn Sie Arrays verwenden.|  
|[CPropertyPage::GetPSP](../Topic/CPropertyPage::GetPSP.md)|Ruft die Struktur Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) ab, die dem `CPropertyPage`\-Objekt zugeordnet ist.|  
|[CPropertyPage::OnApply](../Topic/CPropertyPage::OnApply.md)|Aufgerufen vom Framework, wenn das zugewiesen, jetzt Schaltfläche geklickt wird.|  
|[CPropertyPage::OnCancel](../Topic/CPropertyPage::OnCancel.md)|Aufgerufen vom Framework, wenn auf die Schaltfläche Abbrechen geklickt wird.|  
|[CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md)|Aufgerufen vom Framework, wenn die aktuelle Seite nicht mehr die aktuelle Seite ist.  Datenvalidierung hier durchführen.|  
|[CPropertyPage::OnOK](../Topic/CPropertyPage::OnOK.md)|Aufgerufen vom Framework, wenn OK, jetzt gelten oder Schaltfläche Schließen geklickt wird.|  
|[CPropertyPage::OnQueryCancel](../Topic/CPropertyPage::OnQueryCancel.md)|Aufgerufen vom Framework, wenn auf die Schaltfläche Abbrechen geklickt und vor dem Löschen stattgefunden hat.|  
|[CPropertyPage::OnReset](../Topic/CPropertyPage::OnReset.md)|Aufgerufen vom Framework, wenn auf die Schaltfläche Abbrechen geklickt wird.|  
|[CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md)|Aufgerufen vom Framework, wenn die Seite die aktuelle Seite ausgeführt wird.|  
|[CPropertyPage::OnWizardBack](../Topic/CPropertyPage::OnWizardBack.md)|Aufgerufen vom Framework, wenn auf die Schaltfläche "Zurück" bei Verwendung eines assistentenartigeigenschaftenblatts geklickt wird.|  
|[CPropertyPage::OnWizardFinish](../Topic/CPropertyPage::OnWizardFinish.md)|Aufgerufen vom Framework, wenn auf die Endschaltfläche bei Verwendung eines assistentenartigeigenschaftenblatts geklickt wird.|  
|[CPropertyPage::OnWizardNext](../Topic/CPropertyPage::OnWizardNext.md)|Aufgerufen vom Framework, wenn auf die nächste Schaltfläche bei Verwendung eines assistentenartigeigenschaftenblatts geklickt wird.|  
|[CPropertyPage::QuerySiblings](../Topic/CPropertyPage::QuerySiblings.md)|Leitet die Meldung an jede Seite des Eigenschaftenblatts weiter.|  
|[CPropertyPage::SetModified](../Topic/CPropertyPage::SetModified.md)|Der aufrufen, um den angewendete zu aktivieren oder zu deaktivieren Schaltfläche jetzt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPropertyPage::m\_psp](../Topic/CPropertyPage::m_psp.md)|Die Struktur Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  Bietet Zugriff auf den grundlegenden Eigenschaftenseitenparametern.|  
  
## Hinweise  
 Wie bei Standarddialogfeldern, leiten Sie eine Klasse von `CPropertyPage` für jede Seite im Eigenschaftenblatt.  Um `CPropertyPage` abgeleitete Objekte zu verwenden, erstellen Sie zuerst ein [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)\-Objekt, und erstellen Sie dann ein Objekt für jede Seite die in das Eigenschaftenblatt wechselt.  Rufen Sie [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) für jede Seite im Blatt, und zeigen Sie dann das Eigenschaftenblatt, indem Sie [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) für ein modales Eigenschaftenblatt aufrufen, oder [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) für ein nicht modales Eigenschaftenblatt an.  
  
 Sie können einen Typ Dialogfeld im Registerformat erstellen aufgerufen einen Assistenten, der aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten besteht, die den Benutzer durch die Schritte eines Vorgangs, wie Installieren eines Geräts oder Erstellen eines Newsletters übergeben.  In einem assistentenartigdialogfeld im registerformat haben die Eigenschaftenseiten nicht Registerkarten, und nur eine Eigenschaftenseite ist gleichzeitig sichtbar.  Außerdem, anstatt OK auf und wenden Sie jetzt Schaltflächen, hat ein assistentenartigdialogfeld im registerformat eine Schaltfläche Zurück, ein nachfolgendes oder beendet und Schaltfläche Abbrechen.  
  
 Weitere Informationen zum Einrichten eines Eigenschaftenblatts als Assistent, finden Sie unter [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md).  Weitere Informationen zur Verwendung von `CPropertyPage`\-Objekten, finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## Anforderungen  
 **Header:**  afxdlgs.h  
  
## Siehe auch  
 [MFC Sampling CMNCTRL1](../../top/visual-cpp-samples.md)   
 [Das MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [Bei MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel SNAPVW](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)