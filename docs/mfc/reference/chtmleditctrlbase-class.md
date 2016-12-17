---
title: "CHtmlEditCtrlBase Class"
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
  - "CHtmlEditCtrlBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrlBase class"
ms.assetid: e0cc74b4-8320-4570-b673-16c03d2ae266
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditCtrlBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine HTML\-Bearbeitungskomponente dar.  
  
## Syntax  
  
```  
  
template < class   
T  
 > class CHtmlEditCtrlBase  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHtmlEditCtrlBase::AddToGlyphTable](../Topic/CHtmlEditCtrlBase::AddToGlyphTable.md)|Fügt einen Eintrag dem Namensliste hinzu, das Bilder angibt, das für bestimmte Tags im Entwurfsmodus anzuzeigen.|  
|[CHtmlEditCtrlBase::Bold](../Topic/CHtmlEditCtrlBase::Bold.md)|Schaltet den Zustand "Fett" für den ausgewählten Text um.|  
|[CHtmlEditCtrlBase::Button](../Topic/CHtmlEditCtrlBase::Button.md)|Überschreibt ein Schaltflächen\-Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::CheckBox](../Topic/CHtmlEditCtrlBase::CheckBox.md)|Überschreibt ein Kontrollkästchen\-Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::ClearSelection](../Topic/CHtmlEditCtrlBase::ClearSelection.md)|Löscht die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::Copy](../Topic/CHtmlEditCtrlBase::Copy.md)|Kopiert die aktuelle Auswahl in die Zwischenablage.|  
|[CHtmlEditCtrlBase::Cut](../Topic/CHtmlEditCtrlBase::Cut.md)|Kopiert die aktuelle Auswahl in die Zwischenablage und entfernt sie dann.|  
|[CHtmlEditCtrlBase::Delete](../Topic/CHtmlEditCtrlBase::Delete.md)|Löscht die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::DropDownBox](../Topic/CHtmlEditCtrlBase::DropDownBox.md)|Überschreibt ein Dropdown\-Auswahlsteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::EmptyGlyphTable](../Topic/CHtmlEditCtrlBase::EmptyGlyphTable.md)|Entfernt alle Einträge aus der Namensliste, die alle Bilder ausblendet, die für Tags im Entwurfsmodus angezeigt werden.|  
|[CHtmlEditCtrlBase::ExecCommand](../Topic/CHtmlEditCtrlBase::ExecCommand.md)|Führt einen Befehl aus.|  
|[CHtmlEditCtrlBase::Font](../Topic/CHtmlEditCtrlBase::Font.md)|Öffnet ein Schriftartdialogfeld, um den Benutzer zu ermöglichen, die Textfarbe, die Schriftart und Schriftgrad der aktuellen Auswahl zu ändern.|  
|[CHtmlEditCtrlBase::GetAbsolutePosition](../Topic/CHtmlEditCtrlBase::GetAbsolutePosition.md)|Gibt zurück, ob Positionseigenschaft eines Elements ist "Absolute".|  
|[CHtmlEditCtrlBase::GetBackColor](../Topic/CHtmlEditCtrlBase::GetBackColor.md)|Ruft die Hintergrundfarbe der aktuellen Auswahl ab.|  
|[CHtmlEditCtrlBase::GetBlockFormat](../Topic/CHtmlEditCtrlBase::GetBlockFormat.md)|Ruft das aktuelle Blockformattag ab.|  
|[CHtmlEditCtrlBase::GetBlockFormatNames](../Topic/CHtmlEditCtrlBase::GetBlockFormatNames.md)|Ruft die Zeichenfolgen entsprechend den verfügbaren Blockformattags ab.|  
|[CHtmlEditCtrlBase::GetBookMark](../Topic/CHtmlEditCtrlBase::GetBookMark.md)|Ruft den Namen eines Lesezeichenankers ab.|  
|[CHtmlEditCtrlBase::GetDocument](../Topic/CHtmlEditCtrlBase::GetDocument.md)|Ruft das Dokumentobjekt ab.|  
|[CHtmlEditCtrlBase::GetDocumentHTML](../Topic/CHtmlEditCtrlBase::GetDocumentHTML.md)|Ruft das HTML des aktuellen Dokuments ab.|  
|[CHtmlEditCtrlBase::GetDocumentTitle](../Topic/CHtmlEditCtrlBase::GetDocumentTitle.md)|Ruft den Namen des Dokuments ab.|  
|[CHtmlEditCtrlBase::GetEvent](../Topic/CHtmlEditCtrlBase::GetEvent.md)|Ruft einen Schnittstellenzeiger für das Ereignisobjekt ab, das die Informationen enthält, die den letzten Ereignis relevant sind.|  
|[CHtmlEditCtrlBase::GetEventSrcElement](../Topic/CHtmlEditCtrlBase::GetEventSrcElement.md)|Ruft das Objekt ab, das das Ereignis ausgelöst hat.|  
|[CHtmlEditCtrlBase::GetFontFace](../Topic/CHtmlEditCtrlBase::GetFontFace.md)|Ruft den Schriftartnamen für die aktuelle Auswahl ab.|  
|[CHtmlEditCtrlBase::GetFontSize](../Topic/CHtmlEditCtrlBase::GetFontSize.md)|Ruft den Schriftgrad für die aktuelle Auswahl ab.|  
|[CHtmlEditCtrlBase::GetForeColor](../Topic/CHtmlEditCtrlBase::GetForeColor.md)|Ruft die Farbe des Vordergrunds \(Text\) der aktuellen Auswahl ab.|  
|[CHtmlEditCtrlBase::GetFrameZone](../Topic/CHtmlEditCtrlBase::GetFrameZone.md)|Gibt die Sicherheitszone der aktuellen Seite im Webbrowser zurück.|  
|[CHtmlEditCtrlBase::GetIsDirty](../Topic/CHtmlEditCtrlBase::GetIsDirty.md)|Gibt an, ob das HTML\-Dokument geändert hat.|  
|[CHtmlEditCtrlBase::GetShowAlignedSiteTags](../Topic/CHtmlEditCtrlBase::GetShowAlignedSiteTags.md)|Gibt zurück, ob ein Symbol für alle Elemente angezeigt wird, die eine **styleFloat**\-Eigenschaft verfügen.|  
|[CHtmlEditCtrlBase::GetShowAllTags](../Topic/CHtmlEditCtrlBase::GetShowAllTags.md)|Gibt zurück, ob das web browser Symbole angezeigt werden, um den Speicherort sämtlicher Tags in einem Dokument anzuzeigen.|  
|[CHtmlEditCtrlBase::GetShowAreaTags](../Topic/CHtmlEditCtrlBase::GetShowAreaTags.md)|Ruft ab, ob das web Webbrowsers ein Symbol für Bereichstags anzeigt.|  
|[CHtmlEditCtrlBase::GetShowBRTags](../Topic/CHtmlEditCtrlBase::GetShowBRTags.md)|Ruft ab, ob das web Webbrowsers ein Symbol für Brtags anzeigt.|  
|[CHtmlEditCtrlBase::GetShowCommentTags](../Topic/CHtmlEditCtrlBase::GetShowCommentTags.md)|Ruft ab, ob das web Webbrowsers ein Symbol für Kommentartags anzeigt.|  
|[CHtmlEditCtrlBase::GetShowMiscTags](../Topic/CHtmlEditCtrlBase::GetShowMiscTags.md)|Ruft ab, ob das web werden alle Tags angezeigt, die in Microsoft Internet Explorer 4,0 angezeigt werden.|  
|[CHtmlEditCtrlBase::GetShowScriptTags](../Topic/CHtmlEditCtrlBase::GetShowScriptTags.md)|Ruft ab, ob das web Webbrowsers ein Symbol für alle Skripttags anzeigt.|  
|[CHtmlEditCtrlBase::GetShowStyleTags](../Topic/CHtmlEditCtrlBase::GetShowStyleTags.md)|Ruft ab, ob das web Webbrowsers ein Symbol für alle Formattags anzeigt.|  
|[CHtmlEditCtrlBase::GetShowUnknownTags](../Topic/CHtmlEditCtrlBase::GetShowUnknownTags.md)|Ruft ab, ob das web Webbrowsers ein Symbol für alle unbekannten Tags angezeigt.|  
|[CHtmlEditCtrlBase::HorizontalLine](../Topic/CHtmlEditCtrlBase::HorizontalLine.md)|Überschreibt eine horizontale Linie auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::HyperLink](../Topic/CHtmlEditCtrlBase::HyperLink.md)|Fügt einen Link auf der aktuellen Auswahl ein.|  
|[CHtmlEditCtrlBase::IE50Paste](../Topic/CHtmlEditCtrlBase::IE50Paste.md)|Führt einen Einfügevorgang aus, der mit Microsoft Internet Explorer 5 kompatibel ist.|  
|[CHtmlEditCtrlBase::Iframe](../Topic/CHtmlEditCtrlBase::Iframe.md)|Überschreibt inline Rahmen in der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Image](../Topic/CHtmlEditCtrlBase::Image.md)|Überschreibt ein Bild auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Indent](../Topic/CHtmlEditCtrlBase::Indent.md)|Erhöht den Einzug des markierten Texts durch ein Einzugsinkrement.|  
|[CHtmlEditCtrlBase::InsFieldSet](../Topic/CHtmlEditCtrlBase::InsFieldSet.md)|Überschreibt ein Feld auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputButton](../Topic/CHtmlEditCtrlBase::InsInputButton.md)|Überschreibt ein Schaltflächen\-Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputHidden](../Topic/CHtmlEditCtrlBase::InsInputHidden.md)|Fügt ein ausgeblendetes Steuerelement auf der aktuellen Auswahl ein.|  
|[CHtmlEditCtrlBase::InsInputImage](../Topic/CHtmlEditCtrlBase::InsInputImage.md)|Überschreibt Bildsteuerung auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputPassword](../Topic/CHtmlEditCtrlBase::InsInputPassword.md)|Überschreibt ein Kennwortsteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputReset](../Topic/CHtmlEditCtrlBase::InsInputReset.md)|Überschreibt ein Rücksetzungssteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputSubmit](../Topic/CHtmlEditCtrlBase::InsInputSubmit.md)|Überschreibt ein sendenssteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputUpload](../Topic/CHtmlEditCtrlBase::InsInputUpload.md)|Überschreibt ein Dateiuploadsteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Is1DElement](../Topic/CHtmlEditCtrlBase::Is1DElement.md)|Bestimmt, ob ein Element statisch positioniert wird.|  
|[CHtmlEditCtrlBase::Is2DElement](../Topic/CHtmlEditCtrlBase::Is2DElement.md)|Bestimmt, ob ein Element absolut positioniert wird.|  
|[CHtmlEditCtrlBase::Italic](../Topic/CHtmlEditCtrlBase::Italic.md)|Schaltet die aktuelle Auswahl zwischen Kursiv und nonitalic um.|  
|[CHtmlEditCtrlBase::JustifyCenter](../Topic/CHtmlEditCtrlBase::JustifyCenter.md)|Zentriert den Style\-Block, in dem die aktuelle Auswahl ist.|  
|[CHtmlEditCtrlBase::JustifyLeft](../Topic/CHtmlEditCtrlBase::JustifyLeft.md)|Belassene\-schließt den Style\-Block aus, in dem die aktuelle Auswahl ist.|  
|[CHtmlEditCtrlBase::JustifyRight](../Topic/CHtmlEditCtrlBase::JustifyRight.md)|Recht\-schließt den Style\-Block aus, in dem die aktuelle Auswahl ist.|  
|[CHtmlEditCtrlBase::ListBox](../Topic/CHtmlEditCtrlBase::ListBox.md)|Überschreibt ein Listenfeld\-Auswahlsteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Marquee](../Topic/CHtmlEditCtrlBase::Marquee.md)|Überschreibt eine leere Laufschrift auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::NewDocument](../Topic/CHtmlEditCtrlBase::NewDocument.md)|Erstellt ein neues Dokument.|  
|[CHtmlEditCtrlBase::OrderList](../Topic/CHtmlEditCtrlBase::OrderList.md)|Schaltet die aktuelle Auswahl zwischen einer sortierten Liste und einem normalen Style\-Block um.|  
|[CHtmlEditCtrlBase::Outdent](../Topic/CHtmlEditCtrlBase::Outdent.md)|nimmt durch ein Inkrement der Einzug des Formatblocks, in dem die aktuelle Auswahl ist.|  
|[CHtmlEditCtrlBase::Paragraph](../Topic/CHtmlEditCtrlBase::Paragraph.md)|Überschreibt einen Zeilenumbruch auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Paste](../Topic/CHtmlEditCtrlBase::Paste.md)|Überschreibt den Inhalt der Zwischenablage auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::PrintDocument](../Topic/CHtmlEditCtrlBase::PrintDocument.md)|Druckt das aktuelle Dokument.|  
|[CHtmlEditCtrlBase::PrintPreview](../Topic/CHtmlEditCtrlBase::PrintPreview.md)|Öffnet das Fenster "Seitenansicht" für das aktuelle Dokument entweder mithilfe der standardmäßigen Seitenansichtsvorlage oder einer benutzerdefinierten Vorlage.|  
|[CHtmlEditCtrlBase::QueryStatus](../Topic/CHtmlEditCtrlBase::QueryStatus.md)|Rufen Sie diese Methode auf, um den Status von Befehlen abzufragen.|  
|[CHtmlEditCtrlBase::RadioButton](../Topic/CHtmlEditCtrlBase::RadioButton.md)|Überschreibt eine Funksteuerung auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::RefreshDocument](../Topic/CHtmlEditCtrlBase::RefreshDocument.md)|Aktualisiert das aktuelle Dokument.|  
|[CHtmlEditCtrlBase::RemoveFormat](../Topic/CHtmlEditCtrlBase::RemoveFormat.md)|Entfernt die Formatierungstags von der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::SaveAs](../Topic/CHtmlEditCtrlBase::SaveAs.md)|Speichert die aktuelle Webseite in einer Datei.|  
|[CHtmlEditCtrlBase::SelectAll](../Topic/CHtmlEditCtrlBase::SelectAll.md)|Markiert das gesamte Dokument.|  
|[CHtmlEditCtrlBase::Set2DPosition](../Topic/CHtmlEditCtrlBase::Set2DPosition.md)|Ermöglicht die absolut positioniert durch Ziehen verschoben werden Elemente.|  
|[CHtmlEditCtrlBase::SetAbsolutePosition](../Topic/CHtmlEditCtrlBase::SetAbsolutePosition.md)|Legt Positionseigenschaft "Absolute" eines Elements oder "statisches" fest.|  
|[CHtmlEditCtrlBase::SetAtomicSelection](../Topic/CHtmlEditCtrlBase::SetAtomicSelection.md)|Festgelegter unteilbarer Auswahlmodus.|  
|[CHtmlEditCtrlBase::SetAutoURLDetectMode](../Topic/CHtmlEditCtrlBase::SetAutoURLDetectMode.md)|Automatische Erkennung der URL Drehungen aktiviert und deaktiviert werden.|  
|[CHtmlEditCtrlBase::SetBackColor](../Topic/CHtmlEditCtrlBase::SetBackColor.md)|Legt die Hintergrundfarbe der aktuellen Auswahl fest.|  
|[CHtmlEditCtrlBase::SetBlockFormat](../Topic/CHtmlEditCtrlBase::SetBlockFormat.md)|Legt das aktuelle Blockformattag fest.|  
|[CHtmlEditCtrlBase::SetBookMark](../Topic/CHtmlEditCtrlBase::SetBookMark.md)|Stellt einen Lesezeichenanker für die aktuelle Auswahl oder die Einfügemarke erstellt.|  
|[CHtmlEditCtrlBase::SetCSSEditingLevel](../Topic/CHtmlEditCtrlBase::SetCSSEditingLevel.md)|Wählt aus, die CSS\-Ebene \(CSS1 oder CSS2\) der Editor unterstützt, sofern vorhanden.|  
|[CHtmlEditCtrlBase::SetDefaultComposeSettings](../Topic/CHtmlEditCtrlBase::SetDefaultComposeSettings.md)|Rufen Sie diese Methode auf, um den Standardeinstellung festlegen zusammensetzt Einstellungen.|  
|[CHtmlEditCtrlBase::SetDesignMode](../Topic/CHtmlEditCtrlBase::SetDesignMode.md)|Bühnenbildmodus.|  
|[CHtmlEditCtrlBase::SetDisableEditFocusUI](../Topic/CHtmlEditCtrlBase::SetDisableEditFocusUI.md)|Deaktiviert den schraffierten Rahmen und die Handles um ein Element, das Bearbeitungsfokus verfügt.|  
|[CHtmlEditCtrlBase::SetDocumentHTML](../Topic/CHtmlEditCtrlBase::SetDocumentHTML.md)|Legt das HTML des aktuellen Dokuments fest.|  
|[CHtmlEditCtrlBase::SetFontFace](../Topic/CHtmlEditCtrlBase::SetFontFace.md)|Legt die Schriftart für die aktuelle Auswahl fest.|  
|[CHtmlEditCtrlBase::SetFontSize](../Topic/CHtmlEditCtrlBase::SetFontSize.md)|Legt den Schriftgrad für die aktuelle Auswahl fest.|  
|[CHtmlEditCtrlBase::SetForeColor](../Topic/CHtmlEditCtrlBase::SetForeColor.md)|Legt die Farbe des Vordergrunds \(Text\) der aktuellen Auswahl fest.|  
|[CHtmlEditCtrlBase::SetIE5PasteMode](../Topic/CHtmlEditCtrlBase::SetIE5PasteMode.md)|Legt den Einfügevorgang fest, um mit Microsoft Internet Explorer 5 kompatibel ist.|  
|[CHtmlEditCtrlBase::SetLiveResize](../Topic/CHtmlEditCtrlBase::SetLiveResize.md)|Veranlasst das web browser, die Darstellung eines Elements während einer Größenanpassung oder eines Vorgangs beweglichen kontinuierlich zu aktualisieren.|  
|[CHtmlEditCtrlBase::SetMultiSelect](../Topic/CHtmlEditCtrlBase::SetMultiSelect.md)|Lässt Mehrfachauswahl.|  
|[CHtmlEditCtrlBase::SetOverrideCursor](../Topic/CHtmlEditCtrlBase::SetOverrideCursor.md)|Beherrscht das web werden nie, um den Mauszeiger zu ändern.|  
|[CHtmlEditCtrlBase::SetOverwriteMode](../Topic/CHtmlEditCtrlBase::SetOverwriteMode.md)|Schaltet den TextEintrag Modus zwischen Einfüge\- und überschreibt.|  
|[CHtmlEditCtrlBase::SetRespectVisInDesign](../Topic/CHtmlEditCtrlBase::SetRespectVisInDesign.md)|Blendet nicht sichtbare Elemente im Entwurfsmodus.|  
|[CHtmlEditCtrlBase::SetShowAlignedSiteTags](../Topic/CHtmlEditCtrlBase::SetShowAlignedSiteTags.md)|Zeigt ein Symbol für alle Elemente an, die eine **styleFloat**\-Eigenschaft verfügen.|  
|[CHtmlEditCtrlBase::SetShowAllTags](../Topic/CHtmlEditCtrlBase::SetShowAllTags.md)|Zeigt Symbole an, um den Speicherort sämtlicher Tags in einem Dokument anzuzeigen.|  
|[CHtmlEditCtrlBase::SetShowAreaTags](../Topic/CHtmlEditCtrlBase::SetShowAreaTags.md)|Zeigt ein Symbol für alle Bereichstags an.|  
|[CHtmlEditCtrlBase::SetShowBRTags](../Topic/CHtmlEditCtrlBase::SetShowBRTags.md)|Zeigt ein Symbol für alle Brtags an.|  
|[CHtmlEditCtrlBase::SetShowCommentTags](../Topic/CHtmlEditCtrlBase::SetShowCommentTags.md)|Zeigt ein Symbol für alle Kommentartags an.|  
|[CHtmlEditCtrlBase::SetShowMiscTags](../Topic/CHtmlEditCtrlBase::SetShowMiscTags.md)|Zeigt alle Tags an, die in Microsoft Internet Explorer 4,0 angezeigt werden.|  
|[CHtmlEditCtrlBase::SetShowScriptTags](../Topic/CHtmlEditCtrlBase::SetShowScriptTags.md)|Zeigt ein Symbol für alle Skripttags an.|  
|[CHtmlEditCtrlBase::SetShowStyleTags](../Topic/CHtmlEditCtrlBase::SetShowStyleTags.md)|Zeigt ein Symbol für alle Formattags an.|  
|[CHtmlEditCtrlBase::SetShowUnknownTags](../Topic/CHtmlEditCtrlBase::SetShowUnknownTags.md)|Zeigt ein Symbol für alle unbekannten Tags an.|  
|[CHtmlEditCtrlBase::TextArea](../Topic/CHtmlEditCtrlBase::TextArea.md)|Überschreibt ein mehrzeiliges Texteingabesteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::TextBox](../Topic/CHtmlEditCtrlBase::TextBox.md)|Überschreibt ein Text\-Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::UnBookmark](../Topic/CHtmlEditCtrlBase::UnBookmark.md)|Entfernt alle Lesezeichen aus der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Underline](../Topic/CHtmlEditCtrlBase::Underline.md)|Schaltet die aktuelle Auswahl unterstrichen oder nicht um unterstrichen.|  
|[CHtmlEditCtrlBase::Unlink](../Topic/CHtmlEditCtrlBase::Unlink.md)|Entfernt einen Link von der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::UnorderList](../Topic/CHtmlEditCtrlBase::UnorderList.md)|Schaltet die aktuelle Auswahl zwischen einer sortierten Liste und einem normalen Style\-Block um.|  
  
#### Parameter  
 `T`  
 Der Name der abgeleiteten Klasse.  
  
## Hinweise  
 **CHtmlEditCtrlBase**  enthält Memberfunktionen für die das HTML\-Bearbeitungsbefehle eines Webbrowsers, wie [Fett](../Topic/CHtmlEditCtrlBase::Bold.md) bereit.  \(Alternativ, können Sie [ExecCommand](../Topic/CHtmlEditCtrlBase::ExecCommand.md) aufrufen, um den Befehl auszuführen **IDM\_BOLD** .\)  
  
 **CHtmlEditCtrlBase**  wird nicht dazu, die eigenständig zu kommunizieren.  Es wurde entwickelt, um eine Basisklasse für abgeleitete Klassen zu sein, die die HTML\-Bearbeitungsfunktionalität eines Webbrowsers verfügbar machen \(siehe [CHtmlEditCtrl](../../mfc/reference/chtmleditctrl-class.md) und [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)\).  
  
## Vererbungshierarchie  
 `CHtmlEditCtrlBase`  
  
## Anforderungen  
 **Header:** afxhtml.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [HTMLEdit\-Beispiel](../../top/visual-cpp-samples.md)