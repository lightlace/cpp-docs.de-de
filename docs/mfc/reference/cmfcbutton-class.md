---
title: "CMFCButton Class"
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
  - "CMFCButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCButton class"
  - "CMFCButton constructor"
  - "CMFCButton::CreateObject method"
  - "CMFCButton::DrawItem method"
  - "CMFCButton::OnDrawParentBackground method"
  - "CMFCButton::PreTranslateMessage method"
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: 35
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse fügt `CMFCButton`\-Funktionen der [CButton](../../mfc/reference/cbutton-class.md)\-Klasse wie Einstimmung des Schaltflächentexts, Kombination des Schaltflächentexts und des Bilds, Auswählen eines Cursors und Angeben einer QuickInfo hinzu.  
  
## Syntax  
  
```  
class CMFCButton : public CButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|Standardkonstruktor.|  
|`CMFCButton::~CMFCButton`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCButton::CleanUp](../Topic/CMFCButton::CleanUp.md)|Setzt interne Variablen zurück und gibt zugeordnete Ressourcen wie Bilder, Bitmaps und Symbole frei.|  
|`CMFCButton::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCButton::DrawItem`|Aufgerufen vom Framework ausgelöst, wenn ein visueller Aspekt einer Ownerdrawnschaltfläche geändert hat.  \(Überschreibungen [CButton::DrawItem](../Topic/CButton::DrawItem.md).\)|  
|[CMFCButton::EnableFullTextTooltip](../Topic/CMFCButton::EnableFullTextTooltip.md)|Gibt an, ob der Text einer QuickInfo in einem großen QuickInfo\-Fenster oder eine abgeschnittene Version des Texts in einem kleinen QuickInfo\-Fenster angezeigt wird.|  
|[CMFCButton::EnableMenuFont](../Topic/CMFCButton::EnableMenuFont.md)|Gibt an, ob die Schaltflächentextschriftart mit der Anwendungsmenüschriftart ist.|  
|[CMFCButton::EnableWindowsTheming](../Topic/CMFCButton::EnableWindowsTheming.md)|Gibt an, ob das Format der Knopfleiste dem Design der aktiven Fenster entspricht.|  
|`CMFCButton::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCButton::GetToolTipCtrl](../Topic/CMFCButton::GetToolTipCtrl.md)|Gibt einen Verweis auf den zugrunde liegenden QuickInfosteuerelement zurück.|  
|[CMFCButton::IsAutoCheck](../Topic/CMFCButton::IsAutoCheck.md)|Gibt an, ob ein Kontrollkästchen oder ein Optionsfeld eine automatische Schaltfläche ist.|  
|[CMFCButton::IsAutorepeatCommandMode](../Topic/CMFCButton::IsAutorepeatCommandMode.md)|Gibt an, ob eine Schaltfläche zu AUTOREPEAT\-Modus festgelegt ist.|  
|[CMFCButton::IsCheckBox](../Topic/CMFCButton::IsCheckBox.md)|Gibt an, ob eine Schaltfläche eine Kontrollkästchenschaltfläche ist.|  
|[CMFCButton::IsChecked](../Topic/CMFCButton::IsChecked.md)|Gibt an, ob die aktuelle Schaltfläche überprüft wird.|  
|[CMFCButton::IsHighlighted](../Topic/CMFCButton::IsHighlighted.md)|Gibt an, ob eine Schaltfläche hervorgehoben wird.|  
|[CMFCButton::IsPressed](../Topic/CMFCButton::IsPressed.md)|Gibt an, ob eine Schaltfläche gedrückt und hervorgehoben wird.|  
|[CMFCButton::IsPushed](../Topic/CMFCButton::IsPushed.md)|Gibt an, ob eine Schaltfläche gedrückt ist.|  
|[CMFCButton::IsRadioButton](../Topic/CMFCButton::IsRadioButton.md)|Gibt an, ob eine Schaltfläche ein Optionsfeld ist.|  
|[CMFCButton::IsWindowsThemingEnabled](../Topic/CMFCButton::IsWindowsThemingEnabled.md)|Gibt an, ob das Format der Knopfleiste dem Design der aktiven Fenster entspricht.|  
|`CMFCButton::OnDrawParentBackground`|Zeichnet den Hintergrund des übergeordneten Elements einer Schaltfläche im angegebenen Bereich.  \(Überschreibungen [AFX\_GLOBAL\_DATA::DrawParentBackground](../Topic/AFX_GLOBAL_DATA::DrawParentBackground.md).\)|  
|`CMFCButton::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCButton::SetAutorepeatMode](../Topic/CMFCButton::SetAutorepeatMode.md)|Legt eine Schaltfläche zu AUTOREPEAT\-Modus fest.|  
|[CMFCButton::SetCheckedImage](../Topic/CMFCButton::SetCheckedImage.md)|Legt das Bild für eine überprüfte Schaltfläche fest.|  
|[CMFCButton::SetFaceColor](../Topic/CMFCButton::SetFaceColor.md)|Legt die Hintergrundfarbe für den Schaltflächentext fest.|  
|[CMFCButton::SetImage](../Topic/CMFCButton::SetImage.md)|Legt das Bild für eine Schaltfläche fest.|  
|[CMFCButton::SetMouseCursor](../Topic/CMFCButton::SetMouseCursor.md)|Legt das Cursor\-Image fest.|  
|[CMFCButton::SetMouseCursorHand](../Topic/CMFCButton::SetMouseCursorHand.md)|Legt den Cursor zum Bild einer Hand fest.|  
|[CMFCButton::SetStdImage](../Topic/CMFCButton::SetStdImage.md)|Wird ein `CMenuImages`\-Objekt, um das Schaltflächensymbol festzulegen.|  
|[CMFCButton::SetTextColor](../Topic/CMFCButton::SetTextColor.md)|Legt die Farbe des Schaltflächentexts für eine Schaltfläche fest, die nicht ausgewählt ist.|  
|[CMFCButton::SetTextHotColor](../Topic/CMFCButton::SetTextHotColor.md)|Legt die Farbe des Schaltflächentexts für eine Schaltfläche fest, die ausgewählt ist.|  
|[CMFCButton::SetTooltip](../Topic/CMFCButton::SetTooltip.md)|Ordnet eine QuickInfo mit einer Schaltfläche auf.|  
|[CMFCButton::SizeToContent](../Topic/CMFCButton::SizeToContent.md)|Ändert eine Schaltfläche Größe, um den Schaltflächentext und \-Image zu enthalten.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCButton::OnDraw](../Topic/CMFCButton::OnDraw.md)|Aufgerufen vom Framework, um eine Schaltfläche zu zeichnen.|  
|[CMFCButton::OnDrawBorder](../Topic/CMFCButton::OnDrawBorder.md)|Aufgerufen vom Framework, um den Kontext einer Schaltfläche zu zeichnen.|  
|[CMFCButton::OnDrawFocusRect](../Topic/CMFCButton::OnDrawFocusRect.md)|Aufgerufen vom Framework, um das Fokusrechteck für eine Schaltfläche zu zeichnen.|  
|[CMFCButton::OnDrawText](../Topic/CMFCButton::OnDrawText.md)|Aufgerufen durch das Framework, um den Schaltflächentext zu zeichnen.|  
|[CMFCButton::OnFillBackground](../Topic/CMFCButton::OnFillBackground.md)|Aufgerufen durch das Framework, um den Hintergrund des Schaltflächentexts zu zeichnen.|  
|[CMFCButton::SelectFont](../Topic/CMFCButton::SelectFont.md)|Ruft die Schriftart ab, die dem angegebenen Gerätekontext zugeordnet ist.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCButton::m\_bDrawFocus](../Topic/CMFCButton::m_bDrawFocus.md)|Gibt an, ob ein Fokusrechteck um eine Schaltfläche gezeichnet wird.|  
|[CMFCButton::m\_bHighlightChecked](../Topic/CMFCButton::m_bHighlightChecked.md)|Gibt an, ob ein BS\_CHECKBOX\-style " hervorhebt, wenn der Cursor darauf gezeigt.|  
|[CMFCButton::m\_bRightImage](../Topic/CMFCButton::m_bRightImage.md)|Gibt an, ob ein Bild auf der rechten Seite der Schaltfläche angezeigt wird.|  
|[CMFCButton::m\_bTransparent](../Topic/CMFCButton::m_bTransparent.md)|Gibt an, ob die Schaltfläche transparent ist.|  
|[CMFCButton::m\_nAlignStyle](../Topic/CMFCButton::m_nAlignStyle.md)|Gibt die Ausrichtung des Schaltflächentexts an.|  
|[CMFCButton::m\_nFlatStyle](../Topic/CMFCButton::m_nFlatStyle.md)|Gibt das Format der Schaltfläche, wie grenzenfreies, zurück, halbflaches oder 3D an.|  
  
## Hinweise  
 Andere Typen Schaltflächen werden von der `CMFCButton`\-Klasse, wie der [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md)\-Klasse, die Links unterstützt, und der `CMFCColorButton`\-Klasse abgeleitet, die ein Farben\-Auswahldialogfeld unterstützt.  
  
 Das Format eines Objekts kann `CMFCButton`*3D*, *flach*, *halbflaches* sein oder *kein Rahmen*.  Schaltflächentext kann links ausgerichtet werden, oberen oder Mittelpunkt einer Schaltfläche.  Zur Laufzeit können Sie steuern, ob die auf, ein Bild oder Text und ein Bild Text.  Sie können auch angeben, dass ein bestimmtes Cursor\-Image angezeigt wird, wenn der Cursor auf einer Schaltfläche zeigt.  
  
 Erstellen Sie ein Button\-Steuerelement entweder direkt im Code oder das Tool **MFC\-Klassen\-Assistent** und eine Dialogfeldvorlage verwenden.  Wenn Sie ein Button\-Steuerelement direkt erstellen, fügen Sie eine `CMFCButton`\-Variable der Anwendung hinzu, und rufen Sie dann den Konstruktor auf und `Create`\-Methoden `CMFCButton` ein Objekt.  Wenn Sie **MFC\-Klassen\-Assistent** verwenden, fügen Sie eine `CButton`\-Variable der Anwendung hinzu, und ändern Sie dann den Typ der Variablen von `CButton` zu `CMFCButton`.  
  
 Um Benachrichtigungsmeldungen in einer Dialogfeld\-Anwendung zu bearbeiten, fügen Sie einen Eintrag in der Meldungszuordnung und Ereignishandler für jede Benachrichtigung hinzu.  Die Benachrichtigungen, die durch ein `CMFCButton`\-Objekt gesendet werden, sind identisch mit denen, die von einem `CButton`\-Objekt gesendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Eigenschaften der Schaltfläche konfiguriert, indem verschiedene Methoden in der `CMFCButton`\-Klasse angewendet wird.  Das Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#28](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#28)]  
[!CODE [NVC_MFC_NewControls#31](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#31)]  
[!CODE [NVC_MFC_NewControls#32](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#32)]  
[!CODE [NVC_MFC_NewControls#33](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#33)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## Anforderungen  
 **Header:** afxbutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl Class](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton\-Klasse](../../mfc/reference/cmfcmenubutton-class.md)