---
title: Klasse CHtmlEditCtrlBase | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrlBase
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrlBase class
ms.assetid: e0cc74b4-8320-4570-b673-16c03d2ae266
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e5541025653cca908d5d0c7666a434aa3f81ab5b
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditctrlbase-class"></a>CHtmlEditCtrlBase-Klasse
Stellt eine HTML-Bearbeitungskomponente dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T> class CHtmlEditCtrlBase  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditCtrlBase::AddToGlyphTable](#addtoglyphtable)|Fügt einen Eintrag in die Symbol-Tabelle, die für bestimmte Tags im Entwurfsmodus anzuzeigenden Bilder angibt.|  
|[CHtmlEditCtrlBase::Bold](#bold)|Blendet die fett formatiert den markierten Text.|  
|[CHtmlEditCtrlBase::Button](#button)|Überschreibt ein Button-Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::CheckBox](#checkbox)|Wird ein Kontrollkästchen-Steuerelement für die aktuelle Auswahl überschrieben.|  
|[CHtmlEditCtrlBase::ClearSelection](#clearselection)|Löscht die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::Copy](#copy)|Kopiert die aktuelle Auswahl in die Zwischenablage.|  
|[CHtmlEditCtrlBase::Cut](#cut)|Kopiert die aktuelle Auswahl in die Zwischenablage und löscht sie dann.|  
|[CHtmlEditCtrlBase::Delete](#delete)|Löscht die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::DropDownBox](#dropdownbox)|Überschreibt eine Dropdown-Liste-Steuerelement für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::EmptyGlyphTable](#emptyglyphtable)|Entfernt alle Einträge aus der Tabelle Symbol, alle Bilder für Tags im Entwurfsmodus angezeigt Blendet.|  
|[CHtmlEditCtrlBase::ExecCommand](#execcommand)|Führt einen Befehl aus.|  
|[CHtmlEditCtrlBase::Font](#font)|Öffnet eine Schriftart (Dialogfeld), um dem Benutzer das Ändern der Farbe, Schriftart und Schriftgrad der aktuellen Auswahl zu aktivieren.|  
|[CHtmlEditCtrlBase::GetAbsolutePosition](#getabsoluteposition)|Gibt zurück, ob ein Element Position-Eigenschaft "absolute".|  
|[CHtmlEditCtrlBase::GetBackColor](#getbackcolor)|Ruft die Hintergrundfarbe der aktuellen Auswahl ab.|  
|[CHtmlEditCtrlBase::GetBlockFormat](#getblockformat)|Ruft den aktuellen Block Formattag ab.|  
|[CHtmlEditCtrlBase::GetBlockFormatNames](#getblockformatnames)|Ruft die Zeichenfolgen für die verfügbaren Block Format-Tags ab.|  
|[CHtmlEditCtrlBase::GetBookMark](#getbookmark)|Ruft den Namen der als Lesezeichen Anker dargestellt.|  
|[CHtmlEditCtrlBase::GetDocument](#getdocument)|Ruft das Document-Objekt ab.|  
|[CHtmlEditCtrlBase::GetDocumentHTML](#getdocumenthtml)|Ruft den HTML-Code des aktuellen Dokuments ab.|  
|[CHtmlEditCtrlBase::GetDocumentTitle](#getdocumenttitle)|Ruft den Titel des Dokuments ab.|  
|[CHtmlEditCtrlBase::GetEvent](#getevent)|Ruft einen Schnittstellenzeiger auf das Ereignisobjekt, das Informationen über das neueste Ereignis enthält.|  
|[CHtmlEditCtrlBase::GetEventSrcElement](#geteventsrcelement)|Ruft das Objekt, das das Ereignis ausgelöst hat.|  
|[CHtmlEditCtrlBase::GetFontFace](#getfontface)|Ruft den Schriftartnamen für die aktuelle Auswahl ab.|  
|[CHtmlEditCtrlBase::GetFontSize](#getfontsize)|Ruft den Schriftgrad für die aktuelle Auswahl ab.|  
|[CHtmlEditCtrlBase::GetForeColor](#getforecolor)|Ruft die Vordergrundfarbe (Text), der die aktuelle Auswahl ab.|  
|[CHtmlEditCtrlBase::GetFrameZone](#getframezone)|Gibt die Sicherheitszone der aktuellen Seite im Webbrowser an.|  
|[CHtmlEditCtrlBase::GetIsDirty](#getisdirty)|Gibt an, ob das HTML-Dokument geändert wurde.|  
|[CHtmlEditCtrlBase::GetShowAlignedSiteTags](#getshowalignedsitetags)|Gibt zurück, ob ein Symbol für alle Elemente angezeigt wird, die über eine **StyleFloat** Eigenschaft.|  
|[CHtmlEditCtrlBase::GetShowAllTags](#getshowalltags)|Gibt zurück, ob der WebBrowser Symbole an den Speicherort der alle Tags in einem Dokument angezeigt.|  
|[CHtmlEditCtrlBase::GetShowAreaTags](#getshowareatags)|Ruft ab, ob der WebBrowser ein Symbol für Tags Bereich angezeigt.|  
|[CHtmlEditCtrlBase::GetShowBRTags](#getshowbrtags)|Ruft ab, ob der WebBrowser ein Symbol für Br-Tags angezeigt.|  
|[CHtmlEditCtrlBase::GetShowCommentTags](#getshowcommenttags)|Ruft ab, ob der WebBrowser ein Symbol für Kommentar-Tags angezeigt.|  
|[CHtmlEditCtrlBase::GetShowMiscTags](#getshowmisctags)|Ruft ab, ob der WebBrowser alle Tags, die in Microsoft Internet Explorer 4.0 angezeigt wird.|  
|[CHtmlEditCtrlBase::GetShowScriptTags](#getshowscripttags)|Ruft ab, ob der WebBrowser ein Symbol für die Script-Tags angezeigt.|  
|[CHtmlEditCtrlBase::GetShowStyleTags](#getshowstyletags)|Ruft ab, ob der WebBrowser ein Symbol für alle Style-Tags angezeigt.|  
|[CHtmlEditCtrlBase::GetShowUnknownTags](#getshowunknowntags)|Ruft ab, ob der WebBrowser zeigt ein Symbol für alle unbekannten Tags an.|  
|[CHtmlEditCtrlBase::HorizontalLine](#horizontalline)|Überschreibt eine horizontale Linie auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::HyperLink](#hyperlink)|Fügt einen Hyperlink auf die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::IE50Paste](#ie50paste)|Führt einen Einfügevorgang mit Microsoft Internet Explorer 5 kompatibel.|  
|[CHtmlEditCtrlBase::Iframe](#iframe)|Überschreibt einen Inlineframe auf die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::Image](#image)|Überschreibt ein Bild auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Indent](#indent)|Eine Einzugsebene Inkrement erhöht den Einzug des ausgewählten Texts.|  
|[CHtmlEditCtrlBase::InsFieldSet](#insfieldset)|Wird ein Feld für die aktuelle Auswahl überschrieben.|  
|[CHtmlEditCtrlBase::InsInputButton](#insinputbutton)|Überschreibt ein Button-Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputHidden](#insinputhidden)|Fügt ein ausgeblendetes Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputImage](#insinputimage)|Überschreibt ein Image-Steuerelement für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::InsInputPassword](#insinputpassword)|Überschreibt eine Kennwort-Steuerelement für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::InsInputReset](#insinputreset)|Überschreibt eine setzt das Steuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::InsInputSubmit](#insinputsubmit)|Überschreibt eine Submit-Steuerelement für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::InsInputUpload](#insinputupload)|Überschreibt eine Dateiupload-Steuerelement für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::Is1DElement](#is1delement)|Bestimmt, ob ein Element statisch positioniert wird.|  
|[CHtmlEditCtrlBase::Is2DElement](#is2delement)|Bestimmt, ob ein Element absolut positioniert ist.|  
|[CHtmlEditCtrlBase::Italic](#italic)|Schaltet die aktuelle Auswahl zwischen kursiv und nicht.|  
|[CHtmlEditCtrlBase::JustifyCenter](#justifycenter)|Zentriert die Format-Block in dem sich die aktuelle Auswahl befindet.|  
|[CHtmlEditCtrlBase::JustifyLeft](#justifyleft)|Richtet den Format-Block in dem sich die aktuelle Auswahl befindet.|  
|[CHtmlEditCtrlBase::JustifyRight](#justifyright)|Richtet den Format-Block in dem sich die aktuelle Auswahl befindet.|  
|[CHtmlEditCtrlBase::ListBox](#listbox)|Überschreibt ein Listenfeld Auswahl auf die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::Marquee](#marquee)|Überschreibt eine leere Auswahlrahmen auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::NewDocument](#newdocument)|Erstellt ein neues Dokument.|  
|[CHtmlEditCtrlBase::OrderList](#orderlist)|Schaltet die aktuelle Auswahl zwischen einer geordneten Liste und einem Standardformat-Block.|  
|[CHtmlEditCtrlBase::Outdent](#outdent)|Verkleinert schrittweise den Einzug des Blocks Format in dem sich die aktuelle Auswahl befindet.|  
|[CHtmlEditCtrlBase::Paragraph](#paragraph)|Überschreibt einen Zeilenumbruch für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::Paste](#paste)|Überschreibt den Inhalt der Zwischenablage an der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::PrintDocument](#printdocument)|Druckt das aktuelle Dokument.|  
|[CHtmlEditCtrlBase::PrintPreview](#printpreview)|Öffnet das Fenster "Seitenansicht" für das aktuelle Dokument mithilfe der Standardvorlage für die Seitenansicht oder eine benutzerdefinierte Vorlage.|  
|[CHtmlEditCtrlBase::QueryStatus](#querystatus)|Rufen Sie diese Methode, um den Status der Befehle abzufragen.|  
|[CHtmlEditCtrlBase::RadioButton](#radiobutton)|Überschreibt ein Optionsfeld für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::RefreshDocument](#refreshdocument)|Aktualisiert das aktuelle Dokument.|  
|[CHtmlEditCtrlBase::RemoveFormat](#removeformat)|Entfernt die Formatierung Tags aus der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::SaveAs](#saveas)|Speichert die aktuelle Webseite in einer Datei.|  
|[CHtmlEditCtrlBase::SelectAll](#selectall)|Wählt das gesamte Dokument aus.|  
|[CHtmlEditCtrlBase::Set2DPosition](#set2dposition)|Ermöglicht absolut positionierten Elemente durch Ziehen verschoben werden.|  
|[CHtmlEditCtrlBase::SetAbsolutePosition](#setabsoluteposition)|Legt die Position-Eigenschaft für ein Element auf "absolut" oder "static".|  
|[CHtmlEditCtrlBase::SetAtomicSelection](#setatomicselection)|Legen Sie atomare Auswahlmodus.|  
|[CHtmlEditCtrlBase::SetAutoURLDetectMode](#setautourldetectmode)|Aktiviert die automatische Erkennung der URL ein- und ausschalten.|  
|[CHtmlEditCtrlBase::SetBackColor](#setbackcolor)|Legt die Hintergrundfarbe der aktuellen Auswahl fest.|  
|[CHtmlEditCtrlBase::SetBlockFormat](#setblockformat)|Legt den aktuellen Block Formattag fest.|  
|[CHtmlEditCtrlBase::SetBookMark](#setbookmark)|Erstellt einen Anker Lesezeichen für die aktuelle Auswahl oder einfügen.|  
|[CHtmlEditCtrlBase::SetCSSEditingLevel](#setcsseditinglevel)|Wählt die CSS Level (CSS1 oder CSS2) Editor, ggf. unterstützt.|  
|[CHtmlEditCtrlBase::SetDefaultComposeSettings](#setdefaultcomposesettings)|Rufen Sie diese Methode zum Festlegen der Einstellungen erstellen.|  
|[CHtmlEditCtrlBase::SetDesignMode](#setdesignmode)|Legen Sie im Entwurfsmodus.|  
|[CHtmlEditCtrlBase::SetDisableEditFocusUI](#setdisableeditfocusui)|Deaktiviert den schraffierten Rahmen und behandelt werden, um ein Element aus, bearbeiten den Fokus besitzt.|  
|[CHtmlEditCtrlBase::SetDocumentHTML](#setdocumenthtml)|Legt den HTML-Code des aktuellen Dokuments.|  
|[CHtmlEditCtrlBase::SetFontFace](#setfontface)|Legt die Schriftart für die aktuelle Auswahl fest.|  
|[CHtmlEditCtrlBase::SetFontSize](#setfontsize)|Legt den Schriftgrad für die aktuelle Auswahl fest.|  
|[CHtmlEditCtrlBase::SetForeColor](#setforecolor)|Legt die Vordergrundfarbe (Text) der aktuellen Auswahl fest.|  
|[CHtmlEditCtrlBase::SetIE5PasteMode](#setie5pastemode)|Legt den Einfügevorgang mit Microsoft Internet Explorer 5 kompatibel.|  
|[CHtmlEditCtrlBase::SetLiveResize](#setliveresize)|Bewirkt, dass der WebBrowser, um ein Element Darstellung kontinuierlich während eines Vorgangs ändern der Größe oder verschieben zu aktualisieren.|  
|[CHtmlEditCtrlBase::SetMultiSelect](#setmultiselect)|Ermöglicht die Auswahl mehrerer Elemente.|  
|[CHtmlEditCtrlBase::SetOverrideCursor](#setoverridecursor)|Befehle der WebBrowser nicht zum Ändern des Mauszeigers.|  
|[CHtmlEditCtrlBase::SetOverwriteMode](#setoverwritemode)|Schaltet zwischen der Eingabe von Text-Modus einfügen und überschreiben.|  
|[CHtmlEditCtrlBase::SetRespectVisInDesign](#setrespectvisindesign)|Blendet die unsichtbare Elemente im Entwurfsmodus.|  
|[CHtmlEditCtrlBase::SetShowAlignedSiteTags](#setshowalignedsitetags)|Zeigt ein Symbol für alle Elemente, deren ein **StyleFloat** Eigenschaft.|  
|[CHtmlEditCtrlBase::SetShowAllTags](#setshowalltags)|Zeigt die Symbole, die die Position von allen Tags in einem Dokument anzuzeigen.|  
|[CHtmlEditCtrlBase::SetShowAreaTags](#setshowareatags)|Ein Symbol für die Bereich-Tags angezeigt.|  
|[CHtmlEditCtrlBase::SetShowBRTags](#setshowbrtags)|Zeigt ein Symbol für alle Br-Tags.|  
|[CHtmlEditCtrlBase::SetShowCommentTags](#setshowcommenttags)|Zeigt ein Symbol für das Kommentar-Tags.|  
|[CHtmlEditCtrlBase::SetShowMiscTags](#setshowmisctags)|Zeigt alle Tags, die in Microsoft Internet Explorer 4.0 angezeigt.|  
|[CHtmlEditCtrlBase::SetShowScriptTags](#setshowscripttags)|Zeigt ein Symbol für die Script-Tags.|  
|[CHtmlEditCtrlBase::SetShowStyleTags](#setshowstyletags)|Zeigt ein Symbol für alle Style-Tags.|  
|[CHtmlEditCtrlBase::SetShowUnknownTags](#setshowunknowntags)|Zeigt ein Symbol für alle unbekannten Tags.|  
|[CHtmlEditCtrlBase::TextArea](#textarea)|Überschreibt ein mehrzeiliges Textfeld Eingabesteuerelement für die aktuelle Auswahl.|  
|[CHtmlEditCtrlBase::TextBox](#textbox)|Überschreibt ein Textsteuerelement auf der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::UnBookmark](#unbookmark)|Entfernt alle Lesezeichen aus der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::Underline](#underline)|Schaltet die aktuelle Auswahl zwischen unterstrichen und nicht unterstrichen.|  
|[CHtmlEditCtrlBase::Unlink](#unlink)|Entfernt alle Links aus der aktuellen Auswahl.|  
|[CHtmlEditCtrlBase::UnorderList](#unorderlist)|Schaltet die aktuelle Auswahl zwischen einer geordneten Liste und einem Standardformat-Block.|  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Name der abgeleiteten Klasse.  
  
## <a name="remarks"></a>Hinweise  
 **CHtmlEditCtrlBase** stellt Memberfunktionen für den WebBrowser HTML Bearbeitungsbefehle, wie z. B. [fett](#bold). (Sie können auch aufrufen [ExecCommand](#execcommand) zum Ausführen der **IDM_BOLD** Befehl.)  
  
 **CHtmlEditCtrlBase** soll nicht eigenständigen auf. Sie dient als Basisklasse für abgeleitete Klassen sein, die die HTML-Bearbeitung Funktionalität der WebBrowser verfügbar zu machen (siehe [CHtmlEditCtrl](../../mfc/reference/chtmleditctrl-class.md) und [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CHtmlEditCtrlBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxhtml.h  
  
##  <a name="a-nameaddtoglyphtablea--chtmleditctrlbaseaddtoglyphtable"></a><a name="addtoglyphtable"></a>CHtmlEditCtrlBase::AddToGlyphTable  
 Fügt einen Eintrag in die Symbol-Tabelle, die für bestimmte Tags im Entwurfsmodus anzuzeigenden Bilder angibt.  
  
```  
HRESULT AddToGlyphTable(
    LPCTSTR szTag,  
    LPCTSTR szImgUrl,  
    unsigned short nTagType,  
    unsigned short nAlignment,  
    unsigned short nPosInfo,  
    unsigned short nDirection,  
    unsigned int nImgWidth,  
    unsigned int nImgHeight) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szTag`  
 Der Tagname (z. B. "P" oder "Tabelle").  
  
 *szImgUrl*  
 Die Bild-URL.  
  
 *nTagType*  
 Tag-Typ: 0 bedeutet, dass das Bild für das Anfangstag nur. 1 bedeutet, dass das Bild nur das Endtag ist. 2 bedeutet, dass das Bild für sowohl die Start- und Endtags. Einzelne Tags wie Br und Kommentar müssen mit dem Tagtyp, der auf 0 festgelegt hinzugefügt werden.  
  
 *nAlignment*  
 Ausrichtung (nur rechteckige Elemente): dieser Parameter gibt an, dass das Bild für ein Element mit einem Ausrichtungsattribut. Links = 0, Center = 1, rechts = 2 und undefined = 3. Links, müssen rechts oder zentriert Attribute explizit auf das Element festgelegt werden.  
  
 *nPosInfo*  
 Positionierungsinformationen. Bestimmt, welche cascading (CSS) Positionierung Wert Stylesheets das Symbol gilt, wenn statische Positionierung = 0, absolute Positionierung = 1, relative Positionierung = 2, und alle = 3. In diesem Feld können Sie angeben, ein Symbol für ein Tag, wenn er nicht positioniert ist und ein anderes Symbol einen Ankerpunkt angezeigt, wenn das Tag befindet.  
  
 *nDirection*  
 Die Richtung. Dieser Parameter gibt das Bild für einen Tag basierend auf der aktuellen Sprache die Lesefolge. 0 gibt an, von links nach rechts, rechts nach links Wert 1 gibt an, 2 Gibt an, von oben nach unten, 3 gibt an, von unten nach oben und 4 gibt alle. Sie haben dieses Feld normalerweise auf 4 festlegen.  
  
 *nImgWidth*  
 Die Breite in Pixel.  
  
 *nImgHeight*  
 Die Höhe in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den Parametern finden Sie unter "Glyphe Tabellenformat Zeichenfolge" in [bearbeiten Glyphen verwenden](https://msdn.microsoft.com/library/aa969614.aspx).  
  
 Diese Methode sendet die [IDM_ADDTOGLYPHTABLE-Befehls-ID](https://msdn.microsoft.com/library/aa769891.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namebolda--chtmleditctrlbasebold"></a><a name="bold"></a>CHtmlEditCtrlBase::Bold  
 Blendet die fett formatiert den markierten Text.  
  
```  
HRESULT Bold() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_BOLD-Befehls-ID](https://msdn.microsoft.com/library/aa769861.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namebuttona--chtmleditctrlbasebutton"></a><a name="button"></a>CHtmlEditCtrlBase::Button  
 Überschreibt ein Button-Steuerelement auf der aktuellen Auswahl.  
  
```  
HRESULT Button(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Button-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_BUTTON-Befehls-ID](https://msdn.microsoft.com/library/aa769966.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namecheckboxa--chtmleditctrlbasecheckbox"></a><a name="checkbox"></a>CHtmlEditCtrlBase::CheckBox  
 Wird ein Kontrollkästchen-Steuerelement für die aktuelle Auswahl überschrieben.  
  
```  
HRESULT CheckBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Kontrollkästchen-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_CHECKBOX-Befehls-ID](https://msdn.microsoft.com/library/aa769972.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameclearselectiona--chtmleditctrlbaseclearselection"></a><a name="clearselection"></a>CHtmlEditCtrlBase::ClearSelection  
 Löscht die aktuelle Auswahl.  
  
```  
HRESULT ClearSelection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_CLEARSELECTION-Befehls-ID](https://msdn.microsoft.com/library/aa770038.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namecopya--chtmleditctrlbasecopy"></a><a name="copy"></a>CHtmlEditCtrlBase::Copy  
 Kopiert die aktuelle Auswahl in die Zwischenablage.  
  
```  
HRESULT Copy() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_COPY-Befehls-ID](https://msdn.microsoft.com/library/aa769872.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namecuta--chtmleditctrlbasecut"></a><a name="cut"></a>CHtmlEditCtrlBase::Cut  
 Kopiert die aktuelle Auswahl in die Zwischenablage und löscht sie dann.  
  
```  
HRESULT Cut() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_CUT-Befehls-ID](https://msdn.microsoft.com/library/aa769875.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namedeletea--chtmleditctrlbasedelete"></a><a name="delete"></a>CHtmlEditCtrlBase::Delete  
 Löscht die aktuelle Auswahl.  
  
```  
HRESULT Delete() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_DELETE-Befehls-ID](https://msdn.microsoft.com/library/aa769876.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namedropdownboxa--chtmleditctrlbasedropdownbox"></a><a name="dropdownbox"></a>CHtmlEditCtrlBase::DropDownBox  
 Überschreibt eine Dropdown-Liste-Steuerelement für die aktuelle Auswahl.  
  
```  
HRESULT DropDownBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Steuerelements Dropdown-Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_DROPDOWNBOX-Befehls-ID](https://msdn.microsoft.com/library/aa769984.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameemptyglyphtablea--chtmleditctrlbaseemptyglyphtable"></a><a name="emptyglyphtable"></a>CHtmlEditCtrlBase::EmptyGlyphTable  
 Entfernt alle Einträge aus der Tabelle Symbol, alle Bilder für Tags im Entwurfsmodus angezeigt Blendet.  
  
```  
HRESULT EmptyGlyphTable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_EMPTYGLYPHTABLE-Befehls-ID](https://msdn.microsoft.com/library/aa769907.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameexeccommanda--chtmleditctrlbaseexeccommand"></a><a name="execcommand"></a>CHtmlEditCtrlBase::ExecCommand  
 Führt einen Befehl aus.  
  
```  
HRESULT ExecCommand(
    long cmdID,  
    long cmdExecOpt,  
    VARIANT* pInVar = NULL,  
    VARIANT* pOutVar = NULL) const;  
  
HRESULT ExecCommand(
    const GUID* pGuid,  
    long cmdID,  
    long cmdExecOpt,  
    VARIANT* pInVar = NULL,  
    VARIANT* pOutVar = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID, die ausgeführt werden. Eine Liste finden Sie unter [MSHTML-Befehls-IDs](https://msdn.microsoft.com/library/aa741315.aspx).  
  
 `cmdExecOpt`  
 Werte, die von der [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) -Enumeration, die beschreiben, wie das Objekt den Befehl ausführen soll.  
  
 *pInVar*  
 Die Eingabeargumente.  
  
 *pOutVar*  
 Die Ausgabe des Befehls.  
  
 *pGuid*  
 Die GUID der Befehlsgruppe.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode bietet die Funktionalität des [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300).  
  
##  <a name="a-namefonta--chtmleditctrlbasefont"></a><a name="font"></a>CHtmlEditCtrlBase::Font  
 Öffnet eine Schriftart (Dialogfeld), um dem Benutzer das Ändern der Farbe, Schriftart und Schriftgrad der aktuellen Auswahl zu aktivieren.  
  
```  
HRESULT Font() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_FONT-Befehls-ID](https://msdn.microsoft.com/library/aa769913.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetabsolutepositiona--chtmleditctrlbasegetabsoluteposition"></a><a name="getabsoluteposition"></a>CHtmlEditCtrlBase::GetAbsolutePosition  
 Gibt zurück, ob ein Element Position-Eigenschaft "absolute".  
  
```  
HRESULT GetAbsolutePosition(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn die-Eigenschaft des Elements Position festgelegt zu "absolute".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_ABSOLUTE_POSITION-Befehls-ID](https://msdn.microsoft.com/library/aa769889.aspx).  
  
##  <a name="a-namegetbackcolora--chtmleditctrlbasegetbackcolor"></a><a name="getbackcolor"></a>CHtmlEditCtrlBase::GetBackColor  
 Ruft die Hintergrundfarbe der aktuellen Auswahl ab.  
  
```  
HRESULT GetBackColor(int& nColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nColor`  
 Die Hintergrundfarbe.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_BACKCOLOR-Befehls-ID](https://msdn.microsoft.com/library/aa769858.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetblockformata--chtmleditctrlbasegetblockformat"></a><a name="getblockformat"></a>CHtmlEditCtrlBase::GetBlockFormat  
 Ruft den aktuellen Block Formattag ab.  
  
```  
HRESULT GetBlockFormat(CString& strFormat) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *strFormat*  
 Der aktuelle Tag der Block-Format.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_BLOCKFMT-Befehls-ID](https://msdn.microsoft.com/library/aa769883.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetblockformatnamesa--chtmleditctrlbasegetblockformatnames"></a><a name="getblockformatnames"></a>CHtmlEditCtrlBase::GetBlockFormatNames  
 Ruft die Zeichenfolgen für die verfügbaren Block Format-Tags ab.  
  
```  
HRESULT GetBlockFormatNames(CStringArray& sa) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *SA*  
 Die verfügbaren Block Format Tags als ein Array von Zeichenfolgen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_GETBLOCKFMTS-Befehls-ID](https://msdn.microsoft.com/library/aa769884.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetbookmarka--chtmleditctrlbasegetbookmark"></a><a name="getbookmark"></a>CHtmlEditCtrlBase::GetBookMark  
 Ruft den Namen der als Lesezeichen Anker dargestellt.  
  
```  
HRESULT GetBookMark(CString& strAnchor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *strAnchor*  
 Der Name der als Lesezeichen Anker dargestellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_BOOKMARK-Befehls-ID](https://msdn.microsoft.com/library/aa769873.aspx).  
  
##  <a name="a-namegetdocumenta--chtmleditctrlbasegetdocument"></a><a name="getdocument"></a>CHtmlEditCtrlBase::GetDocument  
 Ruft das Document-Objekt ab.  
  
```  
HRESULT GetDocument(IHTMLDocument2** ppDoc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppDoc`  
 Das Document-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namegetdocumenthtmla--chtmleditctrlbasegetdocumenthtml"></a><a name="getdocumenthtml"></a>CHtmlEditCtrlBase::GetDocumentHTML  
 Ruft den HTML-Code des aktuellen Dokuments ab.  
  
```  
HRESULT GetDocumentHTML(CString& szHTML) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szHTML`  
 Der HTML-Code.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namegetdocumenttitlea--chtmleditctrlbasegetdocumenttitle"></a><a name="getdocumenttitle"></a>CHtmlEditCtrlBase::GetDocumentTitle  
 Ruft den Titel des Dokuments ab.  
  
```  
HRESULT GetDocumentTitle(CString& szTitle) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *szTitle*  
 Der Titel des Dokuments.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namegeteventa--chtmleditctrlbasegetevent"></a><a name="getevent"></a>CHtmlEditCtrlBase::GetEvent  
 Ruft einen Schnittstellenzeiger auf das Ereignisobjekt, das Informationen über das neueste Ereignis enthält.  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppEventObj`  
 Das Ereignisobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namegeteventsrcelementa--chtmleditctrlbasegeteventsrcelement"></a><a name="geteventsrcelement"></a>CHtmlEditCtrlBase::GetEventSrcElement  
 Ruft das Objekt, das das Ereignis ausgelöst hat.  
  
```  
HRESULT GetEventSrcElement(IHTMLElement** ppSrcElement) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *ppSrcElement*  
 Das Element, das das Ereignis ausgelöst hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namegetfontfacea--chtmleditctrlbasegetfontface"></a><a name="getfontface"></a>CHtmlEditCtrlBase::GetFontFace  
 Ruft den Schriftartnamen für die aktuelle Auswahl ab.  
  
```  
HRESULT GetFontFace(CString& strFace) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strFace`  
 Der Name der Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die aktuelle Auswahl mehrere Schriftarten verwendet `strFace` wird eine leere Zeichenfolge sein.  
  
 Diese Methode sendet die [IDM_FONTNAME-Befehls-ID](https://msdn.microsoft.com/library/aa769880.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetfontsizea--chtmleditctrlbasegetfontsize"></a><a name="getfontsize"></a>CHtmlEditCtrlBase::GetFontSize  
 Ruft den Schriftgrad für die aktuelle Auswahl ab.  
  
```  
HRESULT GetFontSize(short& nSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nSize`  
 Der Schriftgrad.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Schriftgrad HTML (1 bis&7;). Gibt 0 zurück, wenn die Auswahl mehrere Schriftgrade enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_FONTSIZE-Befehls-ID](https://msdn.microsoft.com/library/aa769881.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetforecolora--chtmleditctrlbasegetforecolor"></a><a name="getforecolor"></a>CHtmlEditCtrlBase::GetForeColor  
 Ruft die Vordergrundfarbe (Text), der die aktuelle Auswahl ab.  
  
```  
HRESULT GetForeColor(int& nColor);
```  
  
### <a name="parameters"></a>Parameter  
 `nColor`  
 Die Vordergrundfarbe.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_FORECOLOR-Befehls-ID](https://msdn.microsoft.com/library/aa769882.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetframezonea--chtmleditctrlbasegetframezone"></a><a name="getframezone"></a>CHtmlEditCtrlBase::GetFrameZone  
 Gibt die Sicherheitszone der aktuellen Seite im Webbrowser an.  
  
```  
HRESULT GetFrameZone(short& nZone) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nZone*  
 Der Sicherheitszone.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_GETFRAMEZONE-Befehls-ID](https://msdn.microsoft.com/library/aa769916.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namegetisdirtya--chtmleditctrlbasegetisdirty"></a><a name="getisdirty"></a>CHtmlEditCtrlBase::GetIsDirty  
 Gibt an, ob das HTML-Dokument geändert wurde.  
  
```  
HRESULT GetIsDirty() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt an, ob das Dokument geändert wurde. `GetIsDirty`Gibt eine `HRESULT` von [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910).  
  
##  <a name="a-namegetshowalignedsitetagsa--chtmleditctrlbasegetshowalignedsitetags"></a><a name="getshowalignedsitetags"></a>CHtmlEditCtrlBase::GetShowAlignedSiteTags  
 Gibt zurück, ob ein Symbol für alle Elemente angezeigt wird, die über eine **StyleFloat** Eigenschaft.  
  
```  
HRESULT GetShowAlignedSiteTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn ein Symbol für alle Elemente angezeigt wird, die über eine **StyleFloat** Eigenschaft, False, wenn kein Symbol angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWALIGNEDSITETAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769947.aspx).  
  
##  <a name="a-namegetshowalltagsa--chtmleditctrlbasegetshowalltags"></a><a name="getshowalltags"></a>CHtmlEditCtrlBase::GetShowAllTags  
 Gibt zurück, ob der WebBrowser Symbole an den Speicherort der alle Tags in einem Dokument angezeigt.  
  
```  
HRESULT GetShowAllTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser Symbole, um den Speicherort der alle Tags in einem Dokument anzeigen angezeigt. False, wenn dies nicht der Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWALLTAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769948.aspx).  
  
##  <a name="a-namegetshowareatagsa--chtmleditctrlbasegetshowareatags"></a><a name="getshowareatags"></a>CHtmlEditCtrlBase::GetShowAreaTags  
 Ruft ab, ob der WebBrowser ein Symbol für Tags Bereich angezeigt.  
  
```  
HRESULT GetShowAreaTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser ein Symbol für Tags im Bereich "false" angezeigt, wenn dies nicht der Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWAREATAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769949.aspx).  
  
##  <a name="a-namegetshowbrtagsa--chtmleditctrlbasegetshowbrtags"></a><a name="getshowbrtags"></a>CHtmlEditCtrlBase::GetShowBRTags  
 Ruft ab, ob der WebBrowser ein Symbol für Br-Tags angezeigt.  
  
```  
HRESULT GetShowBRTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser ein Symbol für Br-Tags "false" angezeigt, wenn dies nicht der Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWWBRTAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769956.aspx).  
  
##  <a name="a-namegetshowcommenttagsa--chtmleditctrlbasegetshowcommenttags"></a><a name="getshowcommenttags"></a>CHtmlEditCtrlBase::GetShowCommentTags  
 Ruft ab, ob der WebBrowser ein Symbol für Kommentar-Tags angezeigt.  
  
```  
HRESULT GetShowCommentTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser ein Symbol für Kommentar-Tags "false" angezeigt, wenn dies nicht der Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWCOMMENTTAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769950.aspx).  
  
##  <a name="a-namegetshowmisctagsa--chtmleditctrlbasegetshowmisctags"></a><a name="getshowmisctags"></a>CHtmlEditCtrlBase::GetShowMiscTags  
 Ruft ab, ob der WebBrowser alle Tags, die in Microsoft Internet Explorer 4.0 angezeigt wird.  
  
```  
HRESULT GetShowMiscTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser alle Tags angezeigt, die in Microsoft Internet Explorer 4.0, False zeigt, wenn dies nicht der Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWMISCTAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769952.aspx).  
  
##  <a name="a-namegetshowscripttagsa--chtmleditctrlbasegetshowscripttags"></a><a name="getshowscripttags"></a>CHtmlEditCtrlBase::GetShowScriptTags  
 Ruft ab, ob der WebBrowser ein Symbol für die Script-Tags angezeigt.  
  
```  
HRESULT GetShowScriptTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser ein Symbol für alle Skripttags false angezeigt, wenn dies nicht der Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWSCRIPTTAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769953.aspx).  
  
##  <a name="a-namegetshowstyletagsa--chtmleditctrlbasegetshowstyletags"></a><a name="getshowstyletags"></a>CHtmlEditCtrlBase::GetShowStyleTags  
 Ruft ab, ob der WebBrowser ein Symbol für alle Style-Tags angezeigt.  
  
```  
HRESULT GetShowStyleTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser ein Symbol für alle Style-Tags "false" angezeigt, wenn dies nicht der Fall  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWSTYLETAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769954.aspx).  
  
##  <a name="a-namegetshowunknowntagsa--chtmleditctrlbasegetshowunknowntags"></a><a name="getshowunknowntags"></a>CHtmlEditCtrlBase::GetShowUnknownTags  
 Ruft ab, ob der WebBrowser zeigt ein Symbol für alle unbekannten Tags an.  
  
```  
HRESULT GetShowUnknownTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bCurValue`  
 True, wenn der WebBrowser ein Symbol für alle unbekannten Tags false angezeigt, wenn dies nicht der Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDM_SHOWUNKNOWNTAGS-Befehls-ID](https://msdn.microsoft.com/library/aa769955.aspx).  
  
##  <a name="a-namehorizontallinea--chtmleditctrlbasehorizontalline"></a><a name="horizontalline"></a>CHtmlEditCtrlBase::HorizontalLine  
 Überschreibt eine horizontale Linie auf der aktuellen Auswahl.  
  
```  
HRESULT HorizontalLine(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *szID*  
 Die ID für die horizontale Linie.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_HORIZONTALLINE-Befehls-ID](https://msdn.microsoft.com/library/aa769968.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namehyperlinka--chtmleditctrlbasehyperlink"></a><a name="hyperlink"></a>CHtmlEditCtrlBase::HyperLink  
 Fügt einen Hyperlink auf die aktuelle Auswahl.  
  
```  
HRESULT HyperLink(LPCTSTR szUrl = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szUrl`  
 Der Hyperlink-URL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_HYPERLINK-Befehls-ID](https://msdn.microsoft.com/library/aa769874.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameie50pastea--chtmleditctrlbaseie50paste"></a><a name="ie50paste"></a>CHtmlEditCtrlBase::IE50Paste  
 Führt einen Einfügevorgang, der mit Internet Explorer 5 kompatibel ist.  
  
```  
HRESULT IE50Paste(LPCTSTR szData) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szData`  
 Die Zeichenfolge eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_IE50_PASTE-Befehls-ID](https://msdn.microsoft.com/library/aa769922.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameiframea--chtmleditctrlbaseiframe"></a><a name="iframe"></a>CHtmlEditCtrlBase::Iframe  
 Überschreibt einen Inlineframe auf die aktuelle Auswahl.  
  
```  
HRESULT Iframe(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Inlineframes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_IFRAME-Befehls-ID](https://msdn.microsoft.com/library/aa769969.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameimagea--chtmleditctrlbaseimage"></a><a name="image"></a>CHtmlEditCtrlBase::Image  
 Überschreibt ein Bild auf der aktuellen Auswahl.  
  
```  
HRESULT Image(LPCTSTR szUrl = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szUrl`  
 Der Pfad und Dateiname des Bildes, das eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_IMAGE-Befehls-ID](https://msdn.microsoft.com/library/aa769970.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameindenta--chtmleditctrlbaseindent"></a><a name="indent"></a>CHtmlEditCtrlBase::Indent  
 Eine Einzugsebene Inkrement erhöht den Einzug des ausgewählten Texts.  
  
```  
HRESULT Indent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INDENT-Befehls-ID](https://msdn.microsoft.com/library/aa769963.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsfieldseta--chtmleditctrlbaseinsfieldset"></a><a name="insfieldset"></a>CHtmlEditCtrlBase::InsFieldSet  
 Wird ein Feld für die aktuelle Auswahl überschrieben.  
  
```  
HRESULT InsFieldSet(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Feld.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSFIELDSET-Befehls-ID](https://msdn.microsoft.com/library/aa769967.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsinputbuttona--chtmleditctrlbaseinsinputbutton"></a><a name="insinputbutton"></a>CHtmlEditCtrlBase::InsInputButton  
 Überschreibt ein Button-Steuerelement auf der aktuellen Auswahl.  
  
```  
HRESULT InsInputButton(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Schaltflächen-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSINPUTBUTTON-Befehls-ID](https://msdn.microsoft.com/library/aa769971.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsinputhiddena--chtmleditctrlbaseinsinputhidden"></a><a name="insinputhidden"></a>CHtmlEditCtrlBase::InsInputHidden  
 Fügt ein ausgeblendetes Steuerelement auf der aktuellen Auswahl.  
  
```  
HRESULT InsInputHidden(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Steuerelement ausgeblendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSINPUTHIDDEN-Befehls-ID](https://msdn.microsoft.com/library/aa769974.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsinputimagea--chtmleditctrlbaseinsinputimage"></a><a name="insinputimage"></a>CHtmlEditCtrlBase::InsInputImage  
 Überschreibt ein Image-Steuerelement für die aktuelle Auswahl.  
  
```  
HRESULT InsInputImage(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Image-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSINPUTIMAGE-Befehls-ID](https://msdn.microsoft.com/library/aa769975.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsinputpassworda--chtmleditctrlbaseinsinputpassword"></a><a name="insinputpassword"></a>CHtmlEditCtrlBase::InsInputPassword  
 Überschreibt eine Kennwort-Steuerelement für die aktuelle Auswahl.  
  
```  
HRESULT InsInputPassword(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Kennwort-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSINPUTPASSWORD-Befehls-ID](https://msdn.microsoft.com/library/aa769976.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsinputreseta--chtmleditctrlbaseinsinputreset"></a><a name="insinputreset"></a>CHtmlEditCtrlBase::InsInputReset  
 Überschreibt eine setzt das Steuerelement auf der aktuellen Auswahl.  
  
```  
HRESULT InsInputReset(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Steuerelement zurücksetzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSINPUTRESET-Befehls-ID](https://msdn.microsoft.com/library/aa769978.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsinputsubmita--chtmleditctrlbaseinsinputsubmit"></a><a name="insinputsubmit"></a>CHtmlEditCtrlBase::InsInputSubmit  
 Überschreibt eine Submit-Steuerelement für die aktuelle Auswahl.  
  
```  
HRESULT InsInputSubmit(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Steuerelement senden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSINPUTSUBMIT-Befehls-ID](https://msdn.microsoft.com/library/aa769979.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameinsinputuploada--chtmleditctrlbaseinsinputupload"></a><a name="insinputupload"></a>CHtmlEditCtrlBase::InsInputUpload  
 Überschreibt eine Dateiupload-Steuerelement für die aktuelle Auswahl.  
  
```  
HRESULT InsInputUpload(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Dateiupload-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_INSINPUTUPLOAD-Befehls-ID](https://msdn.microsoft.com/library/aa769973.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameis1delementa--chtmleditctrlbaseis1delement"></a><a name="is1delement"></a>CHtmlEditCtrlBase::Is1DElement  
 Bestimmt, ob ein Element statisch positioniert wird.  
  
```  
HRESULT Is1DElement(bool& bValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bValue`  
 True, wenn das Element statisch positioniert, andernfalls false ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_1D_ELEMENT-Befehls-ID](https://msdn.microsoft.com/library/aa769885.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameis2delementa--chtmleditctrlbaseis2delement"></a><a name="is2delement"></a>CHtmlEditCtrlBase::Is2DElement  
 Bestimmt, ob ein Element absolut positioniert ist.  
  
```  
HRESULT Is2DElement(bool& bValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bValue`  
 True, wenn das Element absolut positioniert, andernfalls false ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_2D_ELEMENT-Befehls-ID](https://msdn.microsoft.com/library/aa769886.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameitalica--chtmleditctrlbaseitalic"></a><a name="italic"></a>CHtmlEditCtrlBase::Italic  
 Schaltet die aktuelle Auswahl zwischen kursiv und nicht.  
  
```  
HRESULT Italic() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_ITALIC-Befehls-ID](https://msdn.microsoft.com/library/aa769988.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namejustifycentera--chtmleditctrlbasejustifycenter"></a><a name="justifycenter"></a>CHtmlEditCtrlBase::JustifyCenter  
 Zentriert die Format-Block in dem sich die aktuelle Auswahl befindet.  
  
```  
HRESULT JustifyCenter() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_JUSTIFYCENTER-Befehls-ID](https://msdn.microsoft.com/library/aa769989.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namejustifylefta--chtmleditctrlbasejustifyleft"></a><a name="justifyleft"></a>CHtmlEditCtrlBase::JustifyLeft  
 Richtet den Format-Block in dem sich die aktuelle Auswahl befindet.  
  
```  
HRESULT JustifyLeft() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_JUSTIFYLEFT-Befehls-ID](https://msdn.microsoft.com/library/aa770011.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namejustifyrighta--chtmleditctrlbasejustifyright"></a><a name="justifyright"></a>CHtmlEditCtrlBase::JustifyRight  
 Richtet den Format-Block in dem sich die aktuelle Auswahl befindet.  
  
```  
HRESULT JustifyRight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_JUSTIFYRIGHT-Befehls-ID](https://msdn.microsoft.com/library/aa770013.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namelistboxa--chtmleditctrlbaselistbox"></a><a name="listbox"></a>CHtmlEditCtrlBase::ListBox  
 Überschreibt ein Listenfeld Auswahl auf die aktuelle Auswahl.  
  
```  
HRESULT ListBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für das Listenfeld-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_LISTBOX-Befehls-ID](https://msdn.microsoft.com/library/aa769985.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namemarqueea--chtmleditctrlbasemarquee"></a><a name="marquee"></a>CHtmlEditCtrlBase::Marquee  
 Überschreibt eine leere Auswahlrahmen auf der aktuellen Auswahl.  
  
```  
HRESULT Marquee(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Auswahlbereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_MARQUEE-Befehls-ID](https://msdn.microsoft.com/library/aa769981.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namenewdocumenta--chtmleditctrlbasenewdocument"></a><a name="newdocument"></a>CHtmlEditCtrlBase::NewDocument  
 Erstellt ein neues Dokument.  
  
```  
HRESULT NewDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-nameorderlista--chtmleditctrlbaseorderlist"></a><a name="orderlist"></a>CHtmlEditCtrlBase::OrderList  
 Schaltet die aktuelle Auswahl zwischen einer geordneten Liste und einem Standardformat-Block.  
  
```  
HRESULT OrderList(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für die sortierte Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_ORDERLIST-Befehls-ID](https://msdn.microsoft.com/library/aa769982.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameoutdenta--chtmleditctrlbaseoutdent"></a><a name="outdent"></a>CHtmlEditCtrlBase::Outdent  
 Verkleinert schrittweise den Einzug des Blocks Format in dem sich die aktuelle Auswahl befindet.  
  
```  
HRESULT Outdent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_OUTDENT-Befehls-ID](https://msdn.microsoft.com/library/aa770015.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameparagrapha--chtmleditctrlbaseparagraph"></a><a name="paragraph"></a>CHtmlEditCtrlBase::Paragraph  
 Überschreibt einen Zeilenumbruch für die aktuelle Auswahl.  
  
```  
HRESULT Paragraph(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID für den Absatz.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_PARAGRAPH-Befehls-ID](https://msdn.microsoft.com/library/aa769983.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namepastea--chtmleditctrlbasepaste"></a><a name="paste"></a>CHtmlEditCtrlBase::Paste  
 Überschreibt den Inhalt der Zwischenablage an der aktuellen Auswahl.  
  
```  
HRESULT Paste() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_PASTE-Befehls-ID](https://msdn.microsoft.com/library/aa770017.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameprintdocumenta--chtmleditctrlbaseprintdocument"></a><a name="printdocument"></a>CHtmlEditCtrlBase::PrintDocument  
 Druckt das aktuelle Dokument.  
  
```  
HRESULT PrintDocument() const;  
HRESULT PrintDocument(LPCTSTR szPrintTemplate) const;  
HRESULT PrintDocument(bool bShowPrintDialog) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szPrintTemplate`  
 Der Pfad zu einer Druckvorlage; Wenn keine Angabe erfolgt, wird standarddruckvorlage verwendet.  
  
 *bShowPrintDialog*  
 Wenn true festgelegt ist, zeigt das Dialogfeld Drucken.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_PRINT-Befehls-ID](https://msdn.microsoft.com/library/aa769937.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameprintpreviewa--chtmleditctrlbaseprintpreview"></a><a name="printpreview"></a>CHtmlEditCtrlBase::PrintPreview  
 Öffnet das Fenster "Seitenansicht" für das aktuelle Dokument mithilfe der Standardvorlage für die Seitenansicht oder eine benutzerdefinierte Vorlage.  
  
```  
HRESULT PrintPreview() const;  
HRESULT PrintPreview(LPCTSTR szPrintTemplate) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szPrintTemplate`  
 Pfad zur Druckvorlagen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_PRINTPREVIEW-Befehls-ID](https://msdn.microsoft.com/library/aa769938.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namequerystatusa--chtmleditctrlbasequerystatus"></a><a name="querystatus"></a>CHtmlEditCtrlBase::QueryStatus  
 Rufen Sie diese Methode, um den Status der Befehle abzufragen.  
  
```  
long QueryStatus(long cmdID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID. Befehls-IDs stammen aus den `CGID_MSHTML`Befehlsgruppe. Diese Befehle sind in Mshtmcid.h definiert. Sie finden auch die Liste online am [MSHTML-Befehls-IDs](http://go.microsoft.com/fwlink/linkid=149220).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237) gibt den Status für `cmdID`, oder 0 bei einem Fehlschlag.  
  
##  <a name="a-nameradiobuttona--chtmleditctrlbaseradiobutton"></a><a name="radiobutton"></a>CHtmlEditCtrlBase::RadioButton  
 Überschreibt ein Optionsfeld für die aktuelle Auswahl.  
  
```  
HRESULT RadioButton(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Optionsfelds.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_RADIOBUTTON-Befehls-ID](https://msdn.microsoft.com/library/aa769977.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namerefreshdocumenta--chtmleditctrlbaserefreshdocument"></a><a name="refreshdocument"></a>CHtmlEditCtrlBase::RefreshDocument  
 Aktualisiert das aktuelle Dokument.  
  
```  
HRESULT RefreshDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_REFRESH-Befehls-ID](https://msdn.microsoft.com/library/aa770020.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameremoveformata--chtmleditctrlbaseremoveformat"></a><a name="removeformat"></a>CHtmlEditCtrlBase::RemoveFormat  
 Entfernt die Formatierung Tags aus der aktuellen Auswahl.  
  
```  
HRESULT RemoveFormat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_REMOVEFORMAT-Befehls-ID](https://msdn.microsoft.com/library/aa770021.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesaveasa--chtmleditctrlbasesaveas"></a><a name="saveas"></a>CHtmlEditCtrlBase::SaveAs  
 Speichert die aktuelle Webseite in einer Datei.  
  
```  
HRESULT SaveAs(LPCTSTR szPath = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szPath`  
 Der Pfad und Dateiname, der zum Speichern der Webseite.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_SAVEAS-Befehls-ID](https://msdn.microsoft.com/library/aa770024.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameselectalla--chtmleditctrlbaseselectall"></a><a name="selectall"></a>CHtmlEditCtrlBase::SelectAll  
 Wählt das gesamte Dokument aus.  
  
```  
HRESULT SelectAll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_SELECTALL-Befehls-ID](https://msdn.microsoft.com/library/aa770025.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameset2dpositiona--chtmleditctrlbaseset2dposition"></a><a name="set2dposition"></a>CHtmlEditCtrlBase::Set2DPosition  
 Ermöglicht absolut positionierten Elemente durch Ziehen verschoben werden.  
  
```  
HRESULT Set2DPosition(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, absolut positionierte Elementen durch Ziehen verschoben werden können.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_2D_POSITION-Befehls-ID](https://msdn.microsoft.com/library/aa769887.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetabsolutepositiona--chtmleditctrlbasesetabsoluteposition"></a><a name="setabsoluteposition"></a>CHtmlEditCtrlBase::SetAbsolutePosition  
 Legt die Position-Eigenschaft für ein Element auf "absolut" oder "static".  
  
```  
HRESULT SetAbsolutePosition(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird die Position-Eigenschaft des Elements "absolute"; Wenn der Wert false ist, ist es "static".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_ABSOLUTE_POSITION-Befehls-ID](https://msdn.microsoft.com/library/aa769889.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetatomicselectiona--chtmleditctrlbasesetatomicselection"></a><a name="setatomicselection"></a>CHtmlEditCtrlBase::SetAtomicSelection  
 Legen Sie atomare Auswahlmodus.  
  
```  
HRESULT SetAtomicSelection(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird jedes Element, das einem ATOMICSELECTION-Attribut auf TRUE festgelegt ist nur als eine Einheit ausgewählt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_ATOMICSELECTION-Befehls-ID](https://msdn.microsoft.com/library/aa769892.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetautourldetectmodea--chtmleditctrlbasesetautourldetectmode"></a><a name="setautourldetectmode"></a>CHtmlEditCtrlBase::SetAutoURLDetectMode  
 Aktiviert die automatische Erkennung der URL ein- und ausschalten.  
  
```  
HRESULT SetAutoURLDetectMode(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird die automatische URL-Erkennung aktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_AUTOURLDETECT_MODE-Befehls-ID](https://msdn.microsoft.com/library/aa769893.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetbackcolora--chtmleditctrlbasesetbackcolor"></a><a name="setbackcolor"></a>CHtmlEditCtrlBase::SetBackColor  
 Legt die Hintergrundfarbe der aktuellen Auswahl fest.  
  
```  
HRESULT SetBackColor(int nColor) const;  
HRESULT SetBackColor(LPCTSTR szColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nColor`  
 Die Farbe. Finden Sie unter `pvaIn` in [IDM_BACKCOLOR-Befehls-ID](https://msdn.microsoft.com/library/aa769858.aspx).  
  
 `szColor`  
 Die Farbe. Finden Sie unter `pvaIn` in [IDM_BACKCOLOR-Befehls-ID](https://msdn.microsoft.com/library/aa769858.aspx).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_BACKCOLOR_-Befehls-ID](https://msdn.microsoft.com/library/aa769858.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetblockformata--chtmleditctrlbasesetblockformat"></a><a name="setblockformat"></a>CHtmlEditCtrlBase::SetBlockFormat  
 Legt den aktuellen Block Formattag fest.  
  
```  
HRESULT SetBlockFormat(LPCTSTR szFormat) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szFormat`  
 Das Formattag.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_BLOCKFMT_command ID](https://msdn.microsoft.com/library/aa769883.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetbookmarka--chtmleditctrlbasesetbookmark"></a><a name="setbookmark"></a>CHtmlEditCtrlBase::SetBookMark  
 Erstellt einen Anker Lesezeichen für die aktuelle Auswahl oder einfügen.  
  
```  
HRESULT SetBookMark(LPCTSTR szAnchorName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *szAnchorName*  
 Der Ankername.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_BOOKMARK-Befehls-ID](https://msdn.microsoft.com/library/aa769873.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetcsseditinglevela--chtmleditctrlbasesetcsseditinglevel"></a><a name="setcsseditinglevel"></a>CHtmlEditCtrlBase::SetCSSEditingLevel  
 Wählt die CSS Level (CSS1 oder CSS2) Editor, ggf. unterstützt.  
  
```  
HRESULT SetCSSEditingLevel(short nLevel) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLevel`  
 Die CSS-Ebene. Übergeben Sie 0 an, wenn Sie nicht, dass CSS-Unterstützung möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_CSSEDITING_LEVEL-Befehls-ID](https://msdn.microsoft.com/library/aa769903.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetdefaultcomposesettingsa--chtmleditctrlbasesetdefaultcomposesettings"></a><a name="setdefaultcomposesettings"></a>CHtmlEditCtrlBase::SetDefaultComposeSettings  
 Rufen Sie diese Methode zum Festlegen der Einstellungen erstellen.  
  
```  
HRESULT SetDefaultComposeSettings(
    LPCSTR szFontName = NULL,  
    unsigned short nFontSize = 3,  
    COLORREF crFontColor = 0xFF000000,  
    COLORREF crFontBgColor = 0xFF000000,  
    bool bBold = false,  
    bool bItalic = false,  
    bool bUnderline = false) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *szFontName*  
 Der Name der Schriftart.  
  
 *nFontSize*  
 Der Schriftgrad.  
  
 *crFontColor*  
 Die Schriftfarbe.  
  
 *crFontBgColor*  
 Die Hintergrundfarbe der Schriftart.  
  
 *bBold*  
 Übergeben Sie true für fett formatierten Text.  
  
 `bItalic`  
 Übergeben Sie true für kursiven Text.  
  
 `bUnderline`  
 Übergeben Sie true für unterstrichenen Text.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_COMPOSESETTINGS-Befehls-ID](https://msdn.microsoft.com/library/aa769901.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetdesignmodea--chtmleditctrlbasesetdesignmode"></a><a name="setdesignmode"></a>CHtmlEditCtrlBase::SetDesignMode  
 Legen Sie im Entwurfsmodus.  
  
```  
BOOL SetDesignMode(BOOL bMode) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bMode`  
 Wenn true, wird im Entwurfsmodus aktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="a-namesetdisableeditfocusuia--chtmleditctrlbasesetdisableeditfocusui"></a><a name="setdisableeditfocusui"></a>CHtmlEditCtrlBase::SetDisableEditFocusUI  
 Deaktiviert den schraffierten Rahmen und behandelt werden, um ein Element aus, bearbeiten den Fokus besitzt.  
  
```  
HRESULT SetDisableEditFocusUI(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Bei "true" wird schraffierten Rahmen und Handles, um eine Website auswählbare Element deaktiviert, wenn das Element im Entwurfsmodus ist "Fokus bearbeiten"; d. h., wenn die Text oder den Inhalt des Elements bearbeitet werden können.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM_DISABLE_EDITFOCUS_UI-Befehls-ID](https://msdn.microsoft.com/library/aa769905.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetdocumenthtmla--chtmleditctrlbasesetdocumenthtml"></a><a name="setdocumenthtml"></a>CHtmlEditCtrlBase::SetDocumentHTML  
 Legt den HTML-Code des aktuellen Dokuments.  
  
```  
HRESULT SetDocumentHTML(LPCTSTR szHTML) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szHTML`  
 Der HTML-Code.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namesetfontfacea--chtmleditctrlbasesetfontface"></a><a name="setfontface"></a>CHtmlEditCtrlBase::SetFontFace  
 Legt die Schriftart für die aktuelle Auswahl fest.  
  
```  
HRESULT SetFontFace(LPCTSTR szFace) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szFace`  
 Der Name der Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM FONTNAME-Befehls-ID](https://msdn.microsoft.com/library/aa769880.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetfontsizea--chtmleditctrlbasesetfontsize"></a><a name="setfontsize"></a>CHtmlEditCtrlBase::SetFontSize  
 Legt den Schriftgrad für die aktuelle Auswahl fest.  
  
```  
HRESULT SetFontSize(unsigned short size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Der HTML-Schriftgrad (1 bis&7;). Der Wert 0 legt den Schriftgrad auf 1 fest.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM FONTSIZE-Befehls-ID](https://msdn.microsoft.com/library/aa769881.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetforecolora--chtmleditctrlbasesetforecolor"></a><a name="setforecolor"></a>CHtmlEditCtrlBase::SetForeColor  
 Legt die Vordergrundfarbe (Text) der aktuellen Auswahl fest.  
  
```  
HRESULT SetForeColor(LPCTSTR szColor) const;  
HRESULT SetForeColor(int nColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szColor`  
 Die Farbe.  
  
 `nColor`  
 Die Farbe.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM FORECOLOR-Befehls-ID](https://msdn.microsoft.com/library/aa769882.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetie5pastemodea--chtmleditctrlbasesetie5pastemode"></a><a name="setie5pastemode"></a>CHtmlEditCtrlBase::SetIE5PasteMode  
 Legt den Einfügevorgang mit Microsoft Internet Explorer 5 kompatibel.  
  
```  
HRESULT SetIE5PasteMode(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, werden alle Einfügevorgänge kompatibel mit Internet Explorer 5; Bei false sind Einfügevorgänge kompatibel mit Internet Explorer 5.5.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IE50_PASTE_MODE IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769923.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetliveresizea--chtmleditctrlbasesetliveresize"></a><a name="setliveresize"></a>CHtmlEditCtrlBase::SetLiveResize  
 Bewirkt, dass der WebBrowser zum Aktualisieren eines Elements Darstellung kontinuierlich während eines Vorgangs zum Ändern der Größe oder verschieben, anstatt nur nach Abschluss der Verschiebung aktualisieren oder dessen Größe ändern.  
  
```  
HRESULT SetLiveResize(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Bei "true" bewirkt, dass der WebBrowser, um ein Element Darstellung kontinuierlich während eines Vorgangs ändern der Größe oder verschieben zu aktualisieren. Bei false wird nur am Ende das Verschieben oder Ändern der Größe aktualisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [LIVERESIZE IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769928.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetmultiselecta--chtmleditctrlbasesetmultiselect"></a><a name="setmultiselect"></a>CHtmlEditCtrlBase::SetMultiSelect  
 Ermöglicht die Auswahl mehrerer Elemente.  
  
```  
HRESULT SetMultiSelect(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Bei "true" ermöglicht die Auswahl von mehr als ein Standort auswählbare Element zu einem Zeitpunkt, wenn der Benutzer Sie die Tasten UMSCHALT oder STRG gedrückt hält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MULTIPLESELECTION IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769929.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetoverridecursora--chtmleditctrlbasesetoverridecursor"></a><a name="setoverridecursor"></a>CHtmlEditCtrlBase::SetOverrideCursor  
 Befehle der WebBrowser nicht zum Ändern des Mauszeigers.  
  
```  
HRESULT SetOverrideCursor(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird der WebBrowser den Mauszeiger nicht geändert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [OVERRIDE_CURSOR IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769932.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetoverwritemodea--chtmleditctrlbasesetoverwritemode"></a><a name="setoverwritemode"></a>CHtmlEditCtrlBase::SetOverwriteMode  
 Schaltet zwischen der Eingabe von Text-Modus einfügen und überschreiben.  
  
```  
HRESULT SetOverwriteMode(bool bMode) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bMode`  
 Bei "true" Texteingabe Modus überschrieben werden; Bei "false" ist der Texteingabe Modus einfügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM ÜBERSCHREIBEN der Befehls-ID](https://msdn.microsoft.com/library/aa770016.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetrespectvisindesigna--chtmleditctrlbasesetrespectvisindesign"></a><a name="setrespectvisindesign"></a>CHtmlEditCtrlBase::SetRespectVisInDesign  
 Blendet die unsichtbare Elemente im Entwurfsmodus.  
  
```  
HRESULT SetRespectVisInDesign(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Bei "true" werden alle Elemente, die über eine Sichtbarkeit auf "hidden" festgelegt oder Anzeigen der Eigenschaft auf "none" festgelegt ist im Entwurfsmodus und Durchsuchen-Modus nicht angezeigt werden; Bei false werden diese Elemente nur im Durchsuchen-Modus angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [RESPECTVISIBILITY_INDESIGN IDM-Befehls-ID](https://msdn.microsoft.com/library/aa770023.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowalignedsitetagsa--chtmleditctrlbasesetshowalignedsitetags"></a><a name="setshowalignedsitetags"></a>CHtmlEditCtrlBase::SetShowAlignedSiteTags  
 Zeigt ein Symbol für alle Elemente, deren ein **StyleFloat** Eigenschaft.  
  
```  
HRESULT SetShowAlignedSiteTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird ein Symbol für alle Elemente, deren ein **StyleFloat** Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWALIGNEDSITETAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769947.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowalltagsa--chtmleditctrlbasesetshowalltags"></a><a name="setshowalltags"></a>CHtmlEditCtrlBase::SetShowAllTags  
 Zeigt die Symbole, die die Position von allen Tags in einem Dokument anzuzeigen.  
  
```  
HRESULT SetShowAllTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird die Symbole, um die Position aller Tags in einem Dokument anzuzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWALLTAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769948.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowareatagsa--chtmleditctrlbasesetshowareatags"></a><a name="setshowareatags"></a>CHtmlEditCtrlBase::SetShowAreaTags  
 Ein Symbol für die Bereich-Tags angezeigt.  
  
```  
HRESULT SetShowAreaTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird ein Symbol für die Bereich-Tags.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWAREATAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769949.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowbrtagsa--chtmleditctrlbasesetshowbrtags"></a><a name="setshowbrtags"></a>CHtmlEditCtrlBase::SetShowBRTags  
 Zeigt ein Symbol für alle Br-Tags.  
  
```  
HRESULT SetShowBRTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird ein Symbol für alle Br-Tags.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWWBRTAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769956.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowcommenttagsa--chtmleditctrlbasesetshowcommenttags"></a><a name="setshowcommenttags"></a>CHtmlEditCtrlBase::SetShowCommentTags  
 Zeigt ein Symbol für das Kommentar-Tags.  
  
```  
HRESULT SetShowCommentTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird ein Symbol für das Kommentar-Tags.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWCOMMENTTAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769950.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowmisctagsa--chtmleditctrlbasesetshowmisctags"></a><a name="setshowmisctags"></a>CHtmlEditCtrlBase::SetShowMiscTags  
 Zeigt alle Tags, die in Microsoft Internet Explorer 4.0 angezeigt.  
  
```  
HRESULT SetShowMiscTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Bei "true" zeigt alle Tags, die in Microsoft Internet Explorer 4.0 angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWMISCTAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769952.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowscripttagsa--chtmleditctrlbasesetshowscripttags"></a><a name="setshowscripttags"></a>CHtmlEditCtrlBase::SetShowScriptTags  
 Zeigt ein Symbol für die Script-Tags.  
  
```  
HRESULT SetShowScriptTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird ein Symbol für die Script-Tags.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWSCRIPTTAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769953.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowstyletagsa--chtmleditctrlbasesetshowstyletags"></a><a name="setshowstyletags"></a>CHtmlEditCtrlBase::SetShowStyleTags  
 Zeigt ein Symbol für alle Style-Tags.  
  
```  
HRESULT SetShowStyleTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird ein Symbol für alle Style-Tags.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWSTYLETAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769954.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-namesetshowunknowntagsa--chtmleditctrlbasesetshowunknowntags"></a><a name="setshowunknowntags"></a>CHtmlEditCtrlBase::SetShowUnknownTags  
 Zeigt ein Symbol für alle unbekannten Tags.  
  
```  
HRESULT SetShowUnknownTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wenn true, wird ein Symbol für alle unbekannten Tags.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SHOWUNKNOWNTAGS IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769955.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nametextareaa--chtmleditctrlbasetextarea"></a><a name="textarea"></a>CHtmlEditCtrlBase::TextArea  
 Überschreibt ein mehrzeiliges Textfeld Eingabesteuerelement für die aktuelle Auswahl.  
  
```  
HRESULT TextArea(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Eingabesteuerelements mehrzeiligen Textfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM TEXTAREA-Befehls-ID](https://msdn.microsoft.com/library/aa769986.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nametextboxa--chtmleditctrlbasetextbox"></a><a name="textbox"></a>CHtmlEditCtrlBase::TextBox  
 Überschreibt ein Textsteuerelement auf der aktuellen Auswahl.  
  
```  
HRESULT TextBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM TEXTBOX-Befehls-ID](https://msdn.microsoft.com/library/aa769980.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameunbookmarka--chtmleditctrlbaseunbookmark"></a><a name="unbookmark"></a>CHtmlEditCtrlBase::UnBookmark  
 Entfernt alle Lesezeichen aus der aktuellen Auswahl.  
  
```  
HRESULT UnBookmark() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [UNBOOKMARK IDM-Befehls-ID](https://msdn.microsoft.com/library/aa770034.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameunderlinea--chtmleditctrlbaseunderline"></a><a name="underline"></a>CHtmlEditCtrlBase::Underline  
 Schaltet die aktuelle Auswahl zwischen unterstrichen und nicht unterstrichen.  
  
```  
HRESULT Underline() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM UNTERSTREICHEN Befehls-ID](https://msdn.microsoft.com/library/aa770035.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameunlinka--chtmleditctrlbaseunlink"></a><a name="unlink"></a>CHtmlEditCtrlBase::Unlink  
 Entfernt alle Links aus der aktuellen Auswahl.  
  
```  
HRESULT Unlink() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [IDM Aufheben der Befehls-ID](https://msdn.microsoft.com/library/aa770037.aspx) an das WebBrowser-Steuerelement.  
  
##  <a name="a-nameunorderlista--chtmleditctrlbaseunorderlist"></a><a name="unorderlist"></a>CHtmlEditCtrlBase::UnorderList  
 Schaltet die aktuelle Auswahl zwischen einer geordneten Liste und einem Standardformat-Block.  
  
```  
HRESULT UnorderList(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die ID der ungeordnete Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [UNORDERLIST IDM-Befehls-ID](https://msdn.microsoft.com/library/aa769987.aspx) an das WebBrowser-Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [HTMLEdit-Beispiel](../../visual-cpp-samples.md)


