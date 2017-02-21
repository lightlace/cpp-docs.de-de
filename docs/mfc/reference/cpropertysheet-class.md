---
title: "CPropertySheet Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertySheet class"
  - "Dialogfelder, Registerkarten"
  - "Eigenschaftenblätter, CPropertySheet class"
  - "Registerkarten-Dialogfelder"
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Eigenschaftenblätter, auch als Dialogfelder im Registerformat dar.  
  
## Syntax  
  
```  
class CPropertySheet : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md)|Erstellt ein `CPropertySheet`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md)|Fügt eine Seite dem Eigenschaftenblatt hinzu.|  
|[CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md)|Erstellt ein `CPropertySheet`\-Objekt.|  
|[CPropertySheet::Create](../Topic/CPropertySheet::Create.md)|Zeigt ein nicht modales Eigenschaftenblatt an.|  
|[CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md)|Zeigt ein modales Eigenschaftenblatt an.|  
|[CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md)|Gibt die ob gestapelte Eigenschaftenblattverwendung oder Bildlaufregisterkarten an.|  
|[CPropertySheet::EndDialog](../Topic/CPropertySheet::EndDialog.md)|Beendet das Eigenschaftenblatt.|  
|[CPropertySheet::GetActiveIndex](../Topic/CPropertySheet::GetActiveIndex.md)|Ruft den Index der aktuellen Seite des Eigenschaftenblatts ab.|  
|[CPropertySheet::GetActivePage](../Topic/CPropertySheet::GetActivePage.md)|Gibt das Objekt der aktiven Seite zurück.|  
|[CPropertySheet::GetPage](../Topic/CPropertySheet::GetPage.md)|Ruft einen Zeiger auf die angegebene Seite ab.|  
|[CPropertySheet::GetPageCount](../Topic/CPropertySheet::GetPageCount.md)|Ruft die Anzahl vonseiten im Eigenschaftenblatt ab.|  
|[CPropertySheet::GetPageIndex](../Topic/CPropertySheet::GetPageIndex.md)|Ruft den Index der angegebenen Seite des Eigenschaftenblatts ab.|  
|[CPropertySheet::GetTabControl](../Topic/CPropertySheet::GetTabControl.md)|Ruft einen Zeiger auf ein Tab\-Steuerelement ab.|  
|[CPropertySheet::MapDialogRect](../Topic/CPropertySheet::MapDialogRect.md)|Konvertiert die Dialogeinheiten eines Rechtecks, um Einheiten zu stößt.|  
|[CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md)|Überschreiben Sie, um von Eigenschaftenblattinitialisierung zu erweitern.|  
|[CPropertySheet::PressButton](../Topic/CPropertySheet::PressButton.md)|Simuliert die Auswahl der angegebenen Schaltfläche in einem Eigenschaftenblatt.|  
|[CPropertySheet::RemovePage](../Topic/CPropertySheet::RemovePage.md)|Entfernt eine Seite aus dem Eigenschaftenblatt.|  
|[CPropertySheet::SetActivePage](../Topic/CPropertySheet::SetActivePage.md)|Legt das Objekt programmgesteuert der aktiven Seite fest.|  
|[CPropertySheet::SetFinishText](../Topic/CPropertySheet::SetFinishText.md)|Legt den Text für die Endschaltfläche fest.|  
|[CPropertySheet::SetTitle](../Topic/CPropertySheet::SetTitle.md)|Legt die Beschriftung des Eigenschaftenblatts fest.|  
|[CPropertySheet::SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md)|Aktiviert die Assistentenschaltflächen.|  
|[CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)|Aktiviert den Assistentenmodus.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPropertySheet::m\_psh](../Topic/CPropertySheet::m_psh.md)|Die Struktur Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  Bietet Zugriff auf den grundlegenden Eigenschaftenblattparametern.|  
  
## Hinweise  
 Ein `CPropertySheet`\-Eigenschaftenblatt besteht aus einem Objekt und mindestens einem [CPropertyPage](../../mfc/reference/cpropertypage-class.md)\-Objekten.  Das Framework wird ein Eigenschaftenblatt als Fenster mit einem Satz von Registerkartenindizes und Bereich an, der die gerade ausgewählte Seite enthält.  Der Benutzer navigiert zu einer bestimmten Seite, indem er die entsprechende Registerkarte verwendet.  
  
 `CPropertySheet` bietet Unterstützung für die erweiterte [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)\-Struktur, die in [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] und in Windows NT 2000 eingeführt wurde.  Die Struktur enthält zusätzliche Flags und Member, die mit einer "Wasserzeichen" Hintergrundbitmaps unterstützen.  
  
 Um diese neuen Bilder in Ihrem Eigenschaftenblattobjekt automatisch anzuzeigen, übergeben Sie für die Bitmap\- und Palettenimages im Aufruf von [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) oder zu [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 Obwohl `CPropertySheet` nicht von [CDialog\-Klasse](../../mfc/reference/cdialog-class.md) abgeleitet ist, ein Objekt zu verwalten `CPropertySheet` ist wie das Verwalten eines `CDialog`\-Objekts.  Beispielsweise erfordert Erstellung eines Eigenschaftenblatts zweiteilige Konstruktion: Rufen Sie den Konstruktor, und rufen Sie dann [DoModal](../Topic/CPropertySheet::DoModal.md) für ein modales Eigenschaftenblatt oder [Erstellen Sie](../Topic/CPropertySheet::Create.md) für ein nicht modales Eigenschaftenblatt auf.  `CPropertySheet`\-Typen verfügt über zwei Konstruktoren: [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) und [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 Wenn Sie ein Objekt erstellen, `CPropertySheet` kann entweder [Fensterstile](../../mfc/reference/window-styles.md) Chance bewirken eine Ausnahme auftritt.  Dies ergibt sich vom System, die versucht, das Format des Eigenschaftenblatts zu ändern, bevor das Blatt erstellt wird.  Um diese Ausnahme zu vermeiden, dass Sie festgelegt den folgenden Formaten wenn Sie das `CPropertySheet` erstellen:  
  
-   DS\_3DLOOK  
  
-   DS\_CONTROL  
  
-   WS\_CHILD  
  
-   WS\_TABSTOP  
  
 Die folgenden Formate sind optional und werden nicht die Chance Ausnahme verursachen:  
  
-   DS\_SHELLFONT  
  
-   DS\_LOCALEDIT  
  
-   WS\_CLIPCHILDREN  
  
 Jedes andere `Window Styles` sind unzulässig und Sie sollten sie nicht aktivieren.  
  
 Austauschdaten `CPropertySheet` zwischen einem Objekt und einem externen Objekt sind an die Austauschdaten mit einem `CDialog`\-Objekt.  Der wichtige Unterschied ist, dass die Einstellungen eines Eigenschaftenblatts in der Regel Membervariablen der `CPropertyPage`\-Objekte und nicht als `CPropertySheet` des Objekts selbst sind.  
  
 Sie können einen Typ Dialogfeld im Registerformat erstellen aufgerufen einen Assistenten, der aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten besteht, die den Benutzer durch die Schritte eines Vorgangs, wie Installieren eines Geräts oder Erstellen eines Newsletters übergeben.  In einem assistentenartigdialogfeld im registerformat haben die Eigenschaftenseiten nicht Registerkarten, und nur eine Eigenschaftenseite ist gleichzeitig sichtbar.  Außerdem, anstatt **OK** und **Jetzt übernehmen** Schaltflächen zu haben, hat ein assistentenartigdialogfeld im registerformat eine Schaltfläche **Zurück**, eine **Weiter** oder Schaltfläche **Fertig stellen**, **Abbrechen** eine Schaltfläche und eine Schaltfläche **Hilfe**.  
  
 Um ein assistentenartigdialogfeld zu erstellen, führen Sie die gleichen Schritte zum Upgrade würden um ein Standardeigenschaftenblatt zu erstellen, aber bevor Sie Aufruf [SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)[DoModal](../Topic/CPropertySheet::DoModal.md) aufrufen.  Um die Assistentenschaltflächen zu aktivieren, rufen Sie [SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md), mit den Flags auf ihre Funktion und Darstellung anzupassen.  Um die Schaltfläche **Fertig stellen**, hat Aufruf [SetFinishText](../Topic/CPropertySheet::SetFinishText.md) nach dem Benutzer zu ermöglichen Aktionen auf der letzten Seite des Assistenten ausgeführt.  
  
 Weitere Informationen dazu, wie `CPropertySheet`\-Objekte, finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md) verwendet.  Außerdem finden Sie im Knowledge Base\-Artikel Q146916: HOWTO: Erstellen Sie ein nicht modales CPropertySheet mit Standardschaltflächen und Artikel Q300606: HOWTO: Entwerfen Sie ein in der Größe veränderbares MFC\-Eigenschaftenblatt.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## Anforderungen  
 **Header:** afxdlgs.h  
  
## Siehe auch  
 [MFC Sampling CMNCTRL1](../../top/visual-cpp-samples.md)   
 [Das MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [Bei MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel SNAPVW](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)