---
title: "CToolBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl class"
  - "QuickInfos [C++], Benachrichtigungen"
  - "Symbolleisten-Steuerelemente [MFC], CToolBarCtrl class"
  - "Windows common controls [C++], CToolBarCtrl"
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CToolBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität der Windows\-Symbolleistengemeinsamen allgemeinen ToolTip\-Steuerelement bereit.  
  
## Syntax  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CToolBarCtrl::CToolBarCtrl](../Topic/CToolBarCtrl::CToolBarCtrl.md)|Erstellt ein `CToolBarCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CToolBarCtrl::AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md)|Fügt eine oder mehrere Bit\-Übersichtsschaltflächensymbole der Liste der Schaltflächenbilder hinzu, die für ein ToolBar\-Steuerelement verfügbar sind.|  
|[CToolBarCtrl::AddButtons](../Topic/CToolBarCtrl::AddButtons.md)|Fügt eine oder mehrere Schaltflächen einem ToolBar\-Steuerelement hinzu.|  
|[CToolBarCtrl::AddString](../Topic/CToolBarCtrl::AddString.md)|Fügt eine neue Zeichenfolge hinzu, übergeben als Ressourcen\-ID, der internen Liste der Symbolleiste von Zeichenfolgen.|  
|[CToolBarCtrl::AddStrings](../Topic/CToolBarCtrl::AddStrings.md)|Fügt eine neue Zeichenfolge oder Zeichenfolgen hinzu, übergeben wie ein Zeiger einem Puffer von NULL\-getrennten Zeichenfolgen, zur internen Liste der Symbolleiste von Zeichenfolgen.|  
|[CToolBarCtrl::AutoSize](../Topic/CToolBarCtrl::AutoSize.md)|Ändert ein ToolBar\-Steuerelement Größe.|  
|[CToolBarCtrl::ChangeBitmap](../Topic/CToolBarCtrl::ChangeBitmap.md)|Ändert die Bitmap für eine Schaltfläche im aktuellen ToolBar\-Steuerelement.|  
|[CToolBarCtrl::CheckButton](../Topic/CToolBarCtrl::CheckButton.md)|Überprüfungen oder freie Räume eine angegebene Schaltfläche in einem ToolBar\-Steuerelement.|  
|[CToolBarCtrl::CommandToIndex](../Topic/CToolBarCtrl::CommandToIndex.md)|Ruft den nullbasierten Index für die Schaltfläche ab, die dem angegebenen Befehlskennzeichen zugeordnet ist.|  
|[CToolBarCtrl::Create](../Topic/CToolBarCtrl::Create.md)|Erstellt ein ToolBar\-Steuerelement und fügt es zu einem `CToolBarCtrl`\-Objekt.|  
|[CToolBarCtrl::CreateEx](../Topic/CToolBarCtrl::CreateEx.md)|Erstellt ein ToolBar\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CToolBarCtrl`\-Objekt.|  
|[CToolBarCtrl::Customize](../Topic/CToolBarCtrl::Customize.md)|Zeigt das Anpassens\-Symbolleistendialogfeld an.|  
|[CToolBarCtrl::DeleteButton](../Topic/CToolBarCtrl::DeleteButton.md)|Löscht eine Schaltfläche aus ToolBar\-Steuerelement.|  
|[CToolBarCtrl::EnableButton](../Topic/CToolBarCtrl::EnableButton.md)|Aktiviert oder deaktiviert die angegebene Schaltfläche in einem ToolBar\-Steuerelement.|  
|[CToolBarCtrl::GetAnchorHighlight](../Topic/CToolBarCtrl::GetAnchorHighlight.md)|Ruft die Anker\-Hervorhebungseinstellung für eine Symbolleiste ab.|  
|[CToolBarCtrl::GetBitmap](../Topic/CToolBarCtrl::GetBitmap.md)|Ruft den Index der Bitmap ab, die mit einer Schaltfläche in einer Symbolleiste zugeordnet ist.|  
|[CToolBarCtrl::GetBitmapFlags](../Topic/CToolBarCtrl::GetBitmapFlags.md)|Ruft die Flags ab, die mit der Bitmap der Symbolleiste zugeordnet werden.|  
|[CToolBarCtrl::GetButton](../Topic/CToolBarCtrl::GetButton.md)|Ruft Informationen über die angegebene Schaltfläche in einem ToolBar\-Steuerelement ab.|  
|[CToolBarCtrl::GetButtonCount](../Topic/CToolBarCtrl::GetButtonCount.md)|Ruft eine Anzahl der Schaltflächen derzeit im ToolBar\-Steuerelement ab.|  
|[CToolBarCtrl::GetButtonInfo](../Topic/CToolBarCtrl::GetButtonInfo.md)|Ruft die Informationen für eine Schaltfläche in einer Symbolleiste ab.|  
|[CToolBarCtrl::GetButtonSize](../Topic/CToolBarCtrl::GetButtonSize.md)|Ruft die aktuelle Breite und Höhe Symbolleisten\-Schaltflächen, in Pixel ab.|  
|[CToolBarCtrl::GetColorScheme](../Topic/CToolBarCtrl::GetColorScheme.md)|Ruft das Farbschema des aktuellen Symbolleisten\-Steuerelements ab.|  
|[CToolBarCtrl::GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md)|Ruft die Bildliste ab, die ein ToolBar\-Steuerelement verwendet, um deaktivierte Schaltflächen anzuzeigen.|  
|[CToolBarCtrl::GetDropTarget](../Topic/CToolBarCtrl::GetDropTarget.md)|Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)\-Schnittstelle für ein ToolBar\-Steuerelement ab.|  
|[CToolBarCtrl::GetExtendedStyle](../Topic/CToolBarCtrl::GetExtendedStyle.md)|Ruft die erweiterten Formate für ein ToolBar\-Steuerelement ab.|  
|[CToolBarCtrl::GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md)|Ruft die Bildliste ab, die ein ToolBar\-Steuerelement verwendet, um "heiße" Schaltflächen anzuzeigen.  Eine aktive Schaltfläche wird hervorgehoben, wenn der Mauszeiger darüber befindet.|  
|[CToolBarCtrl::GetHotItem](../Topic/CToolBarCtrl::GetHotItem.md)|Ruft den Index des hervorgehobenen Elements in einer Symbolleiste ab.|  
|[CToolBarCtrl::GetImageList](../Topic/CToolBarCtrl::GetImageList.md)|Ruft die Bildliste ab, die ein ToolBar\-Steuerelement verwendet, um Schaltflächen im Standardzustand anzuzeigen.|  
|[CToolBarCtrl::GetInsertMark](../Topic/CToolBarCtrl::GetInsertMark.md)|Ruft die aktuelle Einfügemarke für die Symbolleiste ab.|  
|[CToolBarCtrl::GetInsertMarkColor](../Topic/CToolBarCtrl::GetInsertMarkColor.md)|Ruft die Farbe ab, die verwendet wird, um die Einfügemarke für die Symbolleiste zu zeichnen.|  
|[CToolBarCtrl::GetItemRect](../Topic/CToolBarCtrl::GetItemRect.md)|Ruft das umschließende Rechteck einer Schaltfläche in einem ToolBar\-Steuerelement ab.|  
|[CToolBarCtrl::GetMaxSize](../Topic/CToolBarCtrl::GetMaxSize.md)|Ruft die Gesamtgröße aller sichtbaren Schaltflächen und Trennzeichen in der Symbolleiste ab.|  
|[CToolBarCtrl::GetMaxTextRows](../Topic/CToolBarCtrl::GetMaxTextRows.md)|Ruft die maximale Anzahl von Textzeilen ab, die auf einer Symbolleistenschaltfläche angezeigt werden.|  
|[CToolBarCtrl::GetMetrics](../Topic/CToolBarCtrl::GetMetrics.md)|Ruft die Metriken eines Symbolleisten\-Steuerelements ab.|  
|[CToolBarCtrl::GetPadding](../Topic/CToolBarCtrl::GetPadding.md)|Ruft die horizontale und vertikale Abstand des aktuellen Symbolleisten\-Steuerelements ab.|  
|[CToolBarCtrl::GetPressedImageList](../Topic/CToolBarCtrl::GetPressedImageList.md)|Ruft die Bildliste ab, der das aktuelle ToolBar\-Steuerelement verwendet, um Schaltflächen im gedrückten Zustand darzustellen.|  
|[CToolBarCtrl::GetRect](../Topic/CToolBarCtrl::GetRect.md)|Ruft das umschließende Rechteck für eine angegebene Symbolleisten\-Schaltfläche ab.|  
|[CToolBarCtrl::GetRows](../Topic/CToolBarCtrl::GetRows.md)|Ruft die Anzahl von Zeilen aus den Schaltflächen ab, die derzeit in der Symbolleiste angezeigt werden.|  
|[CToolBarCtrl::GetState](../Topic/CToolBarCtrl::GetState.md)|Ruft Informationen über den Zustand der angegebenen Schaltfläche in einem ToolBar\-Steuerelement, wie ab, ob es aktiviert, gedrückt oder überprüft wird.|  
|[CToolBarCtrl::GetString](../Topic/CToolBarCtrl::GetString.md)|Ruft eine Symbolleistenzeichenfolge ab.|  
|[CToolBarCtrl::GetStyle](../Topic/CToolBarCtrl::GetStyle.md)|Ruft die Stile derzeit für ein ToolBar\-Steuerelement ab.|  
|[CToolBarCtrl::GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md)|Ruft das Handle des ToolTip\-Steuerelements ggf. ab, mit dem ToolBar\-Steuerelement zugeordnet.|  
|[CToolBarCtrl::HideButton](../Topic/CToolBarCtrl::HideButton.md)|blendet oder zeigt die angegebene Schaltfläche in einem ToolBar\-Steuerelement.|  
|[CToolBarCtrl::HitTest](../Topic/CToolBarCtrl::HitTest.md)|Bestimmt, wo ein Punkt in einem ToolBar\-Steuerelement liegt.|  
|[CToolBarCtrl::Indeterminate](../Topic/CToolBarCtrl::Indeterminate.md)|Setzt oder freie Räume der unbestimmte \(graue\) Zustand der angegebenen Schaltfläche in einem ToolBar\-Steuerelement.|  
|[CToolBarCtrl::InsertButton](../Topic/CToolBarCtrl::InsertButton.md)|Fügt eine Schaltfläche in einem ToolBar\-Steuerelement ein.|  
|[CToolBarCtrl::InsertMarkHitTest](../Topic/CToolBarCtrl::InsertMarkHitTest.md)|Ruft die Einfügemarkeninformationen für einen Punkt in einer Symbolleiste ab.|  
|[CToolBarCtrl::IsButtonChecked](../Topic/CToolBarCtrl::IsButtonChecked.md)|Teilt mit, ob die angegebene Schaltfläche in einem ToolBar\-Steuerelement überprüft wird.|  
|[CToolBarCtrl::IsButtonEnabled](../Topic/CToolBarCtrl::IsButtonEnabled.md)|Teilt mit, ob die angegebene Schaltfläche in einem ToolBar\-Steuerelement aktiviert ist.|  
|[CToolBarCtrl::IsButtonHidden](../Topic/CToolBarCtrl::IsButtonHidden.md)|Teilt mit, ob die angegebene Schaltfläche in einem ToolBar\-Steuerelement ausgeblendet ist.|  
|[CToolBarCtrl::IsButtonHighlighted](../Topic/CToolBarCtrl::IsButtonHighlighted.md)|Überprüft den Hervorhebungszustand der Symbolleisten\-Schaltfläche.|  
|[CToolBarCtrl::IsButtonIndeterminate](../Topic/CToolBarCtrl::IsButtonIndeterminate.md)|Teilt mit, dass der Zustand der angegebenen Schaltfläche in einem ToolBar\-Steuerelement unbestimmt ist \(grau\).|  
|[CToolBarCtrl::IsButtonPressed](../Topic/CToolBarCtrl::IsButtonPressed.md)|Teilt mit, ob die angegebene Schaltfläche in einem ToolBar\-Steuerelement gedrückt wird.|  
|[CToolBarCtrl::LoadImages](../Topic/CToolBarCtrl::LoadImages.md)|Lastbitmaps in die Bildliste eines Symbolleisten\-Steuerelements.|  
|[CToolBarCtrl::MapAccelerator](../Topic/CToolBarCtrl::MapAccelerator.md)|Ordnet ein Zugriffstastenzeichen zu einer Symbolleistenschaltfläche zu.|  
|[CToolBarCtrl::MarkButton](../Topic/CToolBarCtrl::MarkButton.md)|Legt den Hervorhebungszustand einer angegebenen Schaltfläche in einem ToolBar\-Steuerelement fest.|  
|[CToolBarCtrl::MoveButton](../Topic/CToolBarCtrl::MoveButton.md)|Verschiebt eine Schaltfläche von einem Index auf andere.|  
|[CToolBarCtrl::PressButton](../Topic/CToolBarCtrl::PressButton.md)|Pressen oder Versionen die angegebene Schaltfläche in einem ToolBar\-Steuerelement.|  
|[CToolBarCtrl::ReplaceBitmap](../Topic/CToolBarCtrl::ReplaceBitmap.md)|Ersetzt die vorhandene Bitmap im aktuellen ToolBar\-Steuerelement durch eine neue Bitmap.|  
|[CToolBarCtrl::RestoreState](../Topic/CToolBarCtrl::RestoreState.md)|Stellt den Zustand des Symbolleisten\-Steuerelements wiederher.|  
|[CToolBarCtrl::SaveState](../Topic/CToolBarCtrl::SaveState.md)|Rettet den Zustand des Symbolleisten\-Steuerelements.|  
|[CToolBarCtrl::SetAnchorHighlight](../Topic/CToolBarCtrl::SetAnchorHighlight.md)|Legt die Anker\-Hervorhebungseinstellung für eine Symbolleiste fest.|  
|[CToolBarCtrl::SetBitmapSize](../Topic/CToolBarCtrl::SetBitmapSize.md)|Legt die Größe der zu einem ToolBar\-Steuerelement fest hinzugefügt werden Bitmapbilder.|  
|[CToolBarCtrl::SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)|Legt die Informationen für eine vorhandene Schaltfläche in einer Symbolleiste fest.|  
|[CToolBarCtrl::SetButtonSize](../Topic/CToolBarCtrl::SetButtonSize.md)|Legt die Größe der zu einem ToolBar\-Steuerelement fest hinzugefügt werden, Schaltflächen.|  
|[CToolBarCtrl::SetButtonStructSize](../Topic/CToolBarCtrl::SetButtonStructSize.md)|Gibt die Größe der `TBBUTTON`\-Struktur an.|  
|[CToolBarCtrl::SetButtonWidth](../Topic/CToolBarCtrl::SetButtonWidth.md)|Legt die minimalen und maximalen Schaltflächenbreiten im ToolBar\-Steuerelement fest.|  
|[CToolBarCtrl::SetCmdID](../Topic/CToolBarCtrl::SetCmdID.md)|Legt das dem fest Besitzerfenster gesendet werden Befehlskennzeichen, wenn die angegebene Schaltfläche gedrückt wird.|  
|[CToolBarCtrl::SetColorScheme](../Topic/CToolBarCtrl::SetColorScheme.md)|Legt das Farbschema des aktuellen Symbolleisten\-Steuerelements fest.|  
|[CToolBarCtrl::SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md)|Legt die Bildliste fest, der das ToolBar\-Steuerelement verwendet, um deaktivierte Schaltflächen anzuzeigen.|  
|[CToolBarCtrl::SetDrawTextFlags](../Topic/CToolBarCtrl::SetDrawTextFlags.md)|Legt die Flags in der Win32\-Funktion [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), die verwendet wird, um den Text im angegebenen Rechteck gezeichnet, formatiert entsprechend fest, wie die Flags festgelegt werden.|  
|[CToolBarCtrl::SetExtendedStyle](../Topic/CToolBarCtrl::SetExtendedStyle.md)|Legt die erweiterten Formate für ein ToolBar\-Steuerelement fest.|  
|[CToolBarCtrl::SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md)|Legt die Bildliste fest, der das ToolBar\-Steuerelement verwendet, um "heiße" Schaltflächen anzuzeigen.|  
|[CToolBarCtrl::SetHotItem](../Topic/CToolBarCtrl::SetHotItem.md)|Legt das hervorgehobene Element in einer Symbolleiste fest.|  
|[CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md)|Legt die Bildliste fest, der die Symbolleiste verwendet, um Schaltflächen anzuzeigen, die im Standardzustand sind.|  
|[CToolBarCtrl::SetIndent](../Topic/CToolBarCtrl::SetIndent.md)|Legt den Einzug für die erste Schaltfläche in einem ToolBar\-Steuerelement fest.|  
|[CToolBarCtrl::SetInsertMark](../Topic/CToolBarCtrl::SetInsertMark.md)|Legt die aktuelle Einfügemarke für die Symbolleiste fest.|  
|[CToolBarCtrl::SetInsertMarkColor](../Topic/CToolBarCtrl::SetInsertMarkColor.md)|Legt die Farbe fest, die verwendet wird, um die Einfügemarke für die Symbolleiste zu zeichnen.|  
|[CToolBarCtrl::SetMaxTextRows](../Topic/CToolBarCtrl::SetMaxTextRows.md)|Legt die maximale Anzahl von Textzeilen fest, die auf einer Symbolleistenschaltfläche angezeigt werden.|  
|[CToolBarCtrl::SetMetrics](../Topic/CToolBarCtrl::SetMetrics.md)|Legt die Eigenschaften eines Symbolleisten\-Steuerelements fest.|  
|[CToolBarCtrl::SetOwner](../Topic/CToolBarCtrl::SetOwner.md)|Legt das Fenster, um Benachrichtigungsmeldungen vom ToolBar\-Steuerelement zu empfangen.|  
|[CToolBarCtrl::SetPadding](../Topic/CToolBarCtrl::SetPadding.md)|Legt die horizontale und vertikale Abstand des aktuellen Symbolleisten\-Steuerelements fest.|  
|[CToolBarCtrl::SetPressedImageList](../Topic/CToolBarCtrl::SetPressedImageList.md)|Legt die Bildliste fest, der das aktuelle ToolBar\-Steuerelement verwendet, um Schaltflächen im gedrückten Zustand darzustellen.|  
|[CToolBarCtrl::SetRows](../Topic/CToolBarCtrl::SetRows.md)|Legt die Anzahl von Zeilen aus den Schaltflächen fest, die auf der Symbolleiste angezeigt werden.|  
|[CToolBarCtrl::SetState](../Topic/CToolBarCtrl::SetState.md)|Legt den Zustand für die angegebene Schaltfläche in einem ToolBar\-Steuerelement fest.|  
|[CToolBarCtrl::SetStyle](../Topic/CToolBarCtrl::SetStyle.md)|Legt die Stile für ein ToolBar\-Steuerelement fest.|  
|[CToolBarCtrl::SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md)|Ordnet ein QuickInfo\-Steuerelement mit dem ToolBar\-Steuerelement zu.|  
|[CToolBarCtrl::SetWindowTheme](../Topic/CToolBarCtrl::SetWindowTheme.md)|Legt den visuellen Stil eines Symbolleisten\-Steuerelements fest.|  
  
## Hinweise  
 Dieses Steuerelement \(und daher die `CToolBarCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Eine Windows\-Symbolleistengemeinsame allgemeinen ToolTip\-Steuerelement ist ein rechteckiges untergeordnetes Fenster, das eine oder mehrere Schaltflächen enthält.  Diese Schaltflächen können ein Bitmapbild, eine Zeichenfolge oder beide anzeigen.  Wenn der Benutzer eine Schaltfläche auswählt, sendet sie eine Befehlsmeldung auf Besitzerfenster der Symbolleiste.  In der Regel entsprechen die Schaltflächen in einer Symbolleiste an Elementen im Menü der Anwendung; Sie stellen eine direktere Möglichkeit, sodass der Benutzer auf die Befehle einer Anwendung zugreift.  
  
 `CToolBarCtrl`\-Objekte enthalten einige wichtige interne Datenstrukturen: eine Liste von Schaltflächensymbolbitmaps oder Bildliste, Liste von Schaltflächenbezeichnungszeichenfolgen und Liste von `TBBUTTON`\-Strukturen, die ein Bild zuordnen und\/oder Zeichenfolge mit der Position, formatieren, angeben und von Befehls\-ID der Schaltfläche.  Jedes der Elemente dieser Datenstrukturen wird durch einen nullbasierten Index bezeichnet.  Bevor Sie ein Objekt `CToolBarCtrl` verwenden können, müssen Sie diese Datenstrukturen installieren.  Die Liste der Zeichenfolgen für Schaltflächenbezeichnungen kann nur verwendet werden, Sie können Zeichenfolgen nicht von der Symbolleiste abrufen.  
  
 Um ein `CToolBarCtrl`\-Objekt zu verwenden, führen Sie in der Regel folgende Schritte aus:  
  
1.  Erstellen Sie das `CToolBarCtrl`\-Objekt.  
  
2.  Rufen Sie [Erstellen Sie](../Topic/CToolBarCtrl::Create.md) auf, um die Windows\-Symbolleistengemeinsame allgemeinen ToolTip\-Steuerelement zu erstellen und diese dem `CToolBarCtrl`\-Objekt anzufügen.  Geben Sie das Format der Symbolleiste an, indem Sie Formate, wie **TBSTYLE\_TRANSPARENT** für eine transparente Symbolleiste oder **TBSTYLE\_DROPDOWN** für eine Symbolleiste verwenden, die Dropdown\-Formatschaltflächen unterstützt.  
  
3.  Bestimmen Sie, wie Sie die Schaltflächen auf der Symbolleiste angezeigt werden soll:  
  
    -   Um Bitmapbilder für Schaltflächen zu verwenden, fügen Sie die Schaltflächenbitmaps der Symbolleiste hinzu [AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md) indem Sie aufrufen.  
  
    -   Um die Bilder zu verwenden, die von einer Bildliste für Schaltflächen angezeigt werden, geben Sie die Bildliste an, indem Sie [SetImageList](../Topic/CToolBarCtrl::SetImageList.md)[SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md) oder [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md) aufrufen.  
  
    -   Um Zeichenfolgenbezeichnungen für Schaltflächen zu verwenden, fügen Sie die Zeichenfolgen der Symbolleiste hinzu indem Sie [AddString](../Topic/CToolBarCtrl::AddString.md) und\/oder [AddStrings](../Topic/CToolBarCtrl::AddStrings.md) aufrufen.  
  
4.  Fügen Sie Schaltflächenstrukturen der Symbolleiste hinzu, indem Sie [AddButtons](../Topic/CToolBarCtrl::AddButtons.md) aufrufen.  
  
5.  Wenn Sie QuickInfos für eine Symbolleisten\-Schaltfläche in einem Besitzerfenster möchten, das nicht `CFrameWnd` ist, müssen Sie die **TTN\_NEEDTEXT** Meldungen im Besitzerfenster der Symbolleiste bearbeiten, wie in [Behandlungs\-QuickInfo\-Benachrichtigungen](../../mfc/handling-tool-tip-notifications.md) beschrieben.  Wenn das übergeordnete Fenster der Symbolleiste von `CFrameWnd` abgeleitet ist, werden QuickInfos ohne zusätzlichen Aufwand von Ihnen angezeigt, da `CFrameWnd` einen Standardhandler bereitstellt.  
  
6.  Wenn Sie den Benutzern ermöglichen möchten, die Symbolleiste anzupassen, Handleanpassungsbenachrichtigungsmeldungen im Besitzerfenster, wie in [Behandlungs\-Anpassungs\-Benachrichtigungen](../../mfc/handling-customization-notifications.md) beschrieben.  
  
 Sie können [SaveState](../Topic/CToolBarCtrl::SaveState.md) verwenden, um den aktuellen Zustand eines Symbolleisten\-Steuerelements in der Registrierung und in [RestoreState](../Topic/CToolBarCtrl::RestoreState.md) zu speichern, um den Zustand auf Grundlage der Informationen wiederherzustellen, die zuvor in der Registrierung gespeichert werden.  Zusätzlich zu den Symbolleistenzustand zwischen Verwendungsmöglichkeiten von der Anwendung in der Regel speichern, Speicher der Anwendungen der Zustand, bevor der Benutzer beginnt, Symbolleiste Anpassen, falls der Benutzer später die Symbolleiste in ihren ursprünglichen Zustand wiederherstellen möchte.  
  
## Unterstützung für Internet Explorer 4,0 und höher  
 Um die Funktionalität unterstützen, die in Internet Explorer eingegeben wird, stellt Version 4.0 und höher, MFC Bildlistenunterstützung und die transparente und Ebenenformate für Symbolleisten\-Steuerelemente bereit.  
  
 Eine transparente Symbolleiste ermöglicht den Clients unter der Symbolleiste zum Anzeigen von.  Um eine transparente Symbolleiste zu erstellen, verwenden Sie **TBSTYLE\_FLAT** und **TBSTYLE\_TRANSPARENT** Stile.  Transparente Symbolleisten kennzeichnen das Hottracking; das heißt, wenn der Mauszeiger über eine aktive Schaltfläche auf der Symbolleiste bewegt wird, ändert sich die Darstellung der Schaltfläche.  Die Symbolleisten, die nur mit dem **TBSTYLE\_FLAT** Format erstellt werden, enthalten Schaltflächen, die nicht transparent sind.  
  
 Bildlistenunterstützung können einem Steuerelement größere Flexibilität Standardverhalten, heiße Bilder und deaktivierte Bilder zu.  Verwenden Sie [GetImageList](../Topic/CToolBarCtrl::GetImageList.md), [GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md) und [GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md) mit der transparenten Symbolleiste, um das Bild gemäß seinem Zustands bearbeiten:  
  
 Weitere Informationen zur Verwendung von `CToolBarCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CToolBarCtrl](../../mfc/using-ctoolbarctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [MFC Sampling CMNCTRL1](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel MFCIE](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)