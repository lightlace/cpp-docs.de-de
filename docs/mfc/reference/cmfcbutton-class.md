---
title: CMFCButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd30c9f27d83e7d4cfaf9b993b258b069f73dc4
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039231"
---
# <a name="cmfcbutton-class"></a>CMFCButton-Klasse
Die `CMFCButton` Klasse fügt Funktionen für die [CButton](../../mfc/reference/cbutton-class.md) Klasse z. B. Ausrichten des Schaltflächentexts, Kombinieren von Schaltflächentext mit einem Bild, Auswählen eines Cursors und Festlegen einer QuickInfo.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCButton : public CButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|Standardkonstruktor|  
|`CMFCButton::~CMFCButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCButton::CleanUp](#cleanup)|Setzt die interne Variablen und zugeordnete Ressourcen wie Bilder, Bitmaps und Symbole freigegeben werden.|  
|`CMFCButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCButton::DrawItem`|Wird vom Framework aufgerufen, wenn sich ein Darstellungsaspekt eines eine Ownerdrawn-Schaltfläche geändert hat. (Überschreibt [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Gibt an, ob der vollständige Text einer QuickInfo in einem großen QuickInfo-Fenster oder eine abgeschnittene Version des Texts in einem kleinen QuickInfo-Fenster angezeigt werden soll.|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|Gibt an, ob die Schaltfläche Schriftart die Schriftart der Anwendung im Menü identisch ist.|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Gibt an, ob das aktuelle Windows-Design die Art des Rahmens Schaltfläche entspricht.|  
|`CMFCButton::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Gibt einen Verweis auf die zugrunde liegenden QuickInfo-Steuerelement.|  
|[CMFCButton::IsAutoCheck](#isautocheck)|Gibt an, ob ein Kontrollkästchen- oder Optionsfeld eine Schaltfläche "automatisch" ist.|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Gibt an, ob eine Schaltfläche zum automatischen als dem Wiederholungsmodus festgelegt ist.|  
|[CMFCButton::IsCheckBox](#ischeckbox)|Gibt an, ob eine Schaltfläche ein Kontrollkästchen-Schaltfläche ist.|  
|[CMFCButton::IsChecked](#ischecked)|Gibt an, ob die aktuelle Schaltfläche aktiviert ist.|  
|[CMFCButton::IsHighlighted](#ishighlighted)|Gibt an, ob eine Schaltfläche hervorgehoben ist.|  
|[CMFCButton::IsPressed](#ispressed)|Gibt an, ob eine Schaltfläche abgelegt und hervorgehoben ist.|  
|[CMFCButton::IsPushed](#ispushed)|Gibt an, ob eine Schaltfläche gedrückt wird.|  
|[CMFCButton::IsRadioButton](#isradiobutton)|Gibt an, ob eine Schaltfläche ein Optionsfeld ist.|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Gibt an, ob das aktuelle Windows-Design die Art des Rahmens Schaltfläche entspricht.|  
|`CMFCButton::OnDrawParentBackground`|Zeichnet den Hintergrund des übergeordneten eine Schaltfläche im angegebenen Bereich. (Überschreibt [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Legt eine Schaltfläche zum automatischen als dem Wiederholungsmodus fest.|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Legt das Bild für die aktivierte Schaltfläche fest.|  
|[CMFCButton::SetFaceColor](#setfacecolor)|Legt die Hintergrundfarbe für den Text der Schaltfläche fest.|  
|[CMFCButton::SetImage](#setimage)|Legt das Bild für eine Schaltfläche fest.|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|Legt den Cursorbild.|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|Setzt den Cursor in das Image der Form einer Hand an.|  
|[CMFCButton::SetStdImage](#setstdimage)|Verwendet eine `CMenuImages` Objekt, das das Schaltflächenbild festgelegt.|  
|[CMFCButton::SetTextColor](#settextcolor)|Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die nicht ausgewählt ist.|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die ausgewählt wird.|  
|[CMFCButton::SetTooltip](#settooltip)|Ordnet eine QuickInfo mit einer Schaltfläche an.|  
|[CMFCButton::SizeToContent](#sizetocontent)|Ändert die Größe einer Schaltfläche, um die Schaltflächentext und Bild enthalten.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework eine Schaltfläche gezeichnet werden soll.|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|Wird aufgerufen, durch das Framework den Rahmen einer Schaltfläche gezeichnet werden soll.|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Wird aufgerufen, durch das Framework Fokusrechtecks für eine Schaltfläche gezeichnet werden soll.|  
|[CMFCButton::OnDrawText](#ondrawtext)|Wird aufgerufen, durch das Framework den Text der Schaltfläche gezeichnet werden soll.|  
|[CMFCButton::OnFillBackground](#onfillbackground)|Wird durch das Framework zum Zeichnen des Hintergrunds des Schaltflächentexts aufgerufen.|  
|[CMFCButton::SelectFont](#selectfont)|Ruft die Schriftart, die den angegebenen Gerätekontext zugeordnet ist.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Gibt an, ob ein Fokusrechteck um eine Schaltfläche zu zeichnen.|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Gibt an, ob eine BS_CHECKBOX-Schaltfläche zu markieren, wenn der Cursor darüber bewegt wird.|  
|[CMFCButton::m_bRightImage](#m_brightimage)|Gibt an, ob ein Bild auf der rechten Seite der Schaltfläche angezeigt werden soll.|  
|[CMFCButton::m_bTransparent](#m_btransparent)|Gibt an, ob die Schaltfläche transparent ist.|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Gibt die Ausrichtung des Schaltflächentexts.|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Gibt die Art der Schaltfläche, z. B. randlos, Flatfiles, Semikolon flachen oder 3D.|  
  
## <a name="remarks"></a>Hinweise  
 Andere Arten von Schaltflächen abgeleitet sind die `CMFCButton` Klasse, z. B. die [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) -Klasse, die Hyperlinks unterstützt, und die `CMFCColorButton` Klasse, die ein Farben-Auswahldialogfeld unterstützt.  
  
 Die Art des eine `CMFCButton` Objekt kann es sich *3D*, *Flatfile*, *Semikolon flachen* oder *kein Rahmen*. Als Schaltflächentext kann Links, oben oder in der Mitte einer Schaltfläche ausgerichtet werden. Zur Laufzeit können Sie steuern, ob die Schaltfläche Text, ein Bild oder Text und ein Bild anzeigt. Sie können auch angeben, dass eine bestimmte Cursorbild angezeigt werden, wenn der Cursor über eine Schaltfläche bewegt wird.  
  
 Erstellen Sie ein Button-Steuerelement aus, entweder direkt im Code oder mithilfe der **MFC-Klassen-Assistent** Tool und einer Dialogfeldvorlage. Wenn Sie direkt zu einem Schaltflächen-Steuerelement erstellen, fügen Sie eine `CMFCButton` Variablen auf Ihre Anwendung, und rufen Sie dann den Konstruktor und `Create` Methoden die `CMFCButton` Objekt. Bei Verwendung der **MFC-Klassen-Assistent**, Hinzufügen einer `CButton` -Variablen an die Anwendung, und ändern Sie den Typ der Variablen aus `CButton` auf `CMFCButton`.  
  
 Fügen Sie zum Verarbeiten von benachrichtigungsmeldungen in einem Dialogfeld Feld Anwendung eine Nachrichtenzuordnungseintrag und einen Ereignishandler für jede Benachrichtigung aus. Die Benachrichtigungen gesendet werden, indem eine `CMFCButton` Objekt sind identisch mit denen per ein `CButton` Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Eigenschaften der Schaltfläche Konfigurieren mithilfe verschiedener Methoden in der `CMFCButton` Klasse. Das Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbutton.h  
  
##  <a name="cleanup"></a>  CMFCButton::CleanUp  
 Setzt die interne Variablen und zugeordnete Ressourcen wie Bilder, Bitmaps und Symbole freigegeben werden.  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>  CMFCButton::EnableFullTextTooltip  
 Gibt an, ob der vollständige Text einer QuickInfo in einem großen QuickInfo-Fenster oder eine abgeschnittene Version des Texts in einem kleinen QuickInfo-Fenster angezeigt werden soll.  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *BAM*  
 `TRUE` gesamten Text angezeigt; `FALSE` zum Anzeigetext abgeschnitten.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablemenufont"></a>  CMFCButton::EnableMenuFont  
 Gibt an, ob die Schaltfläche Schriftart die Schriftart der Anwendung im Menü identisch ist.  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *BAM*  
 `TRUE` die Anwendung im Menüschriftart als der Schaltfläche Schriftart verwendet; `FALSE` Systemschriftart verwenden. Die Standardeinstellung ist `TRUE`.  
  
 [in] *bRedraw*  
 `TRUE` auf den Bildschirm sofort neu gezeichnet werden; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Methode nicht auf die Schaltfläche Schriftart angeben verwenden, können Sie angeben, dass die Schriftart, mit der [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) Methode. Wenn Sie eine Schriftart überhaupt nicht angeben, legt das Framework eine Standardschriftart fest.  
  
##  <a name="enablewindowstheming"></a>  CMFCButton::EnableWindowsTheming  
 Gibt an, ob das aktuelle Windows-Design die Art des Rahmens Schaltfläche entspricht.  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 `TRUE` das aktuelle Windows-Design zum Zeichnen des Rahmens Schaltfläche verwenden; `FALSE` des Windows-Designs nicht verwendet. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wirkt sich auf alle Schaltflächen in der Anwendung, die abgeleitet sind die `CMFCButton` Klasse.  
  
##  <a name="gettooltipctrl"></a>  CMFCButton::GetToolTipCtrl  
 Gibt einen Verweis auf die zugrunde liegenden QuickInfo-Steuerelement.  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das zugrunde liegende QuickInfo-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isautocheck"></a>  CMFCButton::IsAutoCheck  
 Gibt an, ob ein Kontrollkästchen- oder Optionsfeld eine Schaltfläche "automatisch" ist.  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Schaltfläche "" formatieren Sie BS_AUTOCHECKBOX oder BS_AUTORADIOBUTTON; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isautorepeatcommandmode"></a>  CMFCButton::IsAutorepeatCommandMode  
 Gibt an, ob eine Schaltfläche zum automatischen als dem Wiederholungsmodus festgelegt ist.  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche zum automatischen als dem Wiederholungsmodus festgelegt ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCButton::SetAutorepeatMode](#setautorepeatmode) Methode, um eine Schaltfläche zum automatischen als dem Wiederholungsmodus einzurichten.  
  
##  <a name="ischeckbox"></a>  CMFCButton::IsCheckBox  
 Gibt an, ob eine Schaltfläche ein Kontrollkästchen-Schaltfläche ist.  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche mit der BS_CHECKBOX oder BS_AUTOCHECKBOX-Format hat. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ischecked"></a>  CMFCButton::IsChecked  
 Gibt an, ob die aktuelle Schaltfläche aktiviert ist.  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Schaltfläche mit der aktuellen überprüft wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet verschiedene Möglichkeiten, um anzugeben, dass verschiedene Arten von Schaltflächen überprüft werden. Ein Optionsfeld ist z. B. überprüft, wenn es sich um einen Punkt enthält. ein Kontrollkästchen aktiviert ist, wenn es enthält eine **X**.  
  
##  <a name="ishighlighted"></a>  CMFCButton::IsHighlighted  
 Gibt an, ob eine Schaltfläche hervorgehoben ist.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche hervorgehoben ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Eine Schaltfläche wird hervorgehoben, wenn die Maus über der Schaltfläche bewegt wird.  
  
##  <a name="ispressed"></a>  CMFCButton::IsPressed  
 Gibt an, ob eine Schaltfläche abgelegt und hervorgehoben ist.  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche aufgerufen werden. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ispushed"></a>  CMFCButton::IsPushed  
 Gibt an, ob eine Schaltfläche gedrückt wird.  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche "" abgelegt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isradiobutton"></a>  CMFCButton::IsRadioButton  
 Gibt an, ob eine Schaltfläche ein Optionsfeld ist.  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Schaltflächenformat BS_RADIOBUTTON oder BS_AUTORADIOBUTTON. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="iswindowsthemingenabled"></a>  CMFCButton::IsWindowsThemingEnabled  
 Gibt an, ob das aktuelle Windows-Design die Art des Rahmens Schaltfläche entspricht.  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das aktuelle Windows-Design die Art des Rahmens Schaltfläche entspricht; andernfalls `FALSE`.  
  
##  <a name="m_bdrawfocus"></a>  CMFCButton::m_bDrawFocus  
 Gibt an, ob ein Fokusrechteck um eine Schaltfläche zu zeichnen.  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bDrawFocus` Element `TRUE` angeben, dass das Framework wird ein Fokusrechteck um Text der Schaltfläche zu zeichnen und Abbild, wenn die Schaltfläche "" den Fokus erhält.  
  
 Die `CMFCButton` Konstruktor initialisiert dieses Element `TRUE`.  
  
##  <a name="m_bhighlightchecked"></a>  CMFCButton::m_bHighlightChecked  
 Gibt an, ob eine BS_CHECKBOX-Schaltfläche zu markieren, wenn der Cursor darüber bewegt wird.  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bHighlightChecked` Element `TRUE` um anzugeben, dass das Framework eine BS_CHECKBOX-Schaltfläche hervorgehoben wird, wenn der Mauszeiger darüber bewegt wird.  
  
##  <a name="m_brightimage"></a>  CMFCButton::m_bRightImage  
 Gibt an, ob ein Bild auf der rechten Seite der Schaltfläche angezeigt werden soll.  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bRightImage` Element `TRUE` um anzugeben, dass das Framework das Bild der Schaltfläche rechts neben der Schaltfläche die Bezeichnung angezeigt wird.  
  
##  <a name="m_btransparent"></a>  CMFCButton::m_bTransparent  
 Gibt an, ob die Schaltfläche transparent ist.  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die `m_bTransparent` Member `TRUE` um anzugeben, dass das Framework die Schaltfläche transparent erkennen lässt. Die `CMFCButton` Konstruktor initialisiert dieses Element `FALSE`.  
  
##  <a name="m_nalignstyle"></a>  CMFCButton::m_nAlignStyle  
 Gibt die Ausrichtung des Schaltflächentexts.  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie eine der folgenden `CMFCButton::AlignStyle` -Enumerationswerte anwenden, um die Ausrichtung des Schaltflächentexts angeben:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|ALIGN_CENTER|(Standard) Richtet den Schaltflächentext in der Mitte der Schaltfläche.|  
|ALIGN_LEFT|Richtet den Text der Schaltfläche auf der linken Seite der Schaltfläche aus.|  
|ALIGN_RIGHT|Richtet den Text der Schaltfläche rechts neben der Schaltfläche.|  
  
 Die `CMFCButton` Konstruktor initialisiert dieses Element ALIGN_CENTER.  
  
##  <a name="m_nflatstyle"></a>  CMFCButton::m_nFlatStyle  
 Gibt die Art der Schaltfläche, z. B. randlos, Flatfiles, Semikolon flachen oder 3D.  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die `CMFCButton::m_nFlatStyle` Enumerationswerte, der die Darstellung einer Schaltfläche festzulegen.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(Standard) Die Schaltfläche wird auf hohe, dreidimensionale Seiten verfügen. Wenn die Schaltfläche geklickt wird, wird die Schaltfläche in einen tiefen Einzug gedrückt werden angezeigt.|  
|BUTTONSTYLE_FLAT|Wenn die Maus über der Schaltfläche nicht angehalten werden muss, wird die Schaltfläche ist anscheinend zweidimensionalen und verfügt nicht über die ausgelöste Seiten. Wenn die Maus über der Schaltfläche bewegt wird, wird die Schaltfläche zu niedrige, dreidimensionale Seiten verfügen. Wenn die Schaltfläche geklickt wird, wird die Schaltfläche in eine flache Einzug gedrückt werden angezeigt.|  
|BUTTONSTYLE_SEMIFLAT|Die Schaltfläche wird auf niedrige, dreidimensionale Seiten verfügen. Wenn die Schaltfläche geklickt wird, wird die Schaltfläche in einen tiefen Einzug gedrückt werden angezeigt.|  
|BUTTONSTYLE_NOBORDERS|Die Schaltfläche wird nicht Seiten ausgelöst haben und zweidimensionalen wird immer angezeigt. Die Schaltfläche wird nicht angezeigt, in einem Einzug gedrückt werden, wenn darauf geklickt wird.|  
  
 Die `CMFCButton` Konstruktor initialisiert dieses Element `BUTTONSTYLE_3D`.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht das Festlegen der Werte der `m_nFlatStyle` Membervariable in der `CMFCButton` Klasse. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>  CMFCButton::OnDraw  
 Wird aufgerufen, durch das Framework eine Schaltfläche gezeichnet werden soll.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *Rect*  
 Ein Verweis auf ein Rechteck, das die Schaltfläche "" umschließt.  
  
 [in] *UiState*  
 Der aktuelle Zustand der Schaltfläche. Weitere Informationen finden Sie unter der `itemState` Mitglied der [DRAWITEMSTRUCT-Struktur](../../mfc/reference/drawitemstruct-structure.md) Thema.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zu verwenden, um eine Schaltfläche gezeichnet werden soll.  
  
##  <a name="ondrawborder"></a>  CMFCButton::OnDrawBorder  
 Wird aufgerufen, durch das Framework den Rahmen einer Schaltfläche gezeichnet werden soll.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *RectClient*  
 Ein Verweis auf ein Rechteck, das die Schaltfläche "" umschließt.  
  
 [in] *UiState*  
 Der aktuelle Zustand der Schaltfläche. Weitere Informationen finden Sie unter der `itemState` Mitglied der [DRAWITEMSTRUCT-Struktur](../../mfc/reference/drawitemstruct-structure.md) Thema.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zu verwenden, um den Rahmen gezeichnet werden soll.  
  
##  <a name="ondrawfocusrect"></a>  CMFCButton::OnDrawFocusRect  
 Wird aufgerufen, durch das Framework Fokusrechtecks für eine Schaltfläche gezeichnet werden soll.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *RectClient*  
 Ein Verweis auf ein Rechteck, das die Schaltfläche "" umschließt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zu verwenden, um das Fokusrechteck gezeichnet werden soll.  
  
##  <a name="ondrawtext"></a>  CMFCButton::OnDrawText  
 Wird aufgerufen, durch das Framework den Text der Schaltfläche gezeichnet werden soll.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *Rect*  
 Ein Verweis auf ein Rechteck, das die Schaltfläche "" umschließt.  
  
 [in] *StrText*  
 Der zu zeichnende Text.  
  
 [in] *UiDTFlags*  
 Flags, die angeben, wie Sie den Text zu formatieren. Weitere Informationen finden Sie unter der *nFormat* Parameter von der [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext) Methode.  
  
 [in] *UiState*  
 (Reserviert).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zu verwenden, um den Text der Schaltfläche gezeichnet werden soll.  
  
##  <a name="onfillbackground"></a>  CMFCButton::OnFillBackground  
 Wird durch das Framework zum Zeichnen des Hintergrunds des Schaltflächentexts aufgerufen.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *RectClient*  
 Ein Verweis auf ein Rechteck, das die Schaltfläche "" umschließt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zu verwenden, um den Hintergrund einer Schaltfläche gezeichnet werden soll.  
  
##  <a name="selectfont"></a>  CMFCButton::SelectFont  
 Ruft die Schriftart, die den angegebenen Gerätekontext zugeordnet ist.  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Überschreiben Sie diese Methode, um Ihren eigenen Code zu verwenden, um die Schriftart abzurufen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setautorepeatmode"></a>  CMFCButton::SetAutorepeatMode  
 Legt eine Schaltfläche zum automatischen als dem Wiederholungsmodus fest.  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nTimeDelay*  
 Eine nicht negative Zahl, die das Intervall zwischen Nachrichten angibt, die an das übergeordnete Fenster gesendet werden. Das Intervall wird in Millisekunden gemessen und der Standardwert beträgt 500 Millisekunden. Geben Sie 0 (null), um die Auto-Repeat-Modus zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode bewirkt, dass die Schaltfläche, um ständig WM_COMMAND-Meldungen an das übergeordnete Fenster senden, bis die Maustaste losgelassen wird, oder die *nTimeDelay* Parameter auf 0 (null) festgelegt ist.  
  
##  <a name="setcheckedimage"></a>  CMFCButton::SetCheckedImage  
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
 [in] *hIcon*  
 Handle für das Symbol, das mithilfe einer Bitmap und eine Maske für das neue Abbild enthält.  
  
 [in] *bAutoDestroy*  
 `TRUE` um anzugeben, dass Bitmapressourcen automatisch; zerstört werden. andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] *hIconHot*  
 Handle für das Symbol, das das Bild für den ausgewählten Zustand enthält.  
  
 [in] *hBitmap*  
 Handle für die Bitmap mit dem Bild für den Status nicht aktiviert.  
  
 [in] *hBitmapHot*  
 Handle für eine Bitmap, die das Bild für den ausgewählten Zustand enthält.  
  
 [in] *bMap3dColors*  
 Gibt eine transparente Farbe für den Hintergrund der Schaltfläche. d. h. auf dem Zifferblatt der Schaltfläche. `TRUE` Verwenden Sie den Farbwert RGB (192, 192, 192) `FALSE` verwenden den Farbwert durch definierten `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] *UiBmpResId*  
 Ressourcen-ID für das Bild nicht ausgewählt.  
  
 [in] *UiBmpHotResId*  
 Ressourcen-ID für das ausgewählte Image.  
  
 [in] *hIconDisabled*  
 Handle für das Symbol für deaktivierten Bilds.  
  
 [in] *hBitmapDisabled*  
 Handle für eine Bitmap, die das deaktivierte Bild enthält.  
  
 [in] *UiBmpDsblResID*  
 Ressourcen-ID der Bitmap für die deaktiviert.  
  
 [in] *bAlphaBlend*  
 `TRUE` nur 32-Bit-Images verwenden, die den alpha-Kanal zu verwenden; `FALSE`, nicht nur die Bilder alpha-Kanal zu verwenden. Die Standardeinstellung ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfacecolor"></a>  CMFCButton::SetFaceColor  
 Legt die Hintergrundfarbe für den Text der Schaltfläche fest.  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CrFace*  
 Ein Wert für den RGB-Farbe.  
  
 [in] *bRedraw*  
 `TRUE` auf den Bildschirm sofort neu gezeichnet werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine neue Füllfarbe für den Hintergrund der Schaltfläche (Schrift) zu definieren. Beachten Sie, dass der Hintergrund nicht gefüllt, wenn die [CMFCButton::m_bTransparent](#m_btransparent) Membervariable wird `TRUE`.  
  
##  <a name="setimage"></a>  CMFCButton::SetImage  
 Legt das Bild für eine Schaltfläche fest.  
  
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
 [in] *hIcon*  
 Handle für das Symbol, das mithilfe einer Bitmap und eine Maske für das neue Abbild enthält.  
  
 [in] *bAutoDestroy*  
 `TRUE` um anzugeben, dass Bitmapressourcen automatisch; zerstört werden. andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] *hIconHot*  
 Handle für das Symbol, das das Bild für den ausgewählten Zustand enthält.  
  
 [in] *hBitmap*  
 Handle für die Bitmap mit dem Bild für den Status nicht aktiviert.  
  
 [in] *hBitmapHot*  
 Handle für eine Bitmap, die das Bild für den ausgewählten Zustand enthält.  
  
 [in] *UiBmpResId*  
 Ressourcen-ID für das Bild nicht ausgewählt.  
  
 [in] *UiBmpHotResId*  
 Ressourcen-ID für das ausgewählte Image.  
  
 [in] *bMap3dColors*  
 Gibt eine transparente Farbe für den Hintergrund der Schaltfläche. d. h. auf dem Zifferblatt der Schaltfläche. `TRUE` Verwenden Sie den Farbwert RGB (192, 192, 192) `FALSE` verwenden den Farbwert durch definierten `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] *hIconDisabled*  
 Handle für das Symbol für deaktivierten Bilds.  
  
 [in] *hBitmapDisabled*  
 Handle für eine Bitmap, die das deaktivierte Bild enthält.  
  
 [in] *UiBmpDsblResID*  
 Ressourcen-ID der Bitmap für die deaktiviert.  
  
 [in] *bAlphaBlend*  
 `TRUE` nur 32-Bit-Images verwenden, die den alpha-Kanal zu verwenden; `FALSE`, nicht nur die Bilder alpha-Kanal zu verwenden. Die Standardeinstellung ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Versionen der `SetImage` Methode in der `CMFCButton` Klasse. Das Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>  CMFCButton::SetMouseCursor  
 Legt den Cursorbild.  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Hcursor*  
 Das Handle eines Cursors.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen Cursorbilds, z. B. den Hand-Cursor, mit der Schaltfläche zuzuordnen. Der Cursor wird aus den Anwendungsressourcen geladen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetMouseCursor` Methode in der `CMFCButton` Klasse. Das Beispiel ist Teil des Codes in der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>  CMFCButton::SetMouseCursorHand  
 Setzt den Cursor in das Image der Form einer Hand an.  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den Cursorbild einer Hand mit der Schaltfläche zuzuordnen. Der Cursor wird aus den Anwendungsressourcen geladen.  
  
##  <a name="setstdimage"></a>  CMFCButton::SetStdImage  
 Verwendet eine `CMenuImages` Objekt, das das Schaltflächenbild festgelegt.  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Id*  
 Eine der Schaltfläche Image-IDs, die in definiert ist die `CMenuImage::IMAGES_IDS` Enumeration. Bilder, z. B. Optionsfelder, Pins dienenden Pfeile angeben, die Image-Werte.  
  
 [in] *Zustand*  
 Eine der Schaltfläche Image Status-IDs, die in definiert ist die `CMenuImages::IMAGE_STATE` Enumeration. Die Bildstatus geben Schaltflächenfarben, z. B. black, grauen, hellen grau-weißen und dunkel grau. Der Standardwert ist `CMenuImages::ImageBlack`.  
  
 [in] *IdDisabled*  
 Eine der Schaltfläche Image-IDs, die in definiert ist die `CMenuImage::IMAGES_IDS` Enumeration. Das Bild zeigt an, dass die Schaltfläche deaktiviert ist. Der Standardwert ist das erste Schaltflächenbild ( `CMenuImages::IdArrowDown`).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settextcolor"></a>  CMFCButton::SetTextColor  
 Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die nicht ausgewählt ist.  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *ClrText*  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settexthotcolor"></a>  CMFCButton::SetTextHotColor  
 Legt die Farbe des Schaltflächentexts für eine Schaltfläche, die ausgewählt wird.  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *ClrTextHot*  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settooltip"></a>  CMFCButton::SetTooltip  
 Ordnet eine QuickInfo mit einer Schaltfläche an.  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszToolTipText*  
 Zeiger auf den Text für die QuickInfo. Geben Sie NULL an, wenn die QuickInfo zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sizetocontent"></a>  CMFCButton::SizeToContent  
 Ändert die Größe einer Schaltfläche, um die Schaltflächentext und Bild enthalten.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bCalcOnly*  
 `TRUE` berechnen, jedoch nicht ändern, die neue Größe der Schaltfläche; `FALSE` so ändern Sie die Größe der Schaltfläche. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` Objekt, das die neue Größe der Schaltfläche enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode berechnet standardmäßig eine neue Größe, die einen horizontalen Rand von 10 Pixel und einem vertikalen Rand von 5 Pixel enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl-Klasse](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton-Klasse](../../mfc/reference/cmfcmenubutton-class.md)
