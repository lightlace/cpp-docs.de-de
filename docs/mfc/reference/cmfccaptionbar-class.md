---
title: CMFCCaptionBar-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5131479af7f34f1cc43cf91adfd0bd3ac52a594b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722981"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar-Klasse
Ein `CMFCCaptionBar` Objekt ist eine Steuerleiste, die drei Elemente anzeigen können: eine Schaltfläche, eine Bezeichnung und eine Bitmap. Es kann jeweils nur ein Element eines Typs angezeigt werden. Sie können jedes Element links, rechts oder in der Mitte des Steuerelements positionieren. Sie können zudem den oberen und unteren Rand der Titelleiste flach oder dreidimensional darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::Create](#create)|Die Beschriftung-Steuerelement erstellt, und fügt es der `CMFCCaptionBar` Objekt.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Gibt an, ob ein weiterer Bereich dynamisch zwischen der Titelleiste und der zugehörigen übergeordneten Rahmen eingefügt werden kann. (Überschreibt [cbasepane:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|Aktiviert oder deaktiviert die Schaltfläche in der Titelleiste.|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|Gibt die Ausrichtung des angegebenen Elements zurück.|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Gibt zurück, die Rahmengröße der Titelleiste.|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Ruft das umschließende Rechteck der Schaltfläche auf der Titelleiste ab.|  
|[CMFCCaptionBar::GetMargin](#getmargin)|Gibt den Abstand zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung zurück.|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Gibt an, ob die Titelleiste in der Leiste Nachrichtenmodus ist.|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Entfernt das Bitmap-Bild von der Titelleiste an.|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|Entfernt die Schaltfläche mit den in der Titelleiste an.|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Entfernt das Symbol in der Titelleiste an.|  
|[CMFCCaptionBar::RemoveText](#removetext)|Entfernt die Bezeichnung aus der Titelleiste an.|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Legt fest, das Bitmap-Bild für die Titelleiste.|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Legt fest, die Rahmengröße der Titelleiste.|  
|[CMFCCaptionBar::SetButton](#setbutton)|Legt fest, die Schaltfläche für die Titelleiste.|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Gibt an, ob die Schaltfläche gedrückt bleibt.|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Legt die QuickInfo für die Schaltfläche fest.|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Legt fest, der die Rahmenart des der Titelleiste.|  
|[CMFCCaptionBar::SetIcon](#seticon)|Legt das Symbol für die Titelleiste fest.|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Legt die QuickInfo für das Bild für die Titelleiste an.|  
|[CMFCCaptionBar::SetMargin](#setmargin)|Legt den Abstand zwischen dem Rand des das Caption-Element und dem Rand des Steuerelements Beschriftung.|  
|[CMFCCaptionBar::SetText](#settext)|Legt fest, das die textbezeichnung für die Titelleiste.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Wird aufgerufen, durch das Framework auf der Hintergrund der Titelleiste gefüllt.|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Wird aufgerufen, durch das Framework zum Zeichnen des Rahmens der Titelleiste.|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Wird aufgerufen, durch das Framework die Beschriftung Befehlsleisten-Schaltfläche gezeichnet werden soll.|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Wird aufgerufen, durch das Framework die Beschriftung Leiste Bild gezeichnet werden soll.|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Wird aufgerufen, durch das Framework zum Zeichnen des Textes der Titelleiste.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Die Hintergrundfarbe der Titelleiste.|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Die Farbe des Rahmens der Titelleiste.|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Die Farbe des Textes der Titelleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Titelleiste zu erstellen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen der `CMFCCaptionBar` Objekt. In der Regel würden Sie die Titelleiste ein Rahmenfenster (Klasse) hinzufügen.  
  
2.  Rufen Sie die [CMFCCaptionBar::Create](#create) Methode, um das Beschriftung-Steuerelement zu erstellen, und fügen Sie ihn auf die `CMFCCaptionBar` Objekt.  
  
3.  Rufen Sie [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), und [CMFCCaptionBar::SetBitmap](#setbitmap)die Elemente der Beschriftung festlegen.  
  
 Wenn Sie das Button-Element festlegen, müssen Sie die Schaltfläche eine Befehls-ID zuweisen. Wenn der Benutzer auf die Schaltfläche klickt, leitet die Titelleiste der WM_COMMAND-Meldungen, die diese ID mit der übergeordneten Rahmenfensters haben.  
  
 Die Titelleiste kann auch im leistenmodus für Nachrichten, arbeiten, die in der Statusleiste emuliert, die in Microsoft Office 2007-Anwendungen angezeigt. Im leistenmodus für Nachrichten zeigt die Titelleiste, eine Bitmap, eine Nachricht und eine Schaltfläche (die in der Regel ein Dialogfeld wird geöffnet.) Sie können eine QuickInfo für die Bitmap zuweisen.  
  
 Rufen Sie zum Aktivieren der Modus "Balken" [CMFCCaptionBar::Create](#create) und den vierten Parameter (bIsMessageBarMode) auf "true" festgelegt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCCaptionBar` Klasse. Das Beispiel zeigt, wie Sie die Beschriftung-Steuerelement zu erstellen, legen Sie einen 3D-Rahmen der Titelleiste, legen Sie die Entfernung zwischen dem Rand der Beschriftung Leiste Elemente und dem Rand des Steuerelements Beschriftung in Pixel, legen Sie die Schaltfläche für die Titelleiste , legen Sie die QuickInfo für die Schaltfläche, legen Sie die textbezeichnung für die Titelleiste, legen Sie das Bitmap-Bild für die Titelleiste und legen Sie die QuickInfo für das Bild in der Titelleiste. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcaptionbar.h  
  
##  <a name="create"></a>  CMFCCaptionBar::Create  
 Die Beschriftung-Steuerelement erstellt, und fügt es der `CMFCCaptionBar` Objekt.  
  
```  
BOOL Create(
    DWORD dwStyle,  
    CWnd* pParentWnd,  
    UINT uID,  
    int nHeight=-1,  
    BOOL bIsMessageBarMode=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *dwStyle*  
 Der logische OR-Kombination der Formate Leiste Beschriftung.  
  
 *pParentWnd*  
 Das übergeordnete Fenster des Steuerelements Beschriftung.  
  
 *Benutzer-ID*  
 Die ID der Beschriftung-Steuerelement.  
  
 *nHeight*  
 Die Höhe in Pixel der Beschriftung-Steuerelement. Wenn sie-1 ist, wird die Höhe berechnet, gemäß die Höhe der das Symbol, das Text und die Schaltfläche, die die Beschriftung StatusBar-Steuerelement zeigt.  
  
 *bIsMessageBarMode*  
 True, wenn die Titelleiste in der Leiste Nachrichtenmodus. "False" andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Steuerelement Beschriftung erfolgreich erstellt wurde. "False" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CMFCCaptionBar` Objekt in zwei Schritten. Zuerst rufen Sie den Konstruktor, und rufen dann die `Create` -Methode, die das Windows-Steuerelement erstellt, und fügt es der `CMFCCaptionBar` Objekt.  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCCaptionBar::DoesAllowDynInsertBefore  
 Gibt an, ob ein weiterer Bereich dynamisch zwischen der Titelleiste und der zugehörigen übergeordneten Rahmen eingefügt werden kann.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt FALSE zurück, es sei denn, der außer Kraft gesetzt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablebutton"></a>  CMFCCaptionBar::EnableButton  
 Aktiviert oder deaktiviert die Schaltfläche in der Titelleiste.  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bAktivieren*<br/>
[in] TRUE, wenn die Schaltfläche "false" zu aktivieren, auf um die Schaltfläche zu deaktivieren.  
  
##  <a name="getalignment"></a>  CMFCCaptionBar::GetAlignment  
 Gibt die Ausrichtung des angegebenen Elements zurück.  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>Parameter  
*Elem*<br/>
[in] Ein Caption-Element der Leiste für die Ausrichtung abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ausrichtung eines Elements, z. B. eine Schaltfläche, eine Bitmap, Text oder ein Symbol.  
  
### <a name="remarks"></a>Hinweise  
 Die Ausrichtung des Elements ist einer der folgenden Werte möglich:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>  CMFCCaptionBar::GetBorderSize  
 Gibt zurück, die Rahmengröße der Titelleiste.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Rahmens in Pixel.  
  
##  <a name="getbuttonrect"></a>  CMFCCaptionBar::GetButtonRect  
 Ruft das umschließende Rechteck der Schaltfläche auf der Titelleiste ab.  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das die Koordinaten des umgebenden Rechtecks der Schaltfläche auf der Titelleiste enthält.  
  
##  <a name="getmargin"></a>  CMFCCaptionBar::GetMargin  
 Gibt den Abstand zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung zurück.  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Entfernung zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung in Pixel.  
  
##  <a name="ismessagebarmode"></a>  CMFCCaptionBar::IsMessageBarMode  
 Gibt an, ob die Titelleiste in der Leiste Nachrichtenmodus ist.  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Titelleiste in der Leiste Nachrichtenmodus. "False" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 In der Leiste Nachrichtenmodus zeigt die Titelleiste ein Images mit einer QuickInfo, eine Nachrichtentext und eine Schaltfläche.  
  
##  <a name="m_clrbarbackground"></a>  CMFCCaptionBar::m_clrBarBackground  
 Die Hintergrundfarbe der Titelleiste.  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>  CMFCCaptionBar::m_clrBarBorder  
 Die Farbe des Rahmens der Titelleiste.  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>  CMFCCaptionBar::m_clrBarText  
 Die Farbe des Textes der Titelleiste.  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>  CMFCCaptionBar::OnDrawBackground  
 Wird aufgerufen, durch das Framework auf der Hintergrund der Titelleiste gefüllt.  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Ein Zeiger auf den Gerätekontext, der der Titelleiste.  
  
*Rect*<br/>
[in] Das umschließende Rechteck ausgefüllt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die `OnDrawBackground` Methode wird aufgerufen, wenn der Hintergrund der Titelleiste wird gefüllt werden soll. Die standardmäßige Implementierung füllt den Hintergrund mithilfe der [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) Farbe.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste anzupassen.  
  
##  <a name="ondrawborder"></a>  CMFCCaptionBar::OnDrawBorder  
 Wird aufgerufen, durch das Framework zum Zeichnen des Rahmens der Titelleiste.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Einen Gerätekontext, der verwendet wird, um die Rahmen anzuzeigen.  
  
*Rect*<br/>
[in] Das umschließende Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verfügen die Rahmen für die flache.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste, Rahmen anzupassen.  
  
##  <a name="ondrawbutton"></a>  CMFCCaptionBar::OnDrawButton  
 Wird aufgerufen, durch das Framework die Beschriftung Befehlsleisten-Schaltfläche gezeichnet werden soll.  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext, der zur Anzeige der Schaltfläche verwendet wird.  
  
*Rect*<br/>
[in] Das umschließende Rechteck der Schaltfläche.  
  
*strButton*<br/>
[in] Die Beschriftung der Schaltfläche Text.  
  
*bAktiviert*<br/>
[in] True, wenn die Schaltfläche aktiviert ist. "False" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste die Schaltfläche anzupassen.  
  
##  <a name="ondrawimage"></a>  CMFCCaptionBar::OnDrawImage  
 Wird aufgerufen, durch das Framework die Beschriftung Leiste Bild gezeichnet werden soll.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext, der zur Anzeige des Bilds verwendet wird.  
  
*Rect*<br/>
[in] Gibt das umschließende Rechteck des Bilds an.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Image-Darstellung anzupassen.  
  
##  <a name="ondrawtext"></a>  CMFCCaptionBar::OnDrawText  
 Wird aufgerufen, durch das Framework zum Zeichnen des Textes der Titelleiste.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext, der zur Anzeige der Schaltfläche verwendet wird.  
  
*Rect*<br/>
[in] Das umschließende Rechteck des Texts.  
  
*strText*<br/>
[in] Die Textzeichenfolge angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung zeigt den Text mithilfe von `CDC::DrawText` und [CMFCCaptionBar::m_clrBarText](#m_clrbartext) Farbe.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung des Texts von der Titelleiste anzupassen.  
  
##  <a name="removebitmap"></a>  CMFCCaptionBar::RemoveBitmap  
 Entfernt das Bitmap-Bild von der Titelleiste an.  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>  CMFCCaptionBar::RemoveButton  
 Entfernt die Schaltfläche mit den in der Titelleiste an.  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Layout der Elemente der Beschriftung werden automatisch angepasst.  
  
##  <a name="removeicon"></a>  CMFCCaptionBar::RemoveIcon  
 Entfernt das Symbol in der Titelleiste an.  
  
```  
void RemoveIcon();
```  
  
##  <a name="removetext"></a>  CMFCCaptionBar::RemoveText  
 Entfernt die Bezeichnung aus der Titelleiste an.  
  
```  
void RemoveText();
```  
  
##  <a name="setbitmap"></a>  CMFCCaptionBar::SetBitmap  
 Legt fest, das Bitmap-Bild für die Titelleiste.  
  
```  
void SetBitmap(
    HBITMAP hBitmap,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

 
void SetBitmap(
    UINT uiBmpResID,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parameter  
*hBitmap*<br/>
[in] Das Handle für die Bitmap festlegen.  
  
*clrTransparent*<br/>
[in] Ein RGB-Wert, der angibt, die transparente Farbe des Bitmap.  
  
*bStretch*<br/>
[in] Bei "true", wird die Bitmap gestreckt, wenn es nicht auf das Bild, das Begrenzungsrechteck passt. Andernfalls wird die Bitmap nicht gestreckt.  
  
*bmpAlignment*<br/>
[in] Die Ausrichtung der Bitmap.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Bitmap in eine Titelleiste festzulegen.  
  
 Die vorherige Bitmap wird automatisch zerstört. Wenn die Titelleiste ein Symbol angezeigt, da Sie aufgerufen der [CMFCCaptionBar::SetIcon](#seticon) -Methode, die Bitmap wird nicht angezeigt, es sei denn, Sie, das Symbol "durch den Aufruf entfernen [CMFCCaptionBar::RemoveIcon](#removeicon).  
  
 Die Bitmap ausgerichtet wird gemäß der *BmpAlignment* Parameter.  Dieser Parameter kann einen der folgenden `BarElementAlignment`-Werte aufweisen:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>  CMFCCaptionBar::SetBorderSize  
 Legt fest, die Rahmengröße der Titelleiste.  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
*nSize*<br/>
[in] Die neue Größe, der die Beschriftung der Rahmen in Pixel.  
  
##  <a name="setbutton"></a>  CMFCCaptionBar::SetButton  
 Legt fest, die Schaltfläche für die Titelleiste.  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszLabel*  
 Die Beschriftung der Schaltfläche-Befehl.  
  
 *uiCmdUI*  
 Die Schaltfläche "-Befehls-ID.  
  
 *btnAlignmnet*  
 Die Ausrichtung.  
  
 *bHasDropDownArrow*  
 TRUE, wenn die Schaltfläche eine Dropdown-Pfeil anzeigt.  
  
##  <a name="setbuttonpressed"></a>  CMFCCaptionBar::SetButtonPressed  
 Gibt an, ob die Schaltfläche gedrückt bleibt.  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bPresed*  
 TRUE, wenn die Schaltfläche mit der ihren aktuellen Status, "false" andernfalls hält.  
  
##  <a name="setbuttontooltip"></a>  CMFCCaptionBar::SetButtonToolTip  
 Legt die QuickInfo für die Schaltfläche fest.  
  
```  
void SetButtonToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Parameter  
*lpszToolTip*<br/>
[in] Die QuickInfo-Beschriftung.  
  
*lpszDescription*<br/>
[in] Die QuickInfo-Beschreibung.  
  
##  <a name="setflatborder"></a>  CMFCCaptionBar::SetFlatBorder  
 Legt fest, der die Rahmenart des der Titelleiste.  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bFlat*<br/>
[in] TRUE, wenn der Rahmen der Titelleiste flach ist. FALSE, wenn der Rahmen 3D ist.  
  
##  <a name="seticon"></a>  CMFCCaptionBar::SetIcon  
 Legt das Symbol für die Titelleiste fest.  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parameter  
*hIcon*<br/>
[in] Das Handle für das Symbol fest.  
  
*iconAlignment*<br/>
[in] Die Ausrichtung des Symbols.  
  
### <a name="remarks"></a>Hinweise  
 Titelleisten können entweder Symbolen oder Bitmaps angezeigt. Finden Sie unter [CMFCCaptionBar::SetBitmap](#setbitmap) um herauszufinden, wie eine Bitmap angezeigt. Wenn Sie sowohl ein Symbol und eine Bitmap festlegen, wird das Symbol wird immer angezeigt. Rufen Sie [CMFCCaptionBar::RemoveIcon](#removeicon) um ein Symbol aus der Titelleiste zu entfernen.  
  
 Das Symbol orientiert sich gemäß der *IconAlignment* Parameter. Es kann eine der folgenden `BarElementAlignment` Werte:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>  CMFCCaptionBar::SetImageToolTip  
 Legt die QuickInfo für das Bild in der Titelleiste fest.  
  
```  
void SetImageToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Parameter  
*lpszToolTip*<br/>
[in] Der Text der QuickInfo.  
  
*lpszDescription*<br/>
[in] Die QuickInfo-Beschreibung.  
  
##  <a name="setmargin"></a>  CMFCCaptionBar::SetMargin  
 Legt den Abstand zwischen dem Rand des das Caption-Element und dem Rand des Steuerelements Beschriftung.  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>Parameter  
*nMargin*<br/>
[in] Die Entfernung zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung in Pixel.  
  
##  <a name="settext"></a>  CMFCCaptionBar::SetText  
 Legt fest, das die textbezeichnung für die Titelleiste.  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parameter  
*strText*<br/>
[in] Die Textzeichenfolge festlegen.  
  
*textAlignment*<br/>
[in] Die Ausrichtung des Texts.  
  
### <a name="remarks"></a>Hinweise  
 Die textbezeichnung ausgerichtet wird gemäß der *TextAlignment* Parameter. Es kann eine der folgenden `BarElementAlignment` Werte:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
