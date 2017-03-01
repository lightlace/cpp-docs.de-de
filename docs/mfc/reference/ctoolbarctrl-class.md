---
title: CToolBarCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class
- Windows common controls [C++], CToolBarCtrl
- toolbar controls [MFC], CToolBarCtrl class
- tool tips [C++], notifications
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
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
ms.openlocfilehash: 2d3ec23d6147299d9a615e9edb0d3f90680bbfac
ms.lasthandoff: 02/24/2017

---
# <a name="ctoolbarctrl-class"></a>CToolBarCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Symbolleisten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolBarCtrl::CToolBarCtrl](#ctoolbarctrl)|Erstellt ein `CToolBarCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolBarCtrl::AddBitmap](#addbitmap)|Die Liste der Bilder für Symbolleisten-Steuerelement hinzugefügt ein oder mehrere Abbilder von Bitmap-Schaltfläche.|  
|[CToolBarCtrl::AddButtons](#addbuttons)|Fügt eine oder mehrere Schaltflächen zu einem Toolbar-Steuerelement.|  
|[CToolBarCtrl::AddString](#addstring)|Fügt eine neue Zeichenfolge, die als eine Ressourcen-ID, der Symbolleiste auf die interne Liste mit Zeichenfolgen übergeben.|  
|[CToolBarCtrl::AddStrings](#addstrings)|Fügt eine neue Zeichenfolge oder Zeichenfolgen, die als Zeiger auf einen Puffer mit Null getrennte Zeichenfolgen, der Symbolleiste auf die interne Liste mit Zeichenfolgen übergeben.|  
|[CToolBarCtrl::AutoSize](#autosize)|Ändert die Größe eines Symbolleisten-Steuerelements.|  
|[CToolBarCtrl::ChangeBitmap](#changebitmap)|Ändert die Bitmap für eine Schaltfläche in der aktuellen Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::CheckButton](#checkbutton)|Überprüft oder löscht eine bestimmte Schaltfläche in einem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::CommandToIndex](#commandtoindex)|Ruft den nullbasierten Index für die Schaltfläche mit der angegebenen Befehls-ID ab.|  
|[CToolBarCtrl::Create](#create)|Erstellt eine Symbolleisten-Steuerelement und fügt es ein `CToolBarCtrl` Objekt.|  
|[CToolBarCtrl::CreateEx](#createex)|Erstellt eine Symbolleisten-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CToolBarCtrl` Objekt.|  
|[CToolBarCtrl::Customize](#customize)|Zeigt das Dialogfeld Symbolleiste anpassen.|  
|[CToolBarCtrl::DeleteButton](#deletebutton)|Löscht eine Schaltfläche aus dem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::EnableButton](#enablebutton)|Aktiviert oder deaktiviert die angegebene Schaltfläche in einem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::GetAnchorHighlight](#getanchorhighlight)|Ruft die Anker Hervorhebung für eine Symbolleiste festlegen.|  
|[CToolBarCtrl::GetBitmap](#getbitmap)|Ruft den Index der Bitmap eine Schaltfläche in einer Symbolleiste zugeordnet.|  
|[CToolBarCtrl::GetBitmapFlags](#getbitmapflags)|Ruft die Flags der Symbolleistenbitmap zugeordnet sind.|  
|[CToolBarCtrl::GetButton](#getbutton)|Ruft Informationen über die angegebene Schaltfläche in einem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::GetButtonCount](#getbuttoncount)|Ruft die Anzahl der Schaltflächen derzeit in der Symbolleisten-Steuerelement ab.|  
|[CToolBarCtrl::GetButtonInfo](#getbuttoninfo)|Ruft die Informationen für eine Schaltfläche in einer Symbolleiste ab.|  
|[CToolBarCtrl::GetButtonSize](#getbuttonsize)|Ruft die aktuelle Breite und Höhe von Symbolleisten-Schaltflächen in Pixel.|  
|[CToolBarCtrl::GetColorScheme](#getcolorscheme)|Ruft das Farbschema des aktuellen Symbolleisten-Steuerelements ab.|  
|[CToolBarCtrl::GetDisabledImageList](#getdisabledimagelist)|Ruft die Bildliste, die Symbolleisten-Steuerelement für den Anzeigeschaltflächen deaktiviert verwendet.|  
|[CToolBarCtrl::GetDropTarget](#getdroptarget)|Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle für eine Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile für eine Symbolleisten-Steuerelement ab.|  
|[CToolBarCtrl::GetHotImageList](#gethotimagelist)|Ruft die Bildliste, die einem Symbolleisten-Steuerelement verwendet wird, um "heißen" Schaltflächen angezeigt. Eine aktive Schaltfläche wird hervorgehoben, wenn der Mauszeiger darüber befindet.|  
|[CToolBarCtrl::GetHotItem](#gethotitem)|Ruft den Index für das Element in einer Symbolleiste ab.|  
|[CToolBarCtrl::GetImageList](#getimagelist)|Ruft die Bildliste, die einem Symbolleisten-Steuerelement verwendet wird, um die Schaltflächen im Standardzustand angezeigt.|  
|[CToolBarCtrl::GetInsertMark](#getinsertmark)|Ruft die aktuellen Einfügemarke für die Symbolleiste ab.|  
|[CToolBarCtrl::GetInsertMarkColor](#getinsertmarkcolor)|Ruft die Farbe verwendet, um die Einfügemarke für die Symbolleiste Zeichnen.|  
|[CToolBarCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck einer Schaltfläche in einem Symbolleisten-Steuerelement ab.|  
|[CToolBarCtrl::GetMaxSize](#getmaxsize)|Ruft die Gesamtgröße aller sichtbaren Schaltflächen und Trennzeichen auf der Symbolleiste ab.|  
|[CToolBarCtrl::GetMaxTextRows](#getmaxtextrows)|Ruft die maximale Anzahl von Textzeilen auf eine Symbolleisten-Schaltfläche angezeigt.|  
|[CToolBarCtrl::GetMetrics](#getmetrics)|Ruft die Metrik der Symbolleisten-Steuerelement ab.|  
|[CToolBarCtrl::GetPadding](#getpadding)|Ruft den horizontalen und vertikalen Abstand des aktuellen Symbolleisten-Steuerelements ab.|  
|[CToolBarCtrl::GetPressedImageList](#getpressedimagelist)|Ruft die Bildliste, die das aktuellen Symbolleisten-Steuerelement verwendet wird, um die Darstellung von Schaltflächen im gedrückten Zustand.|  
|[CToolBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck für eine angegebene Symbolleisten-Schaltfläche.|  
|[CToolBarCtrl::GetRows](#getrows)|Ruft die Anzahl der Zeilen von Schaltflächen, die momentan in der Symbolleiste angezeigt.|  
|[CToolBarCtrl::GetState](#getstate)|Ruft Informationen über den Zustand der angegebenen Schaltfläche in einem Symbolleisten-Steuerelement, z. B., ob es aktiviert, gedrückt oder aktiviert wird, ab.|  
|[CToolBarCtrl::GetString](#getstring)|Ruft eine Zeichenfolge für die Symbolleiste.|  
|[CToolBarCtrl::GetStyle](#getstyle)|Ruft die Stile aktuell in Verwendung für eine Symbolleisten-Steuerelement ab.|  
|[CToolBarCtrl::GetToolTips](#gettooltips)|Ruft ab das Handle für das QuickInfo-Steuerelement, vorhanden, die dem Symbolleisten-Steuerelement zugeordnet.|  
|[CToolBarCtrl::HideButton](#hidebutton)|Blendet oder die angegebene Schaltfläche in einem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::HitTest](#hittest)|Bestimmt, in dem ein Punkt in einem Symbolleisten-Steuerelement liegt.|  
|[CToolBarCtrl::Indeterminate](#indeterminate)|Aktiviert oder deaktiviert (grauen) unbestimmten Zustand der angegebenen Schaltfläche in einem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::InsertButton](#insertbutton)|Fügt eine Schaltfläche in einem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::InsertMarkHitTest](#insertmarkhittest)|Ruft die einfügen-Mark-Informationen für einen Punkt in einer Symbolleiste ab.|  
|[CToolBarCtrl::IsButtonChecked](#isbuttonchecked)|Erfahren Sie, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement aktiviert ist.|  
|[CToolBarCtrl::IsButtonEnabled](#isbuttonenabled)|Erfahren Sie, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement aktiviert ist.|  
|[CToolBarCtrl::IsButtonHidden](#isbuttonhidden)|Erfahren Sie, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement ausgeblendet ist.|  
|[CToolBarCtrl::IsButtonHighlighted](#isbuttonhighlighted)|Überprüft den Status der Hervorhebung der Symbolleisten-Schaltfläche.|  
|[CToolBarCtrl::IsButtonIndeterminate](#isbuttonindeterminate)|Erfahren Sie, ob der Status der angegebenen Schaltfläche in einem Symbolleisten-Steuerelement unbestimmt (grau) ist.|  
|[CToolBarCtrl::IsButtonPressed](#isbuttonpressed)|Erfahren Sie, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement geklickt wird.|  
|[CToolBarCtrl::LoadImages](#loadimages)|Bitmaps in einem Symbolleisten-Steuerelement Bildliste geladen.|  
|[CToolBarCtrl::MapAccelerator](#mapaccelerator)|Ordnet eine Zugriffstaste Zeichen eine Symbolleisten-Schaltfläche.|  
|[CToolBarCtrl::MarkButton](#markbutton)|Legt den Status markieren Sie eine der vorhandenen Schaltflächen in einem Symbolleisten-Steuerelement fest.|  
|[CToolBarCtrl::MoveButton](#movebutton)|Verschiebt eine Schaltfläche aus einem Index.|  
|[CToolBarCtrl::PressButton](#pressbutton)|Drückt, oder die angegebene Schaltfläche in einem Symbolleisten-Steuerelement frei.|  
|[CToolBarCtrl::ReplaceBitmap](#replacebitmap)|Ersetzt den vorhandene Bitmap in der aktuellen Symbolleisten-Steuerelement mit einer neuen Bitmap.|  
|[CToolBarCtrl::RestoreState](#restorestate)|Hiermit wird der Status des Symbolleisten-Steuerelements.|  
|[CToolBarCtrl::SaveState](#savestate)|Speichert den Zustand des Symbolleisten-Steuerelements.|  
|[CToolBarCtrl::SetAnchorHighlight](#setanchorhighlight)|Legt die Anker Hervorhebung für eine Symbolleiste festlegen.|  
|[CToolBarCtrl::SetBitmapSize](#setbitmapsize)|Legt die Größe der Bitmapbilder in einem Symbolleisten-Steuerelement hinzugefügt werden.|  
|[CToolBarCtrl::SetButtonInfo](#setbuttoninfo)|Die Informationen für eine vorhandene Schaltfläche fest in einer Symbolleiste.|  
|[CToolBarCtrl::SetButtonSize](#setbuttonsize)|Legt die Größe der Schaltflächen zu einem Toolbar-Steuerelement hinzugefügt werden.|  
|[CToolBarCtrl::SetButtonStructSize](#setbuttonstructsize)|Gibt die Größe der `TBBUTTON` Struktur.|  
|[CToolBarCtrl::SetButtonWidth](#setbuttonwidth)|Legt die minimale und maximale Schaltfläche breiten in dem Symbolleisten-Steuerelement fest.|  
|[CToolBarCtrl::SetCmdID](#setcmdid)|Legt die Befehls-ID an das Besitzerfenster gesendet werden, wenn die angegebene Schaltfläche gedrückt wird.|  
|[CToolBarCtrl::SetColorScheme](#setcolorscheme)|Legt das Farbschema des aktuellen Symbolleisten-Steuerelements fest.|  
|[CToolBarCtrl::SetDisabledImageList](#setdisabledimagelist)|Legt die Liste der Images, die das Symbolleisten-Steuerelement verwenden auf Anzeigeschaltflächen deaktiviert fest.|  
|[CToolBarCtrl::SetDrawTextFlags](#setdrawtextflags)|Legt die Flags in der Win32-Funktion [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), dient zum Zeichnen von Text in das angegebene Rechteck, formatiert, wie die Flags festgelegt sind.|  
|[CToolBarCtrl::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile für eine Symbolleisten-Steuerelement fest.|  
|[CToolBarCtrl::SetHotImageList](#sethotimagelist)|Legt die Liste der Images, die das Symbolleisten-Steuerelement verwenden "heiße" Schaltflächen angezeigt.|  
|[CToolBarCtrl::SetHotItem](#sethotitem)|Legt das Element in einer Symbolleiste.|  
|[CToolBarCtrl:: SetImageList](#setimagelist)|Legt die Liste der Images, die mithilfe der Symbolleiste Schaltflächen anzuzeigen, die in ihren Standardzustand zurückgesetzt werden.|  
|[CToolBarCtrl::SetIndent](#setindent)|Legt den Einzug für die erste Schaltfläche in einem Symbolleisten-Steuerelement fest.|  
|[CToolBarCtrl::SetInsertMark](#setinsertmark)|Legt die aktuelle Einfügemarke für die Symbolleiste.|  
|[CToolBarCtrl::SetInsertMarkColor](#setinsertmarkcolor)|Wird verwendet, um die Einfügemarke für die Symbolleiste Zeichnen.|  
|[CToolBarCtrl::SetMaxTextRows](#setmaxtextrows)|Legt die maximale Anzahl von Textzeilen auf eine Symbolleisten-Schaltfläche angezeigt.|  
|[CToolBarCtrl::SetMetrics](#setmetrics)|Legt die Metrik der Symbolleisten-Steuerelement fest.|  
|[CToolBarCtrl::SetOwner](#setowner)|Das Fenster zum Empfangen von Nachrichten aus dem Symbolleisten-Steuerelement festgelegt.|  
|[CToolBarCtrl::SetPadding](#setpadding)|Legt den horizontalen und vertikalen Abstand des aktuellen Symbolleisten-Steuerelements fest.|  
|[CToolBarCtrl::SetPressedImageList](#setpressedimagelist)|Legt die Liste der Images, die das aktuellen Symbolleisten-Steuerelement verwendet wird, um die Darstellung von Schaltflächen im gedrückten Zustand.|  
|[CToolBarCtrl::SetRows](#setrows)|Legt die Anzahl der Zeilen von Schaltflächen auf der Symbolleiste angezeigt.|  
|[CToolBarCtrl::SetState](#setstate)|Legt den Status für die angegebene Schaltfläche in einem Symbolleisten-Steuerelement fest.|  
|[CToolBarCtrl::SetStyle](#setstyle)|Legt die Stile für eine Symbolleisten-Steuerelement fest.|  
|[CToolBarCtrl::SetToolTips](#settooltips)|Ordnet ein QuickInfo-Steuerelement mit dem Symbolleisten-Steuerelement.|  
|[CToolBarCtrl::SetWindowTheme](#setwindowtheme)|Legt fest, der die visuelle Darstellung eines Symbolleisten-Steuerelements.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Steuerelement (und somit die `CToolBarCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Ein allgemeine Windows-Symbolleisten-Steuerelement ist ein rechteckiges untergeordnetes Fenster, das eine oder mehrere Schaltflächen enthält. Diese Schaltflächen können ein Bitmap-Bild, eine Zeichenfolge oder beides anzeigen. Wenn der Benutzer eine Schaltfläche auswählt, sendet er eine Befehlsnachricht an Besitzerfenster der Symbolleiste. In der Regel entsprechen die Schaltflächen in einer Symbolleiste Elementen im Menü der Anwendung; Sie bieten eine direktere Möglichkeit für den Benutzer auf die Befehle einer Anwendung zuzugreifen.  
  
 `CToolBarCtrl`-Objekte enthalten verschiedene wichtige interne Datenstrukturen: eine Liste von Bitmaps für Schaltflächen Abbild oder einer Bildliste, eine Liste der Schaltfläche Label-Zeichenfolgen und eine Liste der `TBBUTTON` Strukturen, die ein Bild zuordnen und/oder eine Zeichenfolge mit der Position, Stil, Status und Befehls-ID der Schaltfläche. Jedes Element dieser Datenstrukturen wird durch einen nullbasierten Index bezeichnet. Vor der Verwendung einer `CToolBarCtrl` Objekt ist, müssen Sie diese Datenstrukturen einrichten. Die Liste der Zeichenfolgen kann nur für schaltflächenbeschriftungen verwendet werden. Zeichenfolgen können über die Symbolleiste kann nicht abgerufen werden.  
  
 Verwenden einer `CToolBarCtrl` -Objekt, Sie werden in der Regel gehen Sie folgendermaßen vor:  
  
1.  Erstellen der `CToolBarCtrl` Objekt.  
  
2.  Rufen Sie [erstellen](#create) allgemeine Symbolleisten-Steuerelement von Windows zu erstellen und diese an die `CToolBarCtrl` Objekt. Angeben von Symbolleisten des Formats von Stilen, wie z. B. **TBSTYLE_TRANSPARENT** für eine transparente Symbolleiste oder **TBSTYLE_DROPDOWN** für eine Symbolleiste, die Dropdown Schaltflächen unterstützt.  
  
3.  Identifizieren Sie, wie die Schaltflächen auf der Symbolleiste angezeigt werden sollen:  
  
    -   Um Bitmaps für Schaltflächen zu verwenden, fügen Sie die Bitmaps für Schaltflächen auf der Symbolleiste durch Aufrufen von [AddBitmap](#addbitmap).  
  
    -   Um aus einer Bildliste für Schaltflächen angezeigten Bilder zu verwenden, geben Sie die Bildliste durch Aufrufen von [SetImageList](#setimagelist), [SetHotImageList](#sethotimagelist), oder [SetDisabledImageList](#setdisabledimagelist).  
  
    -   Um Zeichenfolge Bezeichnungen für Schaltflächen zu verwenden, fügen Sie die Zeichenfolgen auf der Symbolleiste durch Aufrufen von [AddString](#addstring) und/oder [AddStrings](#addstrings).  
  
4.  Fügen Sie der Symbolleiste durch Aufrufen von [AddButtons](#addbuttons).  
  
5.  Wenn Sie QuickInfos für eine Symbolleisten-Schaltfläche in einem Besitzerfenster möchten, die keine `CFrameWnd`, behandelt werden müssen die **TTN_NEEDTEXT** Nachrichten in der Symbolleiste des Besitzerfensters, wie in beschrieben [Behandlung von Tool Tipp Benachrichtigungen](../../mfc/handling-tool-tip-notifications.md). Wenn das übergeordnete Fenster der Symbolleiste von abgeleitet ist `CFrameWnd`, QuickInfos werden ohne jegliche zusätzliche Anstrengung von Ihnen angezeigt, da `CFrameWnd` stellt einen Standardhandler.  
  
6.  Ihre Benutzer zum Anpassen der Symbolleiste kann gegebenenfalls Anpassung Benachrichtigungsnachrichten in das Besitzerfenster behandeln, wie in beschrieben [Behandeln von Anpassungsbenachrichtigungen](../../mfc/handling-customization-notifications.md).  
  
 Können [SaveState](#savestate) den aktuellen Status des Symbolleisten-Steuerelements in der Registrierung gespeichert und [RestoreState](#restorestate) zur Wiederherstellung des Zustands basierend auf Informationen, die zuvor in der Registrierung gespeichert. Zusätzlich zum Speichern des Zustands der Symbolleiste zwischen der Anwendung verwendet, Anwendungen in der Regel den Zustand speichern, bevor der Benutzer beginnt, Anpassen der Symbolleiste für den Fall, dass der Benutzer später auf den ursprünglichen Zustand die Symbolleiste wiederherstellen möchte.  
  
## <a name="support-for-internet-explorer-version-40-and-later"></a>Unterstützung für Internet Explorer-Version 4.0 und höher  
 Zur Unterstützung von Funktionen in Internet Explorer, Version 4.0 und höher, stellt MFC Bildlisten unterstützt und transparent und Flatfile-Formate für Symbolleisten-Steuerelemente bereit.  
  
 Eine transparente Symbolleiste kann der Client unter der Symbolleiste sichtbar. Verwenden Sie zum Erstellen einer transparenten Symbolleiste beide **TBSTYLE_FLAT** und **TBSTYLE_TRANSPARENT** Formate. Transparente Symbolleisten Features hot Track. d.h., wenn der Mauszeiger über eine aktive Schaltfläche auf der Symbolleiste bewegt wird, die Darstellung der Schaltfläche ändert sich. Symbolleisten mit erstellt lediglich die **TBSTYLE_FLAT** Stil enthält Schaltflächen, die nicht transparent sind.  
  
 Bildlisten unterstützt Flexibilität ein Steuerelement größere für Standardverhalten hot Bilder und Bilder deaktiviert. Verwendung [Memberfunktion GetImageList](#getimagelist), [GetHotImageList](#gethotimagelist), und [GetDisabledImageList](#getdisabledimagelist) mit der transparenten Symbolleiste aus, um das Bild entsprechend seinem Zustand zu verändern:  
  
 Weitere Informationen zur Verwendung von `CToolBarCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CToolBarCtrl](../../mfc/using-ctoolbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-nameaddbitmapa--ctoolbarctrladdbitmap"></a><a name="addbitmap"></a>CToolBarCtrl::AddBitmap  
 Die Liste der Bilder gespeichert werden, in dem Symbolleisten-Steuerelement hinzugefügt ein oder mehrere Bilder.  
  
```  
int AddBitmap(
    int nNumButtons,  
    UINT nBitmapID);

 
int AddBitmap(
    int nNumButtons,  
    CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `nNumButtons`  
 Anzahl der Bilder in der Bitmap.  
  
 `nBitmapID`  
 Der Ressourcenbezeichner der Bitmap, die das Schaltflächenbild oder Bilder hinzufügen.  
  
 `pBitmap`  
 Zeiger auf die `CBitmap` -Objekt, enthält das Schaltflächenbild oder Bilder hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des ersten neuen Bilds, wenn erfolgreich; andernfalls – 1.  
  
### <a name="remarks"></a>Hinweise  
 Sie können mithilfe der Windows-API [CreateMappedBitmap](http://msdn.microsoft.com/library/windows/desktop/bb787467) Farben zuordnen, bevor die Bitmap zur Symbolleiste hinzufügen. Wenn Sie übergeben, einen Zeiger auf eine **CBitMap** Objekt ist, müssen Sie sicherstellen, dass die Bitmap nicht erst zerstört wird, nachdem die Symbolleiste zerstört wird.  
  
##  <a name="a-nameaddbuttonsa--ctoolbarctrladdbuttons"></a><a name="addbuttons"></a>CToolBarCtrl::AddButtons  
 Fügt eine oder mehrere Schaltflächen zu einem Toolbar-Steuerelement.  
  
```  
BOOL AddButtons(
    int nNumButtons,  
    LPTBBUTTON lpButtons);
```  
  
### <a name="parameters"></a>Parameter  
 `nNumButtons`  
 Anzahl der Schaltflächen hinzufügen.  
  
 `lpButtons`  
 Die Adresse eines Arrays von `TBBUTTON` -Strukturen, die Informationen über die hinzuzufügenden Schaltflächen enthält. Es muss die gleiche Anzahl von Elementen im Array als den angegebenen Schaltflächen `nNumButtons`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpButtons` Zeiger zeigt auf ein Array von `TBBUTTON` Strukturen. Jede `TBBUTTON` Struktur ordnet die Schaltfläche mit der Schaltfläche Style-Abbild und/oder Zeichenfolge, Befehls-ID, Status und benutzerdefinierte Daten hinzugefügt wird:  
  
 `typedef struct _TBBUTTON {`  
  
 `int iBitmap;// zero-based index of button image`  
  
 `int idCommand;  // command to be sent when button pressed`  
  
 `BYTE fsState;   // button state--see below`  
  
 `BYTE fsStyle;   // button style--see below`  
  
 `DWORD dwData;   // application-defined value`  
  
 `int iString;// zero-based index of button label string`  
  
 `} TBBUTTON;`  
  
 Die Elemente werden wie folgt:  
  
 **iBitmap**  
 Nullbasierte Index des Bildes für&1;, wenn kein Bild für diese Schaltfläche.  
  
 **idCommand**  
 Befehl Bezeichner der Schaltfläche zugeordnet. Dieser Bezeichner wird gesendet, einer **WM_COMMAND** angezeigt, wenn die Schaltfläche ausgewählt wird. Wenn die **FsStyle** Element verfügt über die `TBSTYLE_SEP` Wert dieses Elements muss NULL sein.  
  
 **fsState**  
 Schaltfläche Status-Flags. Es kann eine Kombination der unten aufgeführten Werte sein:  
  
- `TBSTATE_CHECKED`Die Schaltfläche der **TBSTYLE_CHECKED** formatieren und gedrückt wird.  
  
- `TBSTATE_ENABLED`Die Schaltfläche akzeptiert Benutzereingaben. Eine Schaltfläche, die diesem Zustand nicht akzeptiert keine Benutzereingaben und ist deaktiviert.  
  
- `TBSTATE_HIDDEN`Die Schaltfläche ist nicht sichtbar und Eingaben.  
  
- `TBSTATE_INDETERMINATE`Die Schaltfläche ist abgeblendet.  
  
- `TBSTATE_PRESSED`Die Schaltfläche wird gedrückt wird.  
  
- `TBSTATE_WRAP`Ein Zeilenumbruch folgt auf die Schaltfläche. Die Schaltfläche müssen die `TBSTATE_ENABLED` Zustand.  
  
 **fsStyle**  
 Schaltflächen-Formatvorlage. Es kann eine Kombination der unten aufgeführten Werte sein:  
  
- `TBSTYLE_BUTTON`Erstellt eine Standardschaltflächen.  
  
- `TBSTYLE_CHECK`Erstellt eine Schaltfläche, die zwischen den Zuständen gedrückten und nicht gedrückt jedes Mal wechselt der Benutzer darauf klickt. Die Schaltfläche hat eine andere Hintergrundfarbe, wenn es im gedrückten Zustand ist.  
  
- `TBSTYLE_CHECKGROUP`Erstellt eine Kontrollkästchen-Schaltfläche, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe gedrückt wird.  
  
- `TBSTYLE_GROUP`Erstellt eine Schaltfläche, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe gedrückt wird.  
  
- `TBSTYLE_SEP`Erstellt ein Trennzeichen, eine kleine zeitliche Lücke zwischen Schaltflächengruppen bereitstellen. Eine Schaltfläche mit diesem Format erhält keine Benutzereingaben.  
  
 `dwData`  
 Benutzerdefinierte Daten.  
  
 **iString**  
 Nullbasierte Index der Zeichenfolge, die als Schaltfläche verwendet der beschriften,&1;, wenn keine Zeichenfolge für diese Schaltfläche vorhanden ist.  
  
 Das Bild und/oder die Zeichenfolge, deren Index, die Sie bereitstellen zuvor worden sein, des Symbolleisten-Steuerelements hinzugefügt muss, auflisten mithilfe der [AddBitmap](#addbitmap), [AddString](#addstring), und/oder [AddStrings](#addstrings).  
  
##  <a name="a-nameaddstringa--ctoolbarctrladdstring"></a><a name="addstring"></a>CToolBarCtrl::AddString  
 Fügt eine neue Zeichenfolge, die als eine Ressourcen-ID, der Symbolleiste auf die interne Liste mit Zeichenfolgen übergeben.  
  
```  
int AddString(UINT nStringID);
```  
  
### <a name="parameters"></a>Parameter  
 *nStringID*  
 Der Ressourcenbezeichner der Zeichenfolgenressource Zeichenfolgenliste für das Symbolleisten-Steuerelement hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der ersten neuen Zeichenfolge hinzugefügt, falls erfolgreich. andernfalls-1.  
  
##  <a name="a-nameaddstringsa--ctoolbarctrladdstrings"></a><a name="addstrings"></a>CToolBarCtrl::AddStrings  
 Fügt eine neue Zeichenfolge oder Zeichenfolgen in die Liste der Zeichenfolgen für eine Symbolleisten-Steuerelement verfügbar.  
  
```  
int AddStrings(LPCTSTR lpszStrings);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszStrings*  
 Die Adresse eines Puffers, der ein oder mehrere Null-terminierte Zeichenfolgen Zeichenfolgenliste der Symbolleiste hinzu. Die letzte Zeichenfolge muss mit zwei Null-Zeichen beendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der ersten neuen Zeichenfolge hinzugefügt, falls erfolgreich. andernfalls-1.  
  
### <a name="remarks"></a>Hinweise  
 Zeichenfolgen in den Puffer müssen durch ein Null-Zeichen getrennt werden. Sie müssen sicherstellen, dass die letzte Zeichenfolge zwei null-Terminatoren sind. Um eine Konstante Zeichenfolge ordnungsgemäß zu formatieren, können Sie es als schreiben:  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#72;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_1.cpp)]  
  
 oder:  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#73;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_2.cpp)]  
  
 Sie übergeben ein `CString` Objekt, das diese Funktion, da es nicht möglich, dass mehrere Null-Zeichen eine `CString`.  
  
##  <a name="a-nameautosizea--ctoolbarctrlautosize"></a><a name="autosize"></a>CToolBarCtrl::AutoSize  
 Ändert die Größe der gesamten Toolbar-Steuerelement.  
  
```  
void AutoSize();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten diese Funktion aufrufen, wenn die Größe des übergeordneten Fensters geändert wird oder wenn die Größe der Symbolleiste geändert wird (z. B. Wenn Sie die Größe der Schaltfläche oder Bitmap oder Zeichenfolgen hinzugefügt).  
  
##  <a name="a-namechangebitmapa--ctoolbarctrlchangebitmap"></a><a name="changebitmap"></a>CToolBarCtrl::ChangeBitmap  
 Ändert die Bitmap für eine Schaltfläche in der aktuellen Symbolleisten-Steuerelement.  
  
```  
BOOL ChangeBitmap(
    int idButton,   
    int iBitmap);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `idButton`|Befehl Bezeichner der Schaltfläche, die eine neue Bitmap zu erhalten.|  
|[in] `iBitmap`|Nullbasierte Index eines Bildes in der Bildliste für das aktuelle Symbolleisten-Steuerelement.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode erfolgreich ist, zeigt das System das angegebene Bild in die angegebene Schaltfläche.  
  
 Diese Methode sendet die [TB_CHANGEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787301) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Bitmap für die **speichern** Schaltfläche, um die Bitmap für die **zu** Schaltfläche.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_3.cpp)]  
  
##  <a name="a-namecheckbuttona--ctoolbarctrlcheckbutton"></a><a name="checkbutton"></a>CToolBarCtrl::CheckButton  
 Überprüft oder löscht eine bestimmte Schaltfläche in einem Symbolleisten-Steuerelement.  
  
```  
BOOL CheckButton(
    int nID,  
    BOOL bCheck = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehl Bezeichner der Schaltfläche zum Aktivieren oder deaktivieren.  
  
 *bNeuere suchen*  
 **True,** auf die Schaltfläche überprüfen **FALSE** zu deaktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Schaltfläche aktiviert wurde, scheint es gedrückt wurden. Wenn Sie mehr als eine Schaltflächenstatus ändern möchten, sollten Sie aufrufen [SetState](#setstate) stattdessen.  
  
##  <a name="a-namecommandtoindexa--ctoolbarctrlcommandtoindex"></a><a name="commandtoindex"></a>CToolBarCtrl::CommandToIndex  
 Ruft den nullbasierten Index für die Schaltfläche mit der angegebenen Befehls-ID ab.  
  
```  
UINT CommandToIndex(UINT nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehls-ID, deren Schaltfläche index, dem Sie, suchen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index für die Schaltfläche mit den Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecreatea--ctoolbarctrlcreate"></a><a name="create"></a>CToolBarCtrl::Create  
 Erstellt eine Symbolleisten-Steuerelement und fügt es ein `CToolBarCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Symbolleisten-Steuerelement-Stil. Symbolleisten müssen immer die **WS_CHILD** Stil. Darüber hinaus können Sie eine beliebige Kombination von Toolbar-Stile und Fensterstile angeben, wie unter beschrieben **Hinweise**.  
  
 `rect`  
 Gibt optional, Größe und Position der Symbolleisten-Steuerelement. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt das Symbolleisten-Steuerelement des übergeordneten Fensters. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Symbolleisten-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie eine `CToolBarCtrl` in zwei Schritten. Zuerst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die das Symbolleisten-Steuerelement erstellt, und fügt es der `CToolBarCtrl` Objekt. Wenden Sie die folgenden Fensterstile zu einem Toolbar-Steuerelement.  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
 Finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Beschreibung der Fensterstile.  
  
 Wenden Sie optional eine Kombination von [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenden Sie eine Kombination von Toolbar-Stile auf das Steuerelement oder die Schaltflächen selbst. Die Stile werden in diesem Thema beschriebenen [Symbolleisten-Steuerelements und Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb760439) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Rufen Sie zum Verwenden der erweiterten Toolbar-Stile [SetExtendedStyle](#setextendedstyle) nach dem Aufruf von **erstellen**. Rufen Sie zum Erstellen einer Symbolleiste mit erweiterten Fensterstile [CToolBarCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
 Das Symbolleisten-Steuerelement legt automatisch die Größe und Position des Fensters Symbolleiste. Die Höhe basiert auf der Höhe der Schaltflächen auf der Symbolleiste. Die Breite entspricht der Breite des Clientbereichs des übergeordneten Fensters. Die `CCS_TOP` und `CCS_BOTTOM` Stile zu ermitteln, ob die Symbolleiste am oberen oder unteren Rand des Clientbereichs positioniert ist. Eine Symbolleiste verfügt standardmäßig über die `CCS_TOP` Stil.  
  
##  <a name="a-namecreateexa--ctoolbarctrlcreateex"></a><a name="createex"></a>CToolBarCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CToolBarCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Gibt das Symbolleisten-Steuerelement-Stil. Symbolleisten müssen immer die **WS_CHILD** Stil. Darüber hinaus können Sie eine beliebige Kombination von Toolbar-Stile und Fensterstile angeben, wie beschrieben in der **Hinweise** Abschnitt [erstellen](#create).  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**. **CreateEx** das Steuerelement erstellt, mit der erweiterten Fensterstile angegebenen `dwExStyle`. Gruppe, die erweiterten Stile, die spezifisch für ein Steuerelement mit [SetExtendedStyle](#setextendedstyle). Verwenden Sie z. B. `CreateEx` solche Stile als festlegen **WS_EX_CONTEXTHELP**, jedoch verwenden `SetExtendedStyle` solche Stile als festlegen **TBSTYLE_EX_DRAWDDARROWS**. Weitere Informationen finden Sie die Stile in der beschriebenen [Symbolleiste Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb760430) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namectoolbarctrla--ctoolbarctrlctoolbarctrl"></a><a name="ctoolbarctrl"></a>CToolBarCtrl::CToolBarCtrl  
 Erstellt ein `CToolBarCtrl`-Objekt.  
  
```  
CToolBarCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [erstellen](#create) auf die Symbolleiste verwendet werden kann.  
  
##  <a name="a-namecustomizea--ctoolbarctrlcustomize"></a><a name="customize"></a>CToolBarCtrl::Customize  
 Zeigt das Dialogfeld Symbolleiste anpassen.  
  
```  
void Customize();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld kann der Benutzer zum Anpassen der Symbolleiste durch Hinzufügen und Löschen von Schaltflächen. Zur Unterstützung der Anpassung muss übergeordneten Fenster der Symbolleiste Anpassung Benachrichtigung behandeln, wie in beschrieben [Behandeln von Anpassungsbenachrichtigungen](../../mfc/handling-customization-notifications.md). Die Symbolleiste muss auch mit erstellt wurden die `CCS_ADJUSTABLE` Format, wie in beschrieben [CToolBarCtrl::Create](#create).  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel Q241850: PRB: Aufruf von CToolBarCtrl::Customize behält keine anpassen Dialogfeld angezeigt.  
  
##  <a name="a-namedeletebuttona--ctoolbarctrldeletebutton"></a><a name="deletebutton"></a>CToolBarCtrl::DeleteButton  
 Löscht eine Schaltfläche aus dem Symbolleisten-Steuerelement.  
  
```  
BOOL DeleteButton(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index der Schaltfläche löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameenablebuttona--ctoolbarctrlenablebutton"></a><a name="enablebutton"></a>CToolBarCtrl::EnableButton  
 Aktiviert oder deaktiviert die angegebene Schaltfläche in einem Symbolleisten-Steuerelement.  
  
```  
BOOL EnableButton(
    int nID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehl Bezeichner der Schaltfläche zum Aktivieren oder deaktivieren.  
  
 `bEnable`  
 **True,** auf die Schaltfläche aktiviert ist; **FALSE** auf die Schaltfläche deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Schaltfläche aktiviert wurde, können Sie gedrückt und überprüft werden. Wenn Sie mehr als eine Schaltflächenstatus ändern möchten, sollten Sie aufrufen [SetState](#setstate) stattdessen.  
  
##  <a name="a-namegetanchorhighlighta--ctoolbarctrlgetanchorhighlight"></a><a name="getanchorhighlight"></a>CToolBarCtrl::GetAnchorHighlight  
 Ruft die Anker Hervorhebung für eine Symbolleiste festlegen.  
  
```  
BOOL GetAnchorHighlight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert ungleich NULL Anker Hervorhebung aktiviert ist. Wenn&0; (null), wird der Anker Hervorhebung deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787313), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbitmapa--ctoolbarctrlgetbitmap"></a><a name="getbitmap"></a>CToolBarCtrl::GetBitmap  
 Ruft den Index der Bitmap eine Schaltfläche in einer Symbolleiste zugeordnet.  
  
```  
int GetBitmap(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehl Bezeichner der Schaltfläche, deren Bitmapindex ist abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Index der Bitmap, falls erfolgreich, oder andernfalls NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert die Funktionalität eines [TB_GETBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787315) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbitmapflagsa--ctoolbarctrlgetbitmapflags"></a><a name="getbitmapflags"></a>CToolBarCtrl::GetBitmapFlags  
 Ruft die Bitmap-Flags aus der Symbolleiste ab.  
  
```  
UINT GetBitmapFlags() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **UINT** , bei dem die **TBBF_LARGE** -Flag festgelegt, wenn die Anzeige Bitmaps für große Symbolleisten, deaktivieren Sie andernfalls unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten nach dem Erstellen der Symbolleiste jedoch vor dem Hinzufügen von Bitmaps auf der Symbolleiste aufgerufen werden. Der Rückgabewert gibt an, ob die Anzeige große Bitmaps oder nicht unterstützt. Wenn die Anzeige große Bitmaps unterstützt und Sie diese verwenden, rufen Sie [SetBitmapSize](#setbitmapsize) und [SetButtonSize](#setbuttonsize) vor dem Hinzufügen der große Bitmap mit [AddBitmap](#addbitmap).  
  
##  <a name="a-namegetbuttona--ctoolbarctrlgetbutton"></a><a name="getbutton"></a>CToolBarCtrl::GetButton  
 Ruft Informationen über die angegebene Schaltfläche in einem Symbolleisten-Steuerelement.  
  
```  
BOOL GetButton(
    int nIndex,  
    LPTBBUTTON lpButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index der Schaltfläche für die Informationen abzurufen.  
  
 `lpButton`  
 Adresse der `TBBUTTON` -Struktur, die eine Kopie der Schaltflächeninformationen zu erhalten. Finden Sie unter [CToolBarCtrl::AddButtons](#addbuttons) Informationen zu den `TBBUTTON` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="a-namegetbuttoncounta--ctoolbarctrlgetbuttoncount"></a><a name="getbuttoncount"></a>CToolBarCtrl::GetButtonCount  
 Ruft die Anzahl der Schaltflächen derzeit in der Symbolleisten-Steuerelement ab.  
  
```  
int GetButtonCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Schaltflächen.  
  
##  <a name="a-namegetbuttoninfoa--ctoolbarctrlgetbuttoninfo"></a><a name="getbuttoninfo"></a>CToolBarCtrl::GetButtonInfo  
 Ruft die Informationen für eine Schaltfläche in einer Symbolleiste ab.  
  
```  
int GetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner der Schaltfläche.  
  
 `ptbbi`  
 Ein Zeiger auf eine [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) -Struktur, die die Schaltflächeninformationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Schaltfläche, wenn erfolgreich. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787321), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbuttonsizea--ctoolbarctrlgetbuttonsize"></a><a name="getbuttonsize"></a>CToolBarCtrl::GetButtonSize  
 Ruft die Größe einer Symbolleisten-Schaltfläche.  
  
```  
DWORD GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` -Wert, der die Breite und Höhe Werte im LOWORD und HIWORD, enthält.  
  
##  <a name="a-namegetbuttontexta--ctoolbarctrlgetbuttontext"></a><a name="getbuttontext"></a>CToolBarCtrl::GetButtonText  
 Ruft den Anzeigetext einer angegebenen Schaltfläche auf der aktuellen Symbolleisten-Steuerelement ab.  
  
```  
CString GetButtonText(int idButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `idButton`|Der Bezeichner für die Schaltfläche, deren Anzeigetext abgerufen wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/using-cstring.md) , der den Anzeigetext für die angegebene Schaltfläche enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TB_GETBUTTONTEXT](http://msdn.microsoft.com/library/windows/desktop/bb787325) -Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="a-namegetcolorschemea--ctoolbarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CToolBarCtrl::GetColorScheme  
 Ruft das Farbschema des aktuellen Symbolleisten-Steuerelements ab.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpColorScheme) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpColorScheme`|Zeiger auf eine [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) -Struktur, die die Farbe-Schema-Informationen erhält. Wenn diese Methode zurückgibt, beschreibt die Struktur die Hervorhebungsfarbe und Schattenfarbe des Symbolleisten-Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TB_GETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787327) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdisabledimagelista--ctoolbarctrlgetdisabledimagelist"></a><a name="getdisabledimagelist"></a>CToolBarCtrl::GetDisabledImageList  
 Ruft die Bildliste, die Symbolleisten-Steuerelement für den Anzeigeschaltflächen deaktiviert verwendet.  
  
```  
CImageList* GetDisabledImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, oder **NULL** Wenn keine deaktivierten Bildliste festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787329), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Die MFC-Implementierung von `GetDisabledImageList` verwendet ein `CImageList` Objekt mit dem Symbolleisten-Steuerelement Schaltfläche Bilder statt ein Handle zu einer Bildliste.  
  
##  <a name="a-namegetdroptargeta--ctoolbarctrlgetdroptarget"></a><a name="getdroptarget"></a>CToolBarCtrl::GetDropTarget  
 Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle für eine Symbolleisten-Steuerelement.  
  
```  
HRESULT GetDropTarget(IDropTarget** ppDropTarget) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppDropTarget`  
 Ein Zeiger auf eine [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) -Schnittstellenzeiger. Wenn ein Fehler auftritt, eine **NULL** Zeiger wird in dieser Adresse aufgenommen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `HRESULT` Wert, der Erfolg oder Misserfolg des Vorgangs.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787343), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetextendedstylea--ctoolbarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CToolBarCtrl::GetExtendedStyle  
 Ruft die erweiterten Stile für eine Symbolleisten-Steuerelement ab.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` , das die erweiterten Stile verwendet für das Symbolleisten-Steuerelement darstellt. Eine Liste der Formate, finden Sie unter [Symbolleiste Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb760430)in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787331), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegethotimagelista--ctoolbarctrlgethotimagelist"></a><a name="gethotimagelist"></a>CToolBarCtrl::GetHotImageList  
 Ruft die Bildliste, die einem Symbolleisten-Steuerelement verwendet wird, um "heißen" Schaltflächen angezeigt. Eine aktive Schaltfläche wird hervorgehoben, wenn der Mauszeiger darüber befindet.  
  
```  
CImageList* GetHotImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, oder **NULL** Wenn keine deaktivierten Bildliste festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787334)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Eine aktive Schaltfläche wird hervorgehoben, wenn der Mauszeiger darüber befindet.  
  
##  <a name="a-namegethotitema--ctoolbarctrlgethotitem"></a><a name="gethotitem"></a>CToolBarCtrl::GetHotItem  
 Ruft den Index für das Element in einer Symbolleiste ab.  
  
```  
int GetHotItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index, der das Element in einer Symbolleiste.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787336), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--ctoolbarctrlgetimagelist"></a><a name="getimagelist"></a>CToolBarCtrl::GetImageList  
 Ruft die Bildliste, die einem Symbolleisten-Steuerelement verwendet wird, um die Schaltflächen im Standardzustand angezeigt.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, oder **NULL** Wenn keine Bildliste festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787337), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetinsertmarka--ctoolbarctrlgetinsertmark"></a><a name="getinsertmark"></a>CToolBarCtrl::GetInsertMark  
 Ruft die aktuellen Einfügemarke für die Symbolleiste ab.  
  
```  
void GetInsertMark(TBINSERTMARK* ptbim) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ptbim`  
 Ein Zeiger auf eine [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) -Struktur, die die Einfügemarke empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787338), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetinsertmarkcolora--ctoolbarctrlgetinsertmarkcolor"></a><a name="getinsertmarkcolor"></a>CToolBarCtrl::GetInsertMarkColor  
 Ruft die Farbe verwendet, um die Einfügemarke für die Symbolleiste Zeichnen.  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die Farbe der aktuellen Einfügemarke enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787339), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetitemrecta--ctoolbarctrlgetitemrect"></a><a name="getitemrect"></a>CToolBarCtrl::GetItemRect  
 Ruft das umschließende Rechteck einer Schaltfläche in einem Symbolleisten-Steuerelement ab.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index der Schaltfläche für die Informationen abzurufen.  
  
 `lpRect`  
 Adresse einer [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Koordinaten des umschließenden Rechtecks empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft das umschließende Rechteck für Schaltflächen, deren Zustand auf, nicht `TBSTATE_HIDDEN`.  
  
##  <a name="a-namegetmaxsizea--ctoolbarctrlgetmaxsize"></a><a name="getmaxsize"></a>CToolBarCtrl::GetMaxSize  
 Ruft die Gesamtgröße aller sichtbaren Schaltflächen und Trennzeichen auf der Symbolleiste ab.  
  
```  
BOOL GetMaxSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pSize`  
 Ein Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) -Struktur, die die Größe der Elemente empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETMAXSIZE](http://msdn.microsoft.com/library/windows/desktop/bb787341), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmaxtextrowsa--ctoolbarctrlgetmaxtextrows"></a><a name="getmaxtextrows"></a>CToolBarCtrl::GetMaxTextRows  
 Ruft die maximale Anzahl von Textzeilen auf eine Symbolleisten-Schaltfläche angezeigt.  
  
```  
int GetMaxTextRows() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Textzeilen auf eine Symbolleisten-Schaltfläche angezeigt werden soll.  
  
##  <a name="a-namegetmetricsa--ctoolbarctrlgetmetrics"></a><a name="getmetrics"></a>CToolBarCtrl::GetMetrics  
 Ruft die Metrik der ab dem `CToolBarCtrl` Objekt.  
  
```  
void GetMetrics(LPTBMETRICS ptbm) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ptbm`  
 Ein Zeiger auf die [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) Struktur der `CToolBarCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [TB_GETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787342) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpaddinga--ctoolbarctrlgetpadding"></a><a name="getpadding"></a>CToolBarCtrl::GetPadding  
 Ruft den horizontalen und vertikalen Abstand des aktuellen Symbolleisten-Steuerelements ab.  
  
```  
BOOL GetPadding(
    int* pnHorzPadding,   
    int* pnVertPadding) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pnHorzPadding`|Eine ganze Zahl, die den horizontalen Abstand des Symbolleisten-Steuerelements in Pixel empfängt.|  
|[out] `pnVertPadding`|Eine ganze Zahl, die den vertikalen Abstand des Symbolleisten-Steuerelements in Pixel empfängt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TB_GETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787344) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpressedimagelista--ctoolbarctrlgetpressedimagelist"></a><a name="getpressedimagelist"></a>CToolBarCtrl::GetPressedImageList  
 Ruft die Bildliste, die das aktuellen Symbolleisten-Steuerelement verwendet wird, um die Darstellung von Schaltflächen im gedrückten Zustand.  
  
```  
CImageList* GetPressedImageList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) , enthält die Liste der Images für das aktuelle Steuerelement oder `NULL` Wenn keine solche Bildliste festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TB_GETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787345) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrecta--ctoolbarctrlgetrect"></a><a name="getrect"></a>CToolBarCtrl::GetRect  
 Ruft das umschließende Rechteck für eine angegebene Symbolleisten-Schaltfläche.  
  
```  
BOOL GetRect(
    int nID,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner der Schaltfläche.  
  
 `lpRect`  
 Ein Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die umschließende Rechteck Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn erfolgreich, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb787346), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrowsa--ctoolbarctrlgetrows"></a><a name="getrows"></a>CToolBarCtrl::GetRows  
 Ruft die Anzahl der Zeilen von Schaltflächen, die derzeit vom Symbolleisten-Steuerelement angezeigt.  
  
```  
int GetRows() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Zeilen von Schaltflächen, die derzeit auf der Symbolleiste angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die Anzahl der Zeilen immer eine, wenn die Symbolleiste erstellt wurde, mit der `TBSTYLE_WRAPABLE` Stil.  
  
##  <a name="a-namegetstatea--ctoolbarctrlgetstate"></a><a name="getstate"></a>CToolBarCtrl::GetState  
 Ruft Informationen über den Zustand der angegebenen Schaltfläche in einem Symbolleisten-Steuerelement, z. B., ob es aktiviert, gedrückt oder aktiviert wird, ab.  
  
```  
int GetState(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehl Bezeichner der Schaltfläche für die Informationen abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Schaltfläche, um die Statusinformationen im Erfolgsfall oder – 1, die andernfalls. Die Zustandsinformationen Schaltfläche kann eine Kombination der Werte im [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich, wenn Sie mehr als einen Schaltflächenstatus abrufen möchten. Rufen Sie einfach einen Status verwenden Sie eine der folgenden Memberfunktionen: [IsButtonEnabled](#isbuttonenabled), [IsButtonChecked](#isbuttonchecked), [IsButtonPressed](#isbuttonpressed), [IsButtonHidden](#isbuttonhidden), oder [IsButtonIndeterminate](#isbuttonindeterminate). Allerdings die `GetState` Member-Funktion ist die einzige Möglichkeit zum Erkennen der `TBSTATE_WRAP` Schaltfläche Status.  
  
##  <a name="a-namegetstringa--ctoolbarctrlgetstring"></a><a name="getstring"></a>CToolBarCtrl::GetString  
 Ruft eine Zeichenfolge für die Symbolleiste.  
  
```  
int GetString(
    int nString,  
    LPTSTR lpstrString,  
    int cchMaxLen) const;  
  
int GetString(
    int nString,  
    CString& str) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nString*  
 Der Index der Zeichenfolge.  
  
 *lpstrString*  
 Zeiger auf einen Puffer, der die Zeichenfolge zurückgegeben.  
  
 *cchMaxLen*  
 Die Länge des Puffers in Bytes.  
  
 `str`  
 Die Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge an, wenn erfolgreich, andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_GETSTRING](http://msdn.microsoft.com/library/windows/desktop/bb787349)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstylea--ctoolbarctrlgetstyle"></a><a name="getstyle"></a>CToolBarCtrl::GetStyle  
 Ruft die derzeit angezeigten Stile zu einem Toolbar-Steuerelement ab.  
  
```  
DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` mit einer Kombination von [Steuerelementtypen für die Symbolleiste](http://msdn.microsoft.com/library/windows/desktop/bb760439)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettooltipsa--ctoolbarctrlgettooltips"></a><a name="gettooltips"></a>CToolBarCtrl::GetToolTips  
 Ruft ab das Handle für das QuickInfo-Steuerelement, vorhanden, die dem Symbolleisten-Steuerelement zugeordnet.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt diese Symbolleiste zugeordnet oder **NULL** die Symbolleiste besitzt keine zugeordnete QuickInfo-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Da das Symbolleisten-Steuerelement ist normalerweise erstellt und ein eigenen QuickInfo-Steuerelement verwaltet, müssen die meisten Programme Aufrufen dieser Funktion.  
  
##  <a name="a-namehittesta--ctoolbarctrlhittest"></a><a name="hittest"></a>CToolBarCtrl::HitTest  
 Bestimmt, in dem ein Punkt in einem Symbolleisten-Steuerelement liegt.  
  
```  
int HitTest(LPPOINT ppt) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppt`  
 Ein Zeiger auf eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die die X-Koordinate des Treffertests in enthält die **x** Member und der y-Koordinate der Treffer im Testen der **y** Member. Die Koordinaten sind relativ zum Clientbereich der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die den Speicherort eines Punkts auf einer Symbolleiste. Wenn der Wert&0; (null) oder ein positiver Wert ist, ist dieser Rückgabewert den nullbasierten Index des Elements Nonseparator in der der Punkt liegt.  
  
 Wenn der Wert negativ ist, der Punkt nicht innerhalb einer Schaltfläche liegen. Der Absolute Wert des Rückgabewerts ist der Index des trennzeichenelements oder das nächste Element der Nonseparator.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787360), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehidebuttona--ctoolbarctrlhidebutton"></a><a name="hidebutton"></a>CToolBarCtrl::HideButton  
 Blendet oder die angegebene Schaltfläche in einem Symbolleisten-Steuerelement.  
  
```  
BOOL HideButton(
    int nID,  
    BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehl Bezeichner der Schaltfläche auszublenden oder anzuzeigen.  
  
 `bHide`  
 **True,** zum Ausblenden der Schaltfläche **FALSE** es angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie mehr als eine Schaltflächenstatus ändern möchten, sollten Sie aufrufen [SetState](#setstate) stattdessen.  
  
##  <a name="a-nameindeterminatea--ctoolbarctrlindeterminate"></a><a name="indeterminate"></a>CToolBarCtrl::Indeterminate  
 Aktiviert oder deaktiviert den unbestimmten Zustand der angegebenen Schaltfläche in einem Symbolleisten-Steuerelement.  
  
```  
BOOL Indeterminate(
    int nID,  
    BOOL bIndeterminate = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehl Bezeichner der Schaltfläche unbestimmten Zustand festgelegt oder gelöscht wird.  
  
 *bIndeterminate*  
 **True,** zum Festlegen des unbestimmten Status für die angegebene Schaltfläche **FALSE** zu deaktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Unbestimmte Schaltflächen wird abgeblendet, wie z. B. die Möglichkeit, die Schaltfläche "Fett" auf der Symbolleiste ein Textverarbeitungsprogramm aussehen würde der ausgewählten Text fett und normale Zeichen enthält. Wenn Sie mehr als eine Schaltflächenstatus ändern möchten, sollten Sie aufrufen [SetState](#setstate) stattdessen.  
  
##  <a name="a-nameinsertbuttona--ctoolbarctrlinsertbutton"></a><a name="insertbutton"></a>CToolBarCtrl::InsertButton  
 Fügt eine Schaltfläche in einem Symbolleisten-Steuerelement.  
  
```  
BOOL InsertButton(
    int nIndex,  
    LPTBBUTTON lpButton);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierter Index einer Schaltfläche. Diese Funktion fügt die neue Schaltfläche auf der linken Seite dieser Schaltfläche.  
  
 `lpButton`  
 Adresse einer `TBBUTTON` Struktur mit Informationen über die Schaltfläche einfügen. Finden Sie unter [CToolBarCtrl::AddButtons](#addbuttons) eine Beschreibung der `TBBUTTON` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Das Bild und/oder die Zeichenfolge, deren Index, die Sie bereitstellen zuvor worden sein, des Symbolleisten-Steuerelements hinzugefügt muss, auflisten mithilfe der [AddBitmap](#addbitmap), [AddString](#addstring), und/oder [AddStrings](#addstrings).  
  
##  <a name="a-nameinsertmarkhittesta--ctoolbarctrlinsertmarkhittest"></a><a name="insertmarkhittest"></a>CToolBarCtrl::InsertMarkHitTest  
 Ruft die einfügen-Mark-Informationen für einen Punkt in einer Symbolleiste ab.  
  
```  
BOOL InsertMarkHitTest(
    LPPOINT ppt,  
    LPTBINSERTMARK ptbim) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppt`  
 Ein Zeiger auf eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die den Treffertest enthält Koordinaten relativ zum Clientbereich der Symbolleiste.  
  
 `ptbim`  
 Ein Zeiger auf eine [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) -Struktur, die die Einfügemarke Mark Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_INSERTMARKHITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787367), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisbuttoncheckeda--ctoolbarctrlisbuttonchecked"></a><a name="isbuttonchecked"></a>CToolBarCtrl::IsButtonChecked  
 Bestimmt, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement aktiviert ist.  
  
```  
BOOL IsButtonChecked(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehls-ID der Schaltfläche in der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Schaltfläche aktiviert ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrachten Sie aufrufen [GetState](#getstate) , wenn Sie mehrere Status abrufen möchten.  
  
##  <a name="a-nameisbuttonenableda--ctoolbarctrlisbuttonenabled"></a><a name="isbuttonenabled"></a>CToolBarCtrl::IsButtonEnabled  
 Bestimmt, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement aktiviert ist.  
  
```  
BOOL IsButtonEnabled(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehls-ID der Schaltfläche in der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche aktiviert ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrachten Sie aufrufen [GetState](#getstate) , wenn Sie mehrere Status abrufen möchten.  
  
##  <a name="a-nameisbuttonhiddena--ctoolbarctrlisbuttonhidden"></a><a name="isbuttonhidden"></a>CToolBarCtrl::IsButtonHidden  
 Bestimmt, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement ausgeblendet ist.  
  
```  
BOOL IsButtonHidden(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehls-ID der Schaltfläche in der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche ausgeblendet wird; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrachten Sie aufrufen [GetState](#getstate) , wenn Sie mehrere Status abrufen möchten.  
  
##  <a name="a-nameisbuttonhighlighteda--ctoolbarctrlisbuttonhighlighted"></a><a name="isbuttonhighlighted"></a>CToolBarCtrl::IsButtonHighlighted  
 Überprüft den Status markieren, eine Symbolleisten-Schaltfläche.  
  
```  
BOOL IsButtonHighlighted(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Befehls-ID für das Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Positive ganze Zahl, wenn die Schaltfläche hervorgehoben ist, wird 0, wenn die Schaltfläche nicht hervorgehoben ist, oder 1, wenn ein Fehler.  
  
##  <a name="a-nameisbuttonindeterminatea--ctoolbarctrlisbuttonindeterminate"></a><a name="isbuttonindeterminate"></a>CToolBarCtrl::IsButtonIndeterminate  
 Bestimmt, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement unbestimmt ist.  
  
```  
BOOL IsButtonIndeterminate(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Befehls-ID der Schaltfläche in der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Positive ganze Zahl, wenn die Schaltfläche unbestimmt ist NULL, wenn die Schaltfläche unbestimmt ist, oder -1, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Unbestimmte Schaltflächen Leuchten abgeblendet, wie z. B. die Möglichkeit, die Schaltfläche "Fett" auf der Symbolleiste ein Textverarbeitungsprogramm aussieht, wenn es sich bei den ausgewählten Text fett und normale Zeichen enthält. Betrachten Sie aufrufen [GetState](#getstate) , wenn Sie mehrere Status abrufen möchten.  
  
##  <a name="a-nameisbuttonpresseda--ctoolbarctrlisbuttonpressed"></a><a name="isbuttonpressed"></a>CToolBarCtrl::IsButtonPressed  
 Bestimmt, ob die angegebene Schaltfläche in einem Symbolleisten-Steuerelement geklickt wird.  
  
```  
BOOL IsButtonPressed(int nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehls-ID der Schaltfläche in der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche gedrückt wird, andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrachten Sie aufrufen [GetState](#getstate) , wenn Sie mehrere Status abrufen möchten.  
  
##  <a name="a-nameloadimagesa--ctoolbarctrlloadimages"></a><a name="loadimages"></a>CToolBarCtrl::LoadImages  
 Bitmaps in einem Symbolleisten-Steuerelement Bildliste geladen.  
  
```  
void LoadImages(
    int iBitmapID,  
    HINSTANCE hinst);
```  
  
### <a name="parameters"></a>Parameter  
 *iBitmapID*  
 Die ID einer Bitmap mit den Bildern geladen werden. Um eine eigene Bitmap-Ressource anzugeben, legen Sie diesen Parameter auf die ID einer Bitmap-Ressource sowie `hInst` auf **NULL**. Bitmap-Ressource wird auf die Bildliste als ein einzelnes Abbild hinzugefügt werden. Sie können standardmäßige, vom System definierte Bitmaps hinzufügen, indem *Hinst* auf **HINST_COMMCTRL** und dieser Parameter auf einen der folgenden IDs festlegen:  
  
|Bitmap-ID|Beschreibung|  
|---------------|-----------------|  
|IDB_HIST_LARGE_COLOR|Explorer-Bitmaps vergrößert|  
|IDB_HIST_SMALL_COLOR|Explorer-Bitmaps klein|  
|IDB_STD_LARGE_COLOR|Standard-Bitmaps vergrößert|  
|IDB_STD_SMALL_COLOR|Standard-Bitmaps klein|  
|IDB_VIEW_LARGE_COLOR|Anzeigen von Bitmaps vergrößert|  
|IDB_VIEW_SMALL_COLOR|Anzeigen von Bitmaps klein|  
  
 *hinst*  
 Programm Instanzhandle an die aufrufende Anwendung. Dieser Parameter kann **HINST_COMMCTRL** eine Liste der standard-Image geladen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_LOADIMAGES](http://msdn.microsoft.com/library/windows/desktop/bb787381), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemapacceleratora--ctoolbarctrlmapaccelerator"></a><a name="mapaccelerator"></a>CToolBarCtrl::MapAccelerator  
 Ordnet eine Zugriffstaste Zeichen eine Symbolleisten-Schaltfläche.  
  
```  
BOOL MapAccelerator(
    TCHAR chAccel,  
    UINT* pIDBtn);
```  
  
### <a name="parameters"></a>Parameter  
 `chAccel`  
 Accelerator-Zeichen zugeordnet werden. Dieses Zeichen ist das gleiche Zeichen, das im Text der Schaltfläche unterstrichen ist.  
  
 *pIDBtn*  
 Ein Zeiger auf eine **UINT** , empfängt die Befehls-ID der Schaltfläche, die dem im angegebenen Beschleuniger entspricht `chAccel`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_MAPACCELERATOR](http://msdn.microsoft.com/library/windows/desktop/bb787383), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemarkbuttona--ctoolbarctrlmarkbutton"></a><a name="markbutton"></a>CToolBarCtrl::MarkButton  
 Legt den Status markieren Sie eine der vorhandenen Schaltflächen in einem Symbolleisten-Steuerelement fest.  
  
```  
BOOL MarkButton(
    int nID,  
    BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner der Schaltfläche.  
  
 `fHighlight`  
 Gibt den Status "Highlight" festgelegt werden. In der Standardeinstellung **TRUE**. Wenn auf festgelegt **FALSE**, die Schaltfläche auf den Standardzustand festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_MARKBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787385)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemovebuttona--ctoolbarctrlmovebutton"></a><a name="movebutton"></a>CToolBarCtrl::MoveButton  
 Verschiebt eine Schaltfläche aus einem Index.  
  
```  
BOOL MoveButton(
    UINT nOldPos,  
    UINT nNewPos);
```  
  
### <a name="parameters"></a>Parameter  
 *nOldPos*  
 Der nullbasierte Index der Schaltfläche verschoben werden soll.  
  
 *nNewPos*  
 Der nullbasierte Index des Ziels für die Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_MOVEBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787387)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namepressbuttona--ctoolbarctrlpressbutton"></a><a name="pressbutton"></a>CToolBarCtrl::PressButton  
 Drückt, oder die angegebene Schaltfläche in einem Symbolleisten-Steuerelement frei.  
  
```  
BOOL PressButton(int nID, BOOL bPress = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Bezeichner der Schaltfläche drücken oder loslassen-Befehl.  
  
 [in] `bPress`  
 `true`Drücken Sie die angegebene Schaltfläche; `false` die angegebene Schaltfläche freigeben. Der Standardwert ist `true`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie mehr als eine Schaltflächenstatus ändern möchten, sollten Sie aufrufen [SetState](#setstate) stattdessen.  
  
 Diese Methode sendet die [TB_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787389) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namereplacebitmapa--ctoolbarctrlreplacebitmap"></a><a name="replacebitmap"></a>CToolBarCtrl::ReplaceBitmap  
 Ersetzt den vorhandene Bitmap in der aktuellen Symbolleisten-Steuerelement mit einer neuen Bitmap.  
  
```  
BOOL ReplaceBitmap(LPTBREPLACEBITMAP pReplaceBitmap);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pReplaceBitmap`|Zeiger auf eine [TBREPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb760484) -Struktur, die die Bitmap ersetzt werden und der neuen Bitmap beschreibt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TB_REPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787391) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden die Bitmap für die Symbolleiste standard mit einer anderen Bitmap ersetzt.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_4.cpp)]  
  
##  <a name="a-namerestorestatea--ctoolbarctrlrestorestate"></a><a name="restorestate"></a>CToolBarCtrl::RestoreState  
 Hiermit wird der Status des Symbolleisten-Steuerelements aus dem Speicherort in der Registrierung, die von den Parametern angegeben.  
  
```  
void RestoreState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Parameter  
 `hKeyRoot`  
 Identifiziert einen geöffneten Schlüssel in der Registrierung oder eines der folgenden vordefinierten reservierte Handlewerte an:  
  
- **HKEY_CLASSES_ROOT.**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Zeigt auf eine Null-terminierte Zeichenfolge mit dem Namen des Unterschlüssels, der ein Wert zugeordnet ist. Dieser Parameter kann Null oder ein Zeiger auf eine leere Zeichenfolge sein. Wenn der Parameter **NULL**, wird der Wert für den Schlüssel identifizierte hinzugefügt werden die `hKeyRoot` Parameter.  
  
 `lpszValueName`  
 Zeigt auf eine Zeichenfolge, die den Namen der abzurufenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits im Schlüssel vorhanden ist, hinzugefügt die Funktion des Schlüssels.  
  
##  <a name="a-namesavestatea--ctoolbarctrlsavestate"></a><a name="savestate"></a>CToolBarCtrl::SaveState  
 Speichert den Zustand des Symbolleisten-Steuerelements an der Position in der Registrierung, die von den Parametern angegeben.  
  
```  
void SaveState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Parameter  
 `hKeyRoot`  
 Identifiziert einen geöffneten Schlüssel in der Registrierung oder eines der folgenden vordefinierten reservierte Handlewerte an:  
  
- **HKEY_CLASSES_ROOT.**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Zeigt auf eine Null-terminierte Zeichenfolge mit dem Namen des Unterschlüssels, der ein Wert zugeordnet ist. Dieser Parameter kann Null oder ein Zeiger auf eine leere Zeichenfolge sein. Wenn der Parameter **NULL**, wird der Wert für den Schlüssel identifizierte hinzugefügt werden die `hKeyRoot` Parameter.  
  
 `lpszValueName`  
 Zeigt auf eine Zeichenfolge, die den Namen der den festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits im Schlüssel vorhanden ist, hinzugefügt die Funktion des Schlüssels.  
  
##  <a name="a-namesetanchorhighlighta--ctoolbarctrlsetanchorhighlight"></a><a name="setanchorhighlight"></a>CToolBarCtrl::SetAnchorHighlight  
 Legt die Anker Hervorhebung für eine Symbolleiste festlegen.  
  
```  
BOOL SetAnchorHighlight(BOOL fAnchor = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `fAnchor`  
 Gibt an, ob Anker Hervorhebung aktiviert oder deaktiviert ist. Wenn dieser Wert ungleich NULL ist, wird die Hervorhebung Anker aktiviert. Wenn dieser Wert&0; (null) ist, wird Anker Hervorhebung deaktiviert  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Einstellung der Anker. Wenn die Hervorhebung aktiviert wurde, ist dieser Wert ungleich NULL ist. Wenn die Hervorhebung nicht aktiviert wurde, ist dieser Wert&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert das Verhalten der Win32-Nachricht [TB_SETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787396), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbitmapsizea--ctoolbarctrlsetbitmapsize"></a><a name="setbitmapsize"></a>CToolBarCtrl::SetBitmapSize  
 Legt die Größe des tatsächlichen Bitmapbildern Symbolleisten-Steuerelement hinzugefügt werden.  
  
```  
BOOL SetBitmapSize(CSize size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Breite und Höhe in Pixel der Bitmap-Images.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion muss aufgerufen werden, nur vor dem Hinzufügen von Bitmaps auf der Symbolleiste. Wenn die Anwendung die Bitmapgröße nicht explizit festgelegt, wird standardmäßig 16 x 15 Pixel.  
  
##  <a name="a-namesetbuttoninfoa--ctoolbarctrlsetbuttoninfo"></a><a name="setbuttoninfo"></a>CToolBarCtrl::SetButtonInfo  
 Die Informationen für eine vorhandene Schaltfläche fest in einer Symbolleiste.  
  
```  
BOOL SetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner der Schaltfläche.  
  
 `ptbbi`  
 Ein Zeiger auf eine [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) -Struktur, die die Schaltflächeninformationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion, die das Verhalten der Win32-Meldung [TB_SETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787413), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbuttonsizea--ctoolbarctrlsetbuttonsize"></a><a name="setbuttonsize"></a>CToolBarCtrl::SetButtonSize  
 Legt die Größe der Schaltflächen in Symbolleisten-Steuerelement fest.  
  
```  
BOOL SetButtonSize(CSize size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Breite und Höhe in Pixel der Schaltflächen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe der Schaltfläche muss immer mindestens so groß wie die Bitmapgröße sein, die eingeschlossen. Diese Funktion muss aufgerufen werden, nur vor dem Hinzufügen von Bitmaps auf der Symbolleiste. Wenn die Anwendung die Größe der Schaltfläche nicht explizit festgelegt, wird standardmäßig auf 24 x 22 Pixel.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetToolBarCtrl](../../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
##  <a name="a-namesetbuttonstructsizea--ctoolbarctrlsetbuttonstructsize"></a><a name="setbuttonstructsize"></a>CToolBarCtrl::SetButtonStructSize  
 Gibt die Größe der `TBBUTTON` Struktur.  
  
```  
void SetButtonStructSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 `nSize`  
 Größe, in Bytes, der von der `TBBUTTON` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie zum Speichern von zusätzlicher Daten in der `TBBUTTON` -Struktur konnte entweder leiten Sie eine neue Struktur von `TBBUTTON`, Hinzufügen der Elemente Sie benötigt, oder erstellen Sie eine neue Struktur, enthält eine `TBBUTTON` Struktur als erste Member. Sie würden dann diese Funktion, um dem Symbolleisten-Steuerelement die Größe der neuen Struktur Teilen aufrufen.  
  
 Finden Sie unter [CToolBarCtrl::AddButtons](#addbuttons) Weitere Informationen zu den `TBBUTTON` Struktur.  
  
##  <a name="a-namesetbuttonwidtha--ctoolbarctrlsetbuttonwidth"></a><a name="setbuttonwidth"></a>CToolBarCtrl::SetButtonWidth  
 Legt die minimale und maximale Schaltfläche breiten in dem Symbolleisten-Steuerelement fest.  
  
```  
BOOL SetButtonWidth(
    int cxMin,  
    int cxMax);
```  
  
### <a name="parameters"></a>Parameter  
 `cxMin`  
 Minimale Schaltflächenbreite in Pixel. Symbolleisten-Schaltflächen werden nie kleiner sind als dieser Wert.  
  
 *cxMax*  
 Maximale Schaltflächenbreite in Pixel. Wenn der Text der Schaltfläche zu groß ist, wird das Steuerelement durch Auslassungspunkte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETBUTTONWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb787417), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcmdida--ctoolbarctrlsetcmdid"></a><a name="setcmdid"></a>CToolBarCtrl::SetCmdID  
 Legt die Befehls-ID, die an das Besitzerfenster gesendet wird, wenn die angegebene Schaltfläche gedrückt wird.  
  
```  
BOOL SetCmdID(
    int nIndex,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index der Schaltfläche, dessen Befehls-ID ist, festgelegt werden.  
  
 `nID`  
 Die Befehls-ID auf die ausgewählte Schaltfläche festgelegt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL, wenn erfolgreich; andernfalls&0; (null).  
  
##  <a name="a-namesetcolorschemea--ctoolbarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CToolBarCtrl::SetColorScheme  
 Legt das Farbschema des aktuellen Symbolleisten-Steuerelements fest.  
  
```  
void SetColorScheme(const COLORSCHEME* lpColorScheme);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `lpColorScheme`|Zeiger auf eine [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) -Struktur, die Farbe und die Schattenfarbe des Symbolleisten-Steuerelements beschreibt.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode hat keine Auswirkung, wenn ein [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] Design festgelegt ist.  
  
 Diese Methode sendet die [TB_SETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787421) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das Farbschema für das aktuelle Symbolleisten-Steuerelement. Im Codebeispiel wird am linken und oberen Rand jedes rote Schaltfläche und den rechten und unteren Rändern Blau. Wenn der Benutzer die Taste drückt, Rot Kanten der Schaltfläche ändert sich in Blau und Ränder blau rot angezeigt.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1&3;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_5.cpp)]  
  
##  <a name="a-namesetdisabledimagelista--ctoolbarctrlsetdisabledimagelist"></a><a name="setdisabledimagelist"></a>CToolBarCtrl::SetDisabledImageList  
 Legt die Liste der Images, die das Symbolleisten-Steuerelement verwenden auf Anzeigeschaltflächen deaktiviert fest.  
  
```  
CImageList* SetDisabledImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf ein `CImageList` Objekt mit den Abbildern, die von dem Symbolleisten-Steuerelement auf die Schaltflächenbilder anzeigen deaktiviert verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt, das zuvor vom Symbolleisten-Steuerelement auf die Schaltflächenbilder anzeigen deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787423), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Die MFC-Implementierung von `SetDisabledImageList` verwendet ein `CImageList` Objekt, das deaktivierte Schaltfläche der Toolbar-Steuerelement enthält Bilder statt ein Handle zu einer Bildliste.  
  
##  <a name="a-namesetdrawtextflagsa--ctoolbarctrlsetdrawtextflags"></a><a name="setdrawtextflags"></a>CToolBarCtrl::SetDrawTextFlags  
 Legt die Flags in der Win32-Funktion [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), dient zum Zeichnen von Text in das angegebene Rechteck, formatiert, wie die Flags festgelegt sind.  
  
```  
DWORD SetDrawTextFlags(
    DWORD dwMask,  
    DWORD dwDTFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMask`  
 Eine Kombination aus einem oder mehreren der in der Win32-Funktion angegebenen Flags für DT_ [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), der angibt, die in bits `dwDTFlags` beim Zeichnen von Text verwendet werden.  
  
 `dwDTFlags`  
 Eine Kombination aus einem oder mehreren der in der Win32-Funktion angegebenen Flags für DT_ `DrawText`, die angeben, wie der Text der Schaltfläche gezeichnet werden. Dieser Wert wird übergeben, um `DrawText` bei der Text der Schaltfläche gezeichnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` mit dem vorherigen Text zeichnen Flags.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETDRAWTEXTFLAGS](http://msdn.microsoft.com/library/windows/desktop/bb787425), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Diese Memberfunktion legt die Flags fest, in der Win32-Funktion `DrawText`, zeichnet der Text in dem angegebenen Rechteck, formatiert, wie die Flags festgelegt sind.  
  
##  <a name="a-namesetextendedstylea--ctoolbarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CToolBarCtrl::SetExtendedStyle  
 Legt die erweiterten Stile für eine Symbolleisten-Steuerelement fest.  
  
```  
DWORD SetExtendedStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Ein Wert, der die neue erweiterte Stile angeben. Dieser Parameter kann eine Kombination aus der Symbolleiste Erweiterte Stile sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` , das vorherige darstellt Erweiterte Stile. Eine Liste der Formate, finden Sie unter [Symbolleiste Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb760430)in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787427), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesethotimagelista--ctoolbarctrlsethotimagelist"></a><a name="sethotimagelist"></a>CToolBarCtrl::SetHotImageList  
 Legt die Liste der Images, die das Symbolleisten-Steuerelement verwenden "heiße" Schaltflächen angezeigt.  
  
```  
CImageList* SetHotImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf ein `CImageList` Objekt mit den Abbildern vom Symbolleisten-Steuerelement verwendet werden, um aktive Schaltflächenbilder anzuzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, das zuvor vom Symbolleisten-Steuerelement verwendet wurde, um aktive Schaltflächenbilder anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787429), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Die MFC-Implementierung von `SetHotImageList` verwendet ein `CImageList` Objekt mit dem Symbolleisten-Steuerelement aktive Schaltfläche Bilder anstelle eines Handles zu einer Bildliste. Eine aktive Schaltfläche wird hervorgehoben, wenn der Mauszeiger darüber befindet.  
  
##  <a name="a-namesethotitema--ctoolbarctrlsethotitem"></a><a name="sethotitem"></a>CToolBarCtrl::SetHotItem  
 Legt das Element in einer Symbolleiste.  
  
```  
int SetHotItem(int nHot);
```  
  
### <a name="parameters"></a>Parameter  
 *nHot*  
 Die nullbasierte Indexnummer des Elements, die im laufenden Systembetrieb vorgenommen werden. Wenn der Wert-1 ist, wird keines der Elemente hot.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index für das vorherige Element oder -1, wenn kein hot Element vorhanden war.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787431)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetimagelista--ctoolbarctrlsetimagelist"></a><a name="setimagelist"></a>CToolBarCtrl:: SetImageList  
 Legt die Liste der Images, die mithilfe der Symbolleiste Schaltflächen anzuzeigen, die in ihren Standardzustand zurückgesetzt werden.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf ein `CImageList` Objekt mit den Abbildern vom Symbolleisten-Steuerelement mit der Schaltflächenbilder in ihrem Standardzustand anzuzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, das zuvor vom Symbolleisten-Steuerelements anzuzeigenden Bilder in ihrem Standardzustand verwendet wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787433)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Die MFC-Implementierung von `SetImageList` verwendet ein `CImageList` Objekt mit dem Symbolleisten-Steuerelement Schaltfläche Bilder statt ein Handle zu einer Bildliste.  
  
##  <a name="a-namesetindenta--ctoolbarctrlsetindent"></a><a name="setindent"></a>CToolBarCtrl::SetIndent  
 Legt den Einzug für die erste Schaltfläche in einem Symbolleisten-Steuerelement fest.  
  
```  
BOOL SetIndent(int iIndent);
```  
  
### <a name="parameters"></a>Parameter  
 *iIndent*  
 Der Wert, der den Einzug in Pixel angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="a-namesetinsertmarka--ctoolbarctrlsetinsertmark"></a><a name="setinsertmark"></a>CToolBarCtrl::SetInsertMark  
 Legt die aktuelle Einfügemarke für die Symbolleiste.  
  
```  
void SetInsertMark(TBINSERTMARK* ptbim);
```  
  
### <a name="parameters"></a>Parameter  
 `ptbim`  
 Ein Zeiger auf die [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) -Struktur, die die Einfügemarke enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787437), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetinsertmarkcolora--ctoolbarctrlsetinsertmarkcolor"></a><a name="setinsertmarkcolor"></a>CToolBarCtrl::SetInsertMarkColor  
 Wird verwendet, um die Einfügemarke für die Symbolleiste Zeichnen.  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Parameter  
 `clrNew`  
 Ein **COLORREF** Wert, der die Farbe der neuen Einfügemarke enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die Farbe der vorherigen Einfügemarke enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TB_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787439), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmaxtextrowsa--ctoolbarctrlsetmaxtextrows"></a><a name="setmaxtextrows"></a>CToolBarCtrl::SetMaxTextRows  
 Legt die maximale Anzahl von Textzeilen auf eine Symbolleisten-Schaltfläche angezeigt.  
  
```  
BOOL SetMaxTextRows(int iMaxRows);
```  
  
### <a name="parameters"></a>Parameter  
 *iMaxRows*  
 Maximale Anzahl von Zeilen festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="a-namesetmetricsa--ctoolbarctrlsetmetrics"></a><a name="setmetrics"></a>CToolBarCtrl::SetMetrics  
 Legt die Metriken von der `CToolBarCtrl` Objekt.  
  
```  
void SetMetrics(LPTBMETRICS ptbm);
```  
  
### <a name="parameters"></a>Parameter  
 `ptbm`  
 Ein Zeiger auf die [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) Struktur der `CToolBarCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [TB_SETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787446) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetownera--ctoolbarctrlsetowner"></a><a name="setowner"></a>CToolBarCtrl::SetOwner  
 Legt das Besitzerfenster für das Symbolleisten-Steuerelement fest.  
  
```  
void SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Zeiger auf die `CWnd` oder `CWnd`-Objekts, das neue Besitzerfensters für das Symbolleisten-Steuerelement abgeleitet.  
  
### <a name="remarks"></a>Hinweise  
 Das Besitzerfenster ist das Fenster, das empfängt Benachrichtigungen aus der Symbolleiste.  
  
##  <a name="a-namesetpaddinga--ctoolbarctrlsetpadding"></a><a name="setpadding"></a>CToolBarCtrl::SetPadding  
 Legt den horizontalen und vertikalen Abstand des aktuellen Symbolleisten-Steuerelements fest.  
  
```  
DWORD SetPadding(
    int nHorzPadding,   
    int nVertPadding);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nHorzPadding`|Gibt den horizontalen Abstand des Symbolleisten-Steuerelements in Pixel.|  
|[in] `nVertPadding`|Gibt den vertikalen Abstand des Symbolleisten-Steuerelements in Pixel.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` , dessen niedriges Word enthält den vorherigen Wert der horizontale Abstand, deren hohes Word den vorherigen Wert der vertikale Abstand. Die Abstandswerte werden in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TB_SETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787448) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die horizontalen und vertikalen Abstand des aktuellen Symbolleisten-Steuerelements auf 20 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_6.cpp)]  
  
##  <a name="a-namesetpressedimagelista--ctoolbarctrlsetpressedimagelist"></a><a name="setpressedimagelist"></a>CToolBarCtrl::SetPressedImageList  
 Legt die Liste der Images, die das aktuellen Symbolleisten-Steuerelement verwendet wird, um die Darstellung von Schaltflächen im gedrückten Zustand.  
  
```  
CImagelist* SetPressedImageList(
    int iImageID,   
    CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iImageID`|Der nullbasierte Index der Bildliste. Legen Sie diesen Parameter auf&0; (null), wenn Sie nur eine Liste der Images verwenden.|  
|[in] `pImageList`|Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) , enthält die neue Bildliste.|  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) , die die vorherigen Bildliste für das aktuelle Steuerelement enthält oder `NULL` Wenn keine solche Bildliste festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TB_SETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787453) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die gedrückten Bildliste an die Liste der Standard-Images identisch sein.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1&5;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_7.cpp)]  
  
##  <a name="a-namesetrowsa--ctoolbarctrlsetrows"></a><a name="setrows"></a>CToolBarCtrl::SetRows  
 Fordert das Symbolleisten-Steuerelement seine Größe selbst auf die angeforderte Anzahl von Zeilen.  
  
```  
void SetRows(
    int nRows,  
    BOOL bLarger,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `nRows`  
 Angeforderte Anzahl von Zeilen.  
  
 `bLarger`  
 Legt fest, ob Zeilen mehr oder weniger Zeilen verwenden, wenn die Symbolleiste auf die angeforderte Anzahl von Zeilen nicht verändert werden kann.  
  
 `lpRect`  
 Verweist auf die [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das neue umfassende Rechteck der Symbolleiste angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Symbolleiste selbst auf die angeforderte Anzahl oder die Zeilen nicht anpassen können, es wird Größe entweder die vergrößern oder die nächste kleinere gültige Größe, abhängig vom Wert `bLarger`. Wenn `bLarger` ist **TRUE**, die Anzahl der Zeilen ist größer als die angeforderte Anzahl. Wenn `bLarger` ist **FALSE**, wird die Anzahl der Zeilen kleiner als die angeforderte Anzahl sein.  
  
 Eine angegebene Anzahl von Zeilen ist gültig für die Symbolleiste, wenn alle Zeilen die gleiche Anzahl von Schaltflächen (außer vielleicht die letzte Zeile) aufweisen, die Schaltflächen angeordnet werden können. Beispielsweise könnte Symbolleiste vier Schaltflächen enthält nicht drei Zeilen festgelegt werden, weil die letzten beiden Zeilen kürzer sein müssten. Wenn Sie versucht, die Größe, drei Zeilen, würden Sie vier Zeilen erhalten, wenn `bLarger` wurde **TRUE** und zwei Zeilen, wenn `bLarger` wurde **FALSE**.  
  
 Wenn in der Symbolleiste Trennzeichen vorhanden sind, sind die Regeln für die bei eine bestimmte Anzahl von Zeilen gültig ist komplizierter. Das Layout wird berechnet, sodass Schaltflächengruppen (Schaltflächen mit einem Trennzeichen vor dem ersten) und die letzte Schaltfläche in der Gruppe nicht auf mehrere Zeilen aufgeteilt werden, wenn die Gruppe nicht auf eine Zeile passen.  
  
 Wenn eine Gruppe nicht auf eine Zeile passt, startet die nächste Gruppe in der nächsten Zeile auch wenn es in der Zeile passen würde, in dem großen beendet. Der Zweck dieser Regel werden die Aufteilung großer Gruppen deutlicher zu machen. Die resultierenden vertikale Trennzeichen werden als Zeilen gezählt.  
  
 Beachten Sie auch, dass der `SetRows` Member-Funktion immer das Layout, bei denen die kleinste Größe der Symbolleiste wählen. Zum Erstellen einer Symbolleiste mit der `TBSTYLE_WRAPABLE` Stil und dann das Steuerelement werden einfach die Methode, die oben aufgeführt werden, wenn die Breite des Steuerelements anwenden.  
  
 Diese Funktion kann nur aufgerufen werden, Symbolleisten, die mit erstellt wurden die `TBSTYLE_WRAPABLE` Stil.  
  
##  <a name="a-namesetstatea--ctoolbarctrlsetstate"></a><a name="setstate"></a>CToolBarCtrl::SetState  
 Legt den Status für die angegebene Schaltfläche in einem Symbolleisten-Steuerelement fest.  
  
```  
BOOL SetState(
    int nID,  
    UINT nState);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Befehls-ID der Schaltfläche.  
  
 `nState`  
 Status-Flags. Es kann eine Kombination der Werte für die Schaltflächenzustände in [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich, wenn Sie mehr als einen Schaltflächenstatus festlegen möchten. Verwenden, um nur ein Status festzulegen eine der folgenden Memberfunktionen: [EnableButton](#enablebutton), [CheckButton](#checkbutton), [HideButton](#hidebutton), [unbestimmt](#indeterminate), oder [PressButton](#pressbutton).  
  
##  <a name="a-namesetstylea--ctoolbarctrlsetstyle"></a><a name="setstyle"></a>CToolBarCtrl::SetStyle  
 Legt die Stile für eine Symbolleisten-Steuerelement fest.  
  
```  
void SetStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Ein `DWORD` mit einer Kombination von [Steuerelementtypen für die Symbolleiste](http://msdn.microsoft.com/library/windows/desktop/bb760439)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettooltipsa--ctoolbarctrlsettooltips"></a><a name="settooltips"></a>CToolBarCtrl::SetToolTips  
 Ordnet einem Symbolleisten-Steuerelement ein QuickInfo-Steuerelement hinzu.  
  
```  
void SetToolTips(CToolTipCtrl* pTip);
```  
  
### <a name="parameters"></a>Parameter  
 *pTip*  
 Zeiger auf die [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt.  
  
##  <a name="a-namesetwindowthemea--ctoolbarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolBarCtrl::SetWindowTheme  
 Legt die visuelle Darstellung der `CToolBarCtrl` Objekt.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 `pszSubAppName`  
 Ein Zeiger auf eine Unicode-Zeichenfolge mit den visuellen Stil der Symbolleiste festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [TB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb787465) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC-Beispiel MFCIE](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar-Klasse](../../mfc/reference/ctoolbar-class.md)

