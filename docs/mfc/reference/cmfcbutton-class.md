---
title: Klasse CMFCButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
dev_langs:
- C++
helpviewer_keywords:
- CMFCButton::CreateObject method
- CMFCButton::DrawItem method
- CMFCButton::PreTranslateMessage method
- CMFCButton constructor
- CMFCButton::OnDrawParentBackground method
- CMFCButton class
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: 35
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 89cd722ac15a1d9ac6b6c815c837559e302f0e68
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbutton-class"></a>CMFCButton-Klasse
Die `CMFCButton` Klasse fügt Funktionen für die [CButton](../../mfc/reference/cbutton-class.md) Klasse wie Ausrichten des Schaltflächentexts, Kombinieren von Schaltflächentext mit einem Bild, Auswählen eines Cursors und Festlegen einer QuickInfo.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCButton : public CButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|Standardkonstruktor|  
|`CMFCButton::~CMFCButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCButton::CleanUp](#cleanup)|Setzt die internen Variablen zurück und frei von zugeordneten Ressourcen wie Bilder, Bitmaps und Symbole.|  
|`CMFCButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCButton::DrawItem`|Vom Framework aufgerufen, wenn sich ein Darstellungsaspekt einer Ownerdrawn-Schaltfläche geändert hat. (Überschreibt [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Gibt an, ob den vollständigen Text der QuickInfo in einem großen QuickInfo-Fenster oder eine abgeschnittene Version des Texts in einem kleinen QuickInfo-Fenster angezeigt.|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|Gibt an, ob die Schaltfläche Schriftart die Schriftart der Anwendung im Menü identisch ist.|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Gibt an, ob die Schaltfläche Rahmenart für das aktuelle Windows-Design entspricht.|  
|`CMFCButton::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Gibt einen Verweis auf das zugrunde liegende QuickInfo-Steuerelement zurück.|  
|[CMFCButton::IsAutoCheck](#isautocheck)|Gibt an, ob ein Kontrollkästchen oder ein Optionsfeld eine automatische Schaltfläche ist.|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Gibt an, ob eine Schaltfläche auf Automatisches Wiederholen-Modus festgelegt ist.|  
|[CMFCButton::IsCheckBox](#ischeckbox)|Gibt an, ob eine Schaltfläche ein Kontrollkästchen-Schaltfläche ist.|  
|[CMFCButton::IsChecked](#ischecked)|Gibt an, ob die aktuelle Schaltfläche aktiviert ist.|  
|[CMFCButton::IsHighlighted](#ishighlighted)|Gibt an, ob eine Schaltfläche hervorgehoben wird.|  
|[CMFCButton::IsPressed](#ispressed)|Gibt an, ob eine Schaltfläche gedrückt und hervorgehoben wird.|  
|[CMFCButton::IsPushed](#ispushed)|Gibt an, ob eine Schaltfläche gedrückt ist.|  
|[CMFCButton::IsRadioButton](#isradiobutton)|Gibt an, ob eine Schaltfläche ein Optionsfeld ist.|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Gibt an, ob die Schaltfläche Rahmenart für das aktuelle Windows-Design entspricht.|  
|`CMFCButton::OnDrawParentBackground`|Zeichnet den Hintergrund des übergeordneten eine Schaltfläche im angegebenen Bereich. (Überschreibt [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Wird eine Schaltfläche auf Automatisches Wiederholen.|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Legt das Bild für die aktivierte Schaltfläche fest.|  
|[CMFCButton::SetFaceColor](#setfacecolor)|Legt die Hintergrundfarbe für den Text der Schaltfläche fest.|  
|[CMFCButton::SetImage](#setimage)|Legt das Bild für die Schaltfläche fest.|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|Legt den Cursorbild.|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|Setzt den Cursor auf das Bild einer Hand.|  
|[CMFCButton::SetStdImage](#setstdimage)|Verwendet ein `CMenuImages` Objekt, das das Bild der Schaltfläche festgelegt.|  
|[CMFCButton::SetTextColor](#settextcolor)|Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die nicht ausgewählt ist.|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die ausgewählt wird.|  
|[CMFCButton::SetTooltip](#settooltip)|Eine Schaltfläche eine QuickInfo zugeordnet.|  
|[CMFCButton::SizeToContent](#sizetocontent)|Ändert die Größe einer Schaltfläche, um die Schaltflächentext und Bild enthalten.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|Aufgerufen, um eine Schaltfläche zu zeichnen.|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|Vom Framework zum Zeichnen des Rahmens einer Schaltfläche aufgerufen wird.|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Vom Framework zum Zeichnen des Fokusrechtecks für eine Schaltfläche aufgerufen wird.|  
|[CMFCButton::OnDrawText](#ondrawtext)|Aufgerufen, um den Text der Schaltfläche gezeichnet werden soll.|  
|[CMFCButton::OnFillBackground](#onfillbackground)|Vom Framework zum Zeichnen des Hintergrunds des Schaltflächentexts aufgerufen.|  
|[CMFCButton::SelectFont](#selectfont)|Ruft die Schriftart, die den angegebenen Gerätekontext zugeordnet ist.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Gibt an, ob ein Fokusrechteck um eine Schaltfläche zu zeichnen.|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Gibt an, ob eine BS_CHECKBOX-Schaltfläche markieren, wenn der Cursor darüber bewegt wird.|  
|[CMFCButton::m_bRightImage](#m_brightimage)|Gibt an, ob ein Bild auf der rechten Seite der Schaltfläche angezeigt werden soll.|  
|[CMFCButton::m_bTransparent](#m_btransparent)|Gibt an, ob die Schaltfläche transparent ist.|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Gibt die Ausrichtung des Schaltflächentexts.|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Gibt den Stil der Schaltfläche, z. B. randlose, Flatfiles, Semikolons flach oder 3D.|  
  
## <a name="remarks"></a>Hinweise  
 Andere Arten von Schaltflächen abgeleitet sind die `CMFCButton` Klasse, z. B. die [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) -Klasse, die Links unterstützt, und die `CMFCColorButton` -Klasse, die ein Farben-Auswahldialogfeld unterstützt.  
  
 Das Format der ein `CMFCButton` Objekt kann es sich *3D*, *flache*, *Semikolons flachen* oder *kein Rahmen*. Button-Text kann Links, oben oder einer Schaltfläche zentriert ausgerichtet werden. Zur Laufzeit können Sie steuern, ob die Schaltfläche Text, ein Bild oder Text und ein Bild anzeigt. Sie können auch angeben, die einen bestimmten Cursorbild angezeigt, wenn der Cursor über eine Schaltfläche bewegt wird.  
  
 Erstellen Sie ein Button-Steuerelement, entweder direkt im Code oder mithilfe der **MFC-Klassen-Assistent** -Tool und einer Dialogfeldvorlage. Wenn Sie ein Button-Steuerelement direkt erstellen, fügen Sie eine `CMFCButton` Variablen auf Ihre Anwendung, und rufen Sie dann den Konstruktor und `Create` Methoden die `CMFCButton` Objekt. Bei Verwendung der **MFC-Klassen-Assistent**, Hinzufügen einer `CButton` Variable für Ihre Anwendung, und ändern Sie den Typ der Variablen aus `CButton` zu `CMFCButton`.  
  
 Fügen Sie einen Nachrichtenzuordnungseintrag und einen Ereignishandler für jede Benachrichtigung, um Benachrichtigungen in einem Dialogfeld Feld Anwendung zu behandeln. Die Benachrichtigungen gesendet werden, indem eine `CMFCButton` Objekt sind identisch mit denen per ein `CButton` Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie die Eigenschaften der Schaltfläche mithilfe verschiedener Methoden in der `CMFCButton` Klasse. Das Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#31;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls&#32;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls&33;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbutton.h  
  
##  <a name="cleanup"></a>CMFCButton::CleanUp  
 Setzt die internen Variablen zurück und frei von zugeordneten Ressourcen wie Bilder, Bitmaps und Symbole.  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>CMFCButton::EnableFullTextTooltip  
 Gibt an, ob den vollständigen Text der QuickInfo in einem großen QuickInfo-Fenster oder eine abgeschnittene Version des Texts in einem kleinen QuickInfo-Fenster angezeigt.  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bOn`  
 `TRUE`gesamten Text angezeigt; `FALSE` um Text anzuzeigen, die abgeschnitten.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablemenufont"></a>CMFCButton::EnableMenuFont  
 Gibt an, ob die Schaltfläche Schriftart die Schriftart der Anwendung im Menü identisch ist.  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bOn`  
 `TRUE`auf die Anwendung im Menüschriftart als die Schaltfläche Schriftart zu verwenden. `FALSE` Systemschriftart verwenden. Die Standardeinstellung ist `TRUE`.  
  
 [in] `bRedraw`  
 `TRUE`um sofort die Bildschirmanzeige; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Methode an, dass die Schaltfläche Schriftart nicht verwenden, können Sie angeben, dass die Schriftart mit der [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) Methode. Wenn Sie eine Schriftart nicht auf allen angeben, legt das Framework eine Standardschriftart fest.  
  
##  <a name="enablewindowstheming"></a>CMFCButton::EnableWindowsTheming  
 Gibt an, ob die Schaltfläche Rahmenart für das aktuelle Windows-Design entspricht.  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`mit dem aktuellen Windows-Design zum Zeichnen des Rahmens der Schaltfläche; `FALSE` nicht den Windows-Designs zu verwenden. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wirkt sich auf alle Schaltflächen in der Anwendung, die von abgeleitet sind die `CMFCButton` Klasse.  
  
##  <a name="gettooltipctrl"></a>CMFCButton::GetToolTipCtrl  
 Gibt einen Verweis auf das zugrunde liegende QuickInfo-Steuerelement zurück.  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das zugrunde liegende QuickInfo-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isautocheck"></a>CMFCButton::IsAutoCheck  
 Gibt an, ob ein Kontrollkästchen oder ein Optionsfeld eine automatische Schaltfläche ist.  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche Format BS_AUTOCHECKBOX oder BS_AUTORADIOBUTTON; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isautorepeatcommandmode"></a>CMFCButton::IsAutorepeatCommandMode  
 Gibt an, ob eine Schaltfläche auf Automatisches Wiederholen-Modus festgelegt ist.  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche Wiederholen Auto-Modus festgelegt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCButton::SetAutorepeatMode](#setautorepeatmode) Methode, um eine Schaltfläche auf Automatisches Wiederholen-Modus festgelegt.  
  
##  <a name="ischeckbox"></a>CMFCButton::IsCheckBox  
 Gibt an, ob eine Schaltfläche ein Kontrollkästchen-Schaltfläche ist.  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche oder BS_CHECKBOX-BS_AUTOCHECKBOX hat. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ischecked"></a>CMFCButton::IsChecked  
 Gibt an, ob die aktuelle Schaltfläche aktiviert ist.  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die aktuelle Schaltfläche aktiviert ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet verschiedene Arten, um anzugeben, dass verschiedene Arten von Schaltflächen aktiviert sind. Z. B. ist ein Optionsfeld aktiviert, wenn es einen Punkt enthält. ein Kontrollkästchen aktiviert ist, wenn es enthält ein **X**.  
  
##  <a name="ishighlighted"></a>CMFCButton::IsHighlighted  
 Gibt an, ob eine Schaltfläche hervorgehoben wird.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche hervorgehoben ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Eine Schaltfläche wird hervorgehoben, wenn die Maus über die Schaltfläche bewegt wird.  
  
##  <a name="ispressed"></a>CMFCButton::IsPressed  
 Gibt an, ob eine Schaltfläche gedrückt und hervorgehoben wird.  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche gedrückt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ispushed"></a>CMFCButton::IsPushed  
 Gibt an, ob eine Schaltfläche gedrückt ist.  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche gedrückt ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isradiobutton"></a>CMFCButton::IsRadioButton  
 Gibt an, ob eine Schaltfläche ein Optionsfeld ist.  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Schaltflächenformat BS_RADIOBUTTON oder BS_AUTORADIOBUTTON. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="iswindowsthemingenabled"></a>CMFCButton::IsWindowsThemingEnabled  
 Gibt an, ob die Schaltfläche Rahmenart für das aktuelle Windows-Design entspricht.  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche Rahmenart für das aktuelle Windows-Design entspricht. andernfalls `FALSE`.  
  
##  <a name="m_bdrawfocus"></a>CMFCButton::m_bDrawFocus  
 Gibt an, ob ein Fokusrechteck um eine Schaltfläche zu zeichnen.  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bDrawFocus` Element `TRUE` angeben, dass das Framework ein Fokusrechteck um die Schaltfläche Text zeichnen und image, wenn die Schaltfläche den Fokus erhält.  
  
 Die `CMFCButton` Konstruktor initialisiert das Mitglied `TRUE`.  
  
##  <a name="m_bhighlightchecked"></a>CMFCButton::m_bHighlightChecked  
 Gibt an, ob eine BS_CHECKBOX-Schaltfläche markieren, wenn der Cursor darüber bewegt wird.  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bHighlightChecked` Element `TRUE` angeben, dass das Framework eine BS_CHECKBOX-Schaltfläche hervorgehoben wird, wenn die Maus darüber bewegt wird.  
  
##  <a name="m_brightimage"></a>CMFCButton::m_bRightImage  
 Gibt an, ob ein Bild auf der rechten Seite der Schaltfläche angezeigt werden soll.  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bRightImage` Element `TRUE` angeben, dass das Framework das Bild der Schaltfläche rechts neben der Schaltfläche die Bezeichnung angezeigt wird.  
  
##  <a name="m_btransparent"></a>CMFCButton::m_bTransparent  
 Gibt an, ob die Schaltfläche transparent ist.  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bTransparent` Element `TRUE` angeben, dass das Framework die Schaltfläche transparent machen. Die `CMFCButton` Konstruktor initialisiert das Mitglied `FALSE`.  
  
##  <a name="m_nalignstyle"></a>CMFCButton::m_nAlignStyle  
 Gibt die Ausrichtung des Schaltflächentexts.  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie eine der folgenden `CMFCButton::AlignStyle` Enumerationswerte, die die Ausrichtung des Schaltflächentexts an:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|ALIGN_CENTER|(Standard) Richtet den Text der Schaltfläche in der Mitte der Schaltfläche.|  
|ALIGN_LEFT|Richtet den Text der Schaltfläche auf der linken Seite der Schaltfläche.|  
|ALIGN_RIGHT|Richtet den Text der Schaltfläche rechts neben der Schaltfläche.|  
  
 Die `CMFCButton` -Konstruktor initialisiert das Mitglied ALIGN_CENTER.  
  
##  <a name="m_nflatstyle"></a>CMFCButton::m_nFlatStyle  
 Gibt den Stil der Schaltfläche, z. B. randlose, Flatfiles, Semikolons flach oder 3D.  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die `CMFCButton::m_nFlatStyle` Enumerationswerte, der die Darstellung einer Schaltfläche angeben.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(Standard) Die Schaltfläche wird auf hohe, dreidimensionale Seiten verfügen. Wenn die Schaltfläche geklickt wird, wird die Schaltfläche, die in einer Tiefe Einzug gedrückt werden.|  
|BUTTONSTYLE_FLAT|Wenn die Maus über die Schaltfläche nicht angehalten werden muss, wird die Schaltfläche zweidimensional sein wird, und keine ausgelöste Seiten. Wenn die Maus über die Schaltfläche bewegt wird, wird die Schaltfläche zu niedrige, dreidimensionale Seiten verfügen. Wenn die Schaltfläche geklickt wird, wird die Schaltfläche, die in eine flache Einzug gedrückt werden.|  
|BUTTONSTYLE_SEMIFLAT|Die Schaltfläche wird auf niedrige, dreidimensionale Seiten verfügen. Wenn die Schaltfläche geklickt wird, wird die Schaltfläche, die in einer Tiefe Einzug gedrückt werden.|  
|BUTTONSTYLE_NOBORDERS|Die Schaltfläche wird nicht Seiten ausgelöst haben und immer zweidimensionalen angezeigt. Die Schaltfläche wird nicht angezeigt, in einem Einzug gedrückt werden sollen, wenn darauf geklickt wird.|  
  
 Die `CMFCButton` Konstruktor initialisiert das Mitglied `BUTTONSTYLE_3D`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Werte für Festlegen der `m_nFlatStyle` -Membervariable in der `CMFCButton` Klasse. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#29;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>CMFCButton::OnDraw  
 Aufgerufen, um eine Schaltfläche zu zeichnen.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.  
  
 [in] `uiState`  
 Der aktuelle Status der Schaltfläche. Weitere Informationen finden Sie unter der `itemState` Mitglied der [DRAWITEMSTRUCT-Struktur](../../mfc/reference/drawitemstruct-structure.md) Thema.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code verwenden, um eine Schaltfläche zu zeichnen.  
  
##  <a name="ondrawborder"></a>CMFCButton::OnDrawBorder  
 Vom Framework zum Zeichnen des Rahmens einer Schaltfläche aufgerufen wird.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectClient`  
 Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.  
  
 [in] `uiState`  
 Der aktuelle Status der Schaltfläche. Weitere Informationen finden Sie unter der `itemState` Mitglied der [DRAWITEMSTRUCT-Struktur](../../mfc/reference/drawitemstruct-structure.md) Thema.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zum Zeichnen des Rahmens.  
  
##  <a name="ondrawfocusrect"></a>CMFCButton::OnDrawFocusRect  
 Vom Framework zum Zeichnen des Fokusrechtecks für eine Schaltfläche aufgerufen wird.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectClient`  
 Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zum Zeichnen des Fokusrechtecks verwenden.  
  
##  <a name="ondrawtext"></a>CMFCButton::OnDrawText  
 Aufgerufen, um den Text der Schaltfläche gezeichnet werden soll.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.  
  
 [in] `strText`  
 Der zu zeichnende Text.  
  
 [in] `uiDTFlags`  
 Flags, die angeben, wie den Text formatiert. Weitere Informationen finden Sie unter der `nFormat` Parameter von der [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext) Methode.  
  
 [in] `uiState`  
 (Reserviert).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code verwenden, um den Text der Schaltfläche gezeichnet werden soll.  
  
##  <a name="onfillbackground"></a>CMFCButton::OnFillBackground  
 Vom Framework zum Zeichnen des Hintergrunds des Schaltflächentexts aufgerufen.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectClient`  
 Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code verwenden, um den Hintergrund einer Schaltfläche zu zeichnen.  
  
##  <a name="selectfont"></a>CMFCButton::SelectFont  
 Ruft die Schriftart, die den angegebenen Gerätekontext zugeordnet ist.  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zu verwenden, um die Schriftart abzurufen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setautorepeatmode"></a>CMFCButton::SetAutorepeatMode  
 Wird eine Schaltfläche auf Automatisches Wiederholen.  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTimeDelay`  
 Eine nicht negative Zahl, die das Intervall zwischen Nachrichten angibt, die für das übergeordnete Fenster gesendet werden. Das Intervall in Millisekunden gemessen wird, und der Standardwert beträgt 500 Millisekunden. Geben Sie&0; (null), um Automatisches Wiederholen-Modus zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode bewirkt, dass die Schaltfläche WM_COMMAND-Meldungen an das übergeordnete Fenster ständig senden, bis die Maustaste losgelassen wird, oder der `nTimeDelay` -Parameter auf&0; (null) festgelegt ist.  
  
##  <a name="setcheckedimage"></a>CMFCButton::SetCheckedImage  
 Legt das Bild für die aktivierte Schaltfläche fest.  
  
```  
void SetCheckedImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetCheckedImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetCheckedImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hIcon`  
 Handle für das Symbol, das die Bitmap und die Maske für das neue Abbild enthält.  
  
 [in] `bAutoDestroy`  
 `TRUE`um anzugeben, dass die Bitmapressourcen automatisch gelöscht werden andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] `hIconHot`  
 Handle für das Symbol, das das Bild für den ausgewählten Zustand enthält.  
  
 [in] `hBitmap`  
 Handle für die Bitmap, die das Bild für den nicht ausgewählten Zustand enthält.  
  
 [in] `hBitmapHot`  
 Handle für die Bitmap mit dem Bild für den ausgewählten Status.  
  
 [in] `bMap3dColors`  
 Gibt die transparente Farbe des Hintergrunds der Schaltfläche. d. h. die Oberfläche der Schaltfläche. `TRUE`Verwenden Sie den Farbwert RGB (192, 192, 192); `FALSE` verwenden den Farbwert definiert `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `uiBmpResId`  
 Ressourcen-ID für das Bild nicht ausgewählt.  
  
 [in] `uiBmpHotResId`  
 Ressourcen-ID für das ausgewählte Bild.  
  
 [in] `hIconDisabled`  
 Handle für das Symbol für deaktivierten Bilds.  
  
 [in] `hBitmapDisabled`  
 Handle für die Bitmap, die deaktivierten Bilds enthält.  
  
 [in] `uiBmpDsblResID`  
 Ressourcen-ID der Bitmap deaktiviert.  
  
 [in] `bAlphaBlend`  
 `TRUE`nur 32-Bit-Images verwenden, die den alpha-Kanal zu verwenden; `FALSE`, nicht nur alpha-Kanal Bilder verwendet. Die Standardeinstellung ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfacecolor"></a>CMFCButton::SetFaceColor  
 Legt die Hintergrundfarbe für den Text der Schaltfläche fest.  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `crFace`  
 Ein Wert für den RGB-Farbe.  
  
 [in] `bRedraw`  
 `TRUE`den Bildschirm sofort neu zeichnen; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine neue Farbe des Hintergrunds der Schaltfläche (Schrift) definieren. Beachten Sie, dass der Hintergrund nicht gefüllt, wenn die [CMFCButton::m_bTransparent](#m_btransparent) Membervariable ist `TRUE`.  
  
##  <a name="setimage"></a>CMFCButton::SetImage  
 Legt das Bild für die Schaltfläche fest.  
  
```  
void SetImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hIcon`  
 Handle für das Symbol, das die Bitmap und die Maske für das neue Abbild enthält.  
  
 [in] `bAutoDestroy`  
 `TRUE`um anzugeben, dass die Bitmapressourcen automatisch gelöscht werden andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] `hIconHot`  
 Handle für das Symbol, das das Bild für den ausgewählten Zustand enthält.  
  
 [in] `hBitmap`  
 Handle für die Bitmap, die das Bild für den nicht ausgewählten Zustand enthält.  
  
 [in] `hBitmapHot`  
 Handle für die Bitmap mit dem Bild für den ausgewählten Status.  
  
 [in] `uiBmpResId`  
 Ressourcen-ID für das Bild nicht ausgewählt.  
  
 [in] `uiBmpHotResId`  
 Ressourcen-ID für das ausgewählte Bild.  
  
 [in] `bMap3dColors`  
 Gibt die transparente Farbe des Hintergrunds der Schaltfläche. d. h. die Oberfläche der Schaltfläche. `TRUE`Verwenden Sie den Farbwert RGB (192, 192, 192); `FALSE` verwenden den Farbwert definiert `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `hIconDisabled`  
 Handle für das Symbol für deaktivierten Bilds.  
  
 [in] `hBitmapDisabled`  
 Handle für die Bitmap, die deaktivierten Bilds enthält.  
  
 [in] `uiBmpDsblResID`  
 Ressourcen-ID der Bitmap deaktiviert.  
  
 [in] `bAlphaBlend`  
 `TRUE`nur 32-Bit-Images verwenden, die den alpha-Kanal zu verwenden; `FALSE`, nicht nur alpha-Kanal Bilder verwendet. Die Standardeinstellung ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Versionen von der `SetImage` -Methode in der `CMFCButton` Klasse. Das Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#31;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>CMFCButton::SetMouseCursor  
 Legt den Cursorbild.  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hcursor`  
 Das Handle des Cursors.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen Cursor-Abbild, z. B. den Hand-Cursor mit der Schaltfläche zuzuordnen. Der Cursor wird aus den Anwendungsressourcen geladen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetMouseCursor` -Methode in der `CMFCButton` Klasse. Das Beispiel ist Teil des Codes in der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#30;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>CMFCButton::SetMouseCursorHand  
 Setzt den Cursor auf das Bild einer Hand.  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Cursorbild einer Hand mit der Schaltfläche zuzuordnen. Der Cursor wird aus den Anwendungsressourcen geladen.  
  
##  <a name="setstdimage"></a>CMFCButton::SetStdImage  
 Verwendet ein `CMenuImages` Objekt, das das Bild der Schaltfläche festgelegt.  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `id`  
 Die Schaltfläche Image-Bezeichner, die in definiert ist die `CMenuImage::IMAGES_IDS` Enumeration. Die Image-Werte angeben, Bilder, z. B. Pfeile, Stifte und Optionsfelder.  
  
 [in] `state`  
 Eine der Schaltfläche Image Status-IDs, die in definiert ist die `CMenuImages::IMAGE_STATE` Enumeration. Die Image-Status geben Schaltflächenfarben, z. B. Schwarz, grau, hellen grau, weiß und dunklen Grau. Der Standardwert ist `CMenuImages::ImageBlack`.  
  
 [in] `idDisabled`  
 Die Schaltfläche Image-Bezeichner, die in definiert ist die `CMenuImage::IMAGES_IDS` Enumeration. Das Bild gibt an, dass die Schaltfläche deaktiviert ist. Der Standardwert ist das erste Schaltflächenbild ( `CMenuImages::IdArrowDown`).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settextcolor"></a>CMFCButton::SetTextColor  
 Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die nicht ausgewählt ist.  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrText`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settexthotcolor"></a>CMFCButton::SetTextHotColor  
 Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die ausgewählt wird.  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrTextHot`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settooltip"></a>CMFCButton::SetTooltip  
 Eine Schaltfläche eine QuickInfo zugeordnet.  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszToolTipText`  
 Zeiger auf den Text für die QuickInfo. Geben Sie NULL an, um die QuickInfo zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sizetocontent"></a>CMFCButton::SizeToContent  
 Ändert die Größe einer Schaltfläche, um die Schaltflächentext und Bild enthalten.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCalcOnly`  
 `TRUE`berechnen, aber nicht ändern, die neue Größe der Schaltfläche; `FALSE` ändern die Größe der Schaltfläche. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` -Objekt, das die neue Größe der Schaltfläche enthält.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig berechnet diese Methode eine neue Größe ein, die einen horizontalen Rand von 10 Pixel und einen vertikalen Rand von 5 Pixel enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl-Klasse](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton-Klasse](../../mfc/reference/cmfcmenubutton-class.md)

