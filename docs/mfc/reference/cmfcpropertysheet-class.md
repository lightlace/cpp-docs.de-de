---
title: "CMFCPropertySheet Class"
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
  - "CMFCPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertySheet class"
  - "CMFCPropertySheet::OnInitDialog method"
  - "CMFCPropertySheet::PreTranslateMessage method"
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse `CMFCPropertySheet` unterstützt ein Eigenschaftenblatt, in dem jede Eigenschaftenseite durch eine Seitenregisterkarte, eine Symbolleisten\-Schaltfläche, einen Strukturansichtsknoten oder ein Listenelement angegeben wird.  
  
## Syntax  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCPropertySheet::CMFCPropertySheet](../Topic/CMFCPropertySheet::CMFCPropertySheet.md)|Erstellt ein `CMFCPropertySheet`\-Objekt.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md)|Fügt dem Eigenschaftsblatt eine Seite hinzu.|  
|[CMFCPropertySheet::AddPageToTree](../Topic/CMFCPropertySheet::AddPageToTree.md)|Fügt dem Struktursteuerelement eine neue Eigenschaftsseite hinzu.|  
|[CMFCPropertySheet::AddTreeCategory](../Topic/CMFCPropertySheet::AddTreeCategory.md)|Fügt dem Struktursteuerelement einen neuen Knoten hinzu.|  
|[CMFCPropertySheet::EnablePageHeader](../Topic/CMFCPropertySheet::EnablePageHeader.md)|Reserviert oben auf jeder Seite Platz, um einen benutzerdefinierten Header zu zeichnen.|  
|[CMFCPropertySheet::GetHeaderHeight](../Topic/CMFCPropertySheet::GetHeaderHeight.md)|Ruft die Höhe des aktuellen Headers ab.|  
|[CMFCPropertySheet::GetLook](../Topic/CMFCPropertySheet::GetLook.md)|Ruft einen Enumerationswert ab, der das Erscheinungsbild des aktuellen Eigenschaftsblatts angibt.|  
|[CMFCPropertySheet::GetNavBarWidth](../Topic/CMFCPropertySheet::GetNavBarWidth.md)|Ruft die Breite der Navigationsleiste in Pixel ab.|  
|[CMFCPropertySheet::GetTab](../Topic/CMFCPropertySheet::GetTab.md)|Ruft das interne Registerkarten\-Steuerelementobjekt ab, das das aktuelle Eigenschaftsblatt\-Steuerelement unterstützt.|  
|`CMFCPropertySheet::GetThisClass`|Wird vom Framework verwendet wird, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCPropertySheet::InitNavigationControl](../Topic/CMFCPropertySheet::InitNavigationControl.md)|Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt\-Steuerelements.|  
|[CMFCPropertySheet::OnActivatePage](../Topic/CMFCPropertySheet::OnActivatePage.md)|Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.|  
|[CMFCPropertySheet::OnDrawPageHeader](../Topic/CMFCPropertySheet::OnDrawPageHeader.md)|Wird durch das Framework aufgerufen, um einen benutzerdefinierten Eigenschaftsseitenheader zu zeichnen.|  
|`CMFCPropertySheet::OnInitDialog`|Verarbeitet die Meldung [WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428).  \(Überschreibt [CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md).\)|  
|[CMFCPropertySheet::OnRemoveTreePage](../Topic/CMFCPropertySheet::OnRemoveTreePage.md)|Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.|  
|`CMFCPropertySheet::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor diese an die Windows\-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden.  \(Überschreibt `CPropertySheet::PreTranslateMessage`.\)|  
|[CMFCPropertySheet::RemoveCategory](../Topic/CMFCPropertySheet::RemoveCategory.md)|Entfernt einen Knoten aus dem Struktursteuerelement.|  
|[CMFCPropertySheet::RemovePage](../Topic/CMFCPropertySheet::RemovePage.md)|Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.|  
|[CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md)|Gibt die Liste der Bilder an, die in der Navigationssteuerung des Outlook\-Bereichs verwendet werden.|  
|[CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md)|Gibt das Erscheinungsbild des Eigenschaftsblatts an.|  
  
## Hinweise  
 Die Klasse `CMFCPropertySheet` stellt Eigenschaftsblätter dar, auch als „Dialogfelder im Registerformat“ bezeichnet.  Die `CMFCPropertySheet`\-Klasse kann eine Eigenschaftsseite in einer Vielzahl von Möglichkeiten anzeigen.  
  
 Führen Sie die folgenden Schritte aus, um die `CMFCPropertySheet`\-Klasse in Ihrer Anwendung zu verwenden:  
  
1.  Leiten Sie eine Klasse aus der `CMFCPropertySheet`\-Klasse ab, und benennen Sie die Klasse, beispielsweise als „CMyPropertySheet“.  
  
2.  Erstellen Sie ein [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)\-Objekt für jede Eigenschaftsseite.  
  
3.  Rufen Sie die Methode [CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md) im CMyPropertySheet\-Konstruktor auf.  Ein Parameter dieser Methode gibt an, dass die Eigenschaftsseiten entweder als Registerkarten oben oder links im Eigenschaftsblatt oder als Registerkarten im Stile eines Microsoft OneNote\-Eigenschaftsblatts oder als Schaltflächen auf einem Microsoft Outlook\-Symbolleistensteuerelement oder als Knoten in einem Gesamtstruktursteuerelement oder als eine Liste von Elementen auf der linken Seite des Eigenschaftsblatt angezeigt werden sollen.  
  
4.  Rufen Sie beim Erstellen eines Eigenschaftsblatt im Stile einer Microsoft Outlook\-Symbolleiste die Methode [CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md) auf, um eine Bildliste zusammen mit den Eigenschaftsseiten zu verknüpfen.  
  
5.  Rufen Sie die Methode [CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md) für jede Eigenschaftsseite auf.  
  
6.  Erstellen Sie ein `CMFCPropertySheet`\-Steuerelement, und rufen Sie dessen `DoModal`\-Methode auf.  
  
## Abbildungen  
 In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile einer eingebetteten Microsoft Outlook\-Symbolleiste vorliegt.  Die Outlook\-Symbolleiste wird auf der linken Seite des Eigenschaftenfensters angezeigt.  
  
 ![CMFCPropertySheet&#45;Farbsteuerelemente](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet\_color")  
  
 Die folgende Abbildung zeigt ein Eigenschaftenblatt, das ein [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)\-Objekt enthält.  Bei diesem Objekt handelt es sich um ein Eigenschaftsblatt im Stile eines Eigenschaftsblatts für allgemeine Standardsteuerelemente.  
  
 ![CMFCPropertySheet&#45;Listen&#45; und Farbsteuerelemente](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet\_list")  
  
 In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile eines Struktursteuerelements vorliegt.  
  
 ![Eigenschaftenstruktur](../../mfc/reference/media/proptree.png "PropTree")  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## Anforderungen  
 **Header:** afxpropertysheet.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage Class](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)