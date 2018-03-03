---
title: CMFCCaptionBar-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c23129c1ac857e812b0da837b19322741087934
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CMFCCaptionBar::Create](#create)|Das Caption-Steuerelement erstellt, und fügt es der `CMFCCaptionBar` Objekt.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Gibt an, ob es sich bei einem anderen Bereich zwischen der Titelleiste und deren übergeordneten Rahmen dynamisch eingefügt werden kann. (Überschreibt [cbasepane:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|Aktiviert oder deaktiviert die Taste auf der Titelleiste.|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|Gibt die Ausrichtung des angegebenen Elements zurück.|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Der Border Size Rand der Titelleiste wird zurückgegeben.|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Ruft das umschließende Rechteck der Schaltflächen auf der Titelleiste ab.|  
|[CMFCCaptionBar::GetMargin](#getmargin)|Gibt den Abstand zwischen dem Rand der Beschriftung menübandleisten-Elementen und den Rand des Steuerelements Beschriftung zurück.|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Gibt an, ob die Titelleiste in die Nachricht leistenmodus ist.|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Entfernt das Bitmap-Bild aus der Titelleiste an.|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|Entfernt die Schaltfläche aus der Titelleiste.|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Entfernt das Symbol in der Titelleiste an.|  
|[CMFCCaptionBar::RemoveText](#removetext)|Entfernt die Beschriftung in der Titelleiste an.|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Legt das Bitmap-Bild für die Titelleiste.|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Legt fest, der Border Size Rand der Titelleiste.|  
|[CMFCCaptionBar::SetButton](#setbutton)|Legt die Schaltfläche für die Titelleiste.|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Gibt an, ob die Schaltfläche gedrückt bleibt.|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Legt die QuickInfo für die Schaltfläche fest.|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Legt die Rahmenart der Titelleiste an.|  
|[CMFCCaptionBar::SetIcon](#seticon)|Legt das Symbol für eine Titelleiste an.|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Legt die QuickInfo für das Bild für die Titelleiste.|  
|[CMFCCaptionBar::SetMargin](#setmargin)|Legt den Abstand zwischen dem Rand das Caption-Element und dem Rand des Steuerelements Beschriftung.|  
|[CMFCCaptionBar::SetText](#settext)|Legt die Beschriftung für die Titelleiste.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Wird aufgerufen, durch das Framework zum Ausfüllen der Titelleiste.|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Wird aufgerufen, durch das Framework den Rahmen der Titelleiste gezeichnet werden soll.|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Wird aufgerufen, durch das Framework Titelleistenschaltfläche Balken gezeichnet werden soll.|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Wird aufgerufen, durch das Framework der Beschriftung Leiste Bild gezeichnet werden soll.|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Wird aufgerufen, durch das Framework den Beschriftungstext für die Balken gezeichnet werden soll.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Die Hintergrundfarbe der Titelleiste.|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Die Farbe des Rahmens Rand der Titelleiste.|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Die Farbe des Textes der Titelleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Titelleiste zu erstellen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen der `CMFCCaptionBar` Objekt. In der Regel würden Sie die Titelleiste einer Rahmenfenster (Klasse) hinzufügen.  
  
2.  Rufen Sie die [CMFCCaptionBar::Create](#create) Methode, um das Caption-Steuerelement zu erstellen, und fügen Sie es auf die `CMFCCaptionBar` Objekt.  
  
3.  Rufen Sie [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), und [CMFCCaptionBar::SetBitmap](#setbitmap)festzulegende die Elemente der Beschriftung.  
  
 Wenn Sie das Button-Element festlegen, müssen Sie die Schaltfläche eine Befehls-ID zuweisen. Wenn der Benutzer die Schaltfläche "", die Beschriftung Leiste Routen klickt der `WM_COMMAND` Nachrichten, die diese ID mit der übergeordneten Rahmenfensters haben.  
  
 Die Titelleiste kann auch im leistenmodus Nachricht, arbeiten, die in der Statusleiste emuliert, die in Microsoft Office 2007-Anwendungen angezeigt wird. Im leistenmodus Nachricht zeigt die Titelleiste eine Bitmap, eine Nachricht und eine Schaltfläche (die in der Regel ein Dialogfeld wird geöffnet.) Sie können eine QuickInfo für die Bitmap zuweisen.  
  
 Rufen Sie zum Aktivieren der Modus "Balken" [CMFCCaptionBar::Create](#create) und legen Sie den vierten Parameter (bIsMessageBarMode) auf `TRUE`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCCaptionBar` Klasse. Im Beispiel wird gezeigt, wie das Caption-Steuerelement zu erstellen, legen Sie eine 3D-Rahmens Rand der Titelleiste, den Abstand zwischen dem Rand der Beschriftung Strich Elemente und den Rand des Steuerelements Beschriftung in Pixel festgelegt, legen Sie die Schaltfläche für die Titelleiste , legen Sie die QuickInfo für die Schaltfläche, legen Sie die textbezeichnung für die Titelleiste, das Bitmap-Bild für die Titelleiste und legen Sie die QuickInfo für das Bild auf der Titelleiste. Dieser Codeausschnitt ist Teil der [MS Office 2007 Demobeispiel für](../../visual-cpp-samples.md).  
  
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
  
##  <a name="create"></a>CMFCCaptionBar::Create  
 Das Caption-Steuerelement erstellt, und fügt es der `CMFCCaptionBar` Objekt.  
  
```  
BOOL Create(
    DWORD dwStyle,  
    CWnd* pParentWnd,  
    UINT uID,  
    int nHeight=-1,  
    BOOL bIsMessageBarMode=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Der logische OR-Kombination der Beschriftung Leiste Stile.  
  
 `pParentWnd`  
 Das übergeordnete Fenster des Steuerelements Beschriftung.  
  
 `uID`  
 Die ID der Beschriftung Statusleisten-Steuerelement.  
  
 `nHeight`  
 Die Höhe in Pixel, der das Caption-Steuerelement. Wenn Sie sie-1 ist, wird die Höhe entsprechend der Höhe der das Symbol ", den Text und die Schaltfläche, die die Beschriftung StatusBar-Steuerelement zeigt berechnet.  
  
 `bIsMessageBarMode`  
 `TRUE`Wenn die Titelleiste in die Nachricht leistenmodus ist. `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Steuerelement Beschriftung erfolgreich erstellt. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CMFCCaptionBar` Objekt in zwei Schritten. Sie rufen Sie zunächst den Konstruktor aus, und rufen Sie dann die `Create` -Methode, die Windows-Steuerelements erstellt und fügt es der `CMFCCaptionBar` Objekt.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore  
 Gibt an, ob es sich bei einem anderen Bereich zwischen der Titelleiste und deren übergeordneten Rahmen dynamisch eingefügt werden kann.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` außer außer Kraft gesetzt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablebutton"></a>CMFCCaptionBar::EnableButton  
 Aktiviert oder deaktiviert die Taste auf der Titelleiste.  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Schaltfläche `FALSE` auf die Schaltfläche deaktiviert.  
  
##  <a name="getalignment"></a>CMFCCaptionBar::GetAlignment  
 Gibt die Ausrichtung des angegebenen Elements zurück.  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `elem`  
 Eine Caption-Element der Leiste für die Ausrichtung abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ausrichtung eines Elements, z. B. eine Schaltfläche, eine Bitmap, Text oder ein Symbol.  
  
### <a name="remarks"></a>Hinweise  
 Die Ausrichtung des Elements kann einer der folgenden Werte sein:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize  
 Der Border Size Rand der Titelleiste wird zurückgegeben.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Rahmens in Pixel.  
  
##  <a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect  
 Ruft das umschließende Rechteck der Schaltflächen auf der Titelleiste ab.  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` Objekt, das die Koordinaten des umschließenden Rechtecks der Schaltflächen auf der Titelleiste enthält.  
  
##  <a name="getmargin"></a>CMFCCaptionBar::GetMargin  
 Gibt den Abstand zwischen dem Rand der Beschriftung menübandleisten-Elementen und den Rand des Steuerelements Beschriftung zurück.  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abstand zwischen dem Rand der Beschriftung menübandleisten-Elementen und den Rand des Steuerelements Beschriftung in Pixel.  
  
##  <a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode  
 Gibt an, ob die Titelleiste in die Nachricht leistenmodus ist.  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Titelleiste in die Nachricht leistenmodus ist. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 In der Nachrichtenmodus Leiste zeigt die Titelleiste ein Bildes mit einer QuickInfo eine Meldungstext und eine Schaltfläche.  
  
##  <a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground  
 Die Hintergrundfarbe der Titelleiste.  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder  
 Die Farbe des Rahmens Rand der Titelleiste.  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText  
 Die Farbe des Textes der Titelleiste.  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground  
 Wird aufgerufen, durch das Framework zum Ausfüllen der Titelleiste.  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext Rand der Titelleiste.  
  
 [in] `rect`  
 Das umschließende Rechteck ausgefüllt.  
  
### <a name="remarks"></a>Hinweise  
 Die `OnDrawBackground` Methode wird aufgerufen, wenn der Hintergrund der Titelleiste wird gefüllt werden soll. Die standardmäßige Implementierung füllt Hintergrund mithilfe der [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) Farbe.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste anzupassen.  
  
##  <a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder  
 Wird aufgerufen, durch das Framework den Rahmen der Titelleiste gezeichnet werden soll.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Einen Gerätekontext, der verwendet wird, um den Rahmen anzuzeigen.  
  
 [in] `rect`  
 Das umschließende Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig haben die Rahmen der Flatfile-Format.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung von Rahmen der Titelleiste anzupassen.  
  
##  <a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton  
 Wird aufgerufen, durch das Framework Titelleistenschaltfläche Balken gezeichnet werden soll.  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext, der verwendet wird, auf die Schaltfläche anzuzeigen.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] `strButton`  
 Die Bezeichnung der Schaltfläche Text.  
  
 [in] `bEnabled`  
 `TRUE`Wenn die Schaltfläche aktiviert ist. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste Schaltfläche anzupassen.  
  
##  <a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage  
 Wird aufgerufen, durch das Framework der Beschriftung Leiste Bild gezeichnet werden soll.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext, der zur Anzeige des Bilds verwendet wird.  
  
 [in] `rect`  
 Gibt das umschließende Rechteck des Bilds an.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung des Bilds anzupassen.  
  
##  <a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText  
 Wird aufgerufen, durch das Framework den Beschriftungstext für die Balken gezeichnet werden soll.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext, der verwendet wird, auf die Schaltfläche anzuzeigen.  
  
 [in] `rect`  
 Das umschließende Rechteck des Texts.  
  
 [in] `strText`  
 Die Textzeichenfolge angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung zeigt den Text mit `CDC::DrawText` und [CMFCCaptionBar::m_clrBarText](#m_clrbartext) Farbe.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung von Text der Titelleiste anzupassen.  
  
##  <a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap  
 Entfernt das Bitmap-Bild aus der Titelleiste an.  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>CMFCCaptionBar::RemoveButton  
 Entfernt die Schaltfläche aus der Titelleiste.  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Layout der Beschriftung menübandleisten-Elementen werden automatisch angepasst.  
  
##  <a name="removeicon"></a>CMFCCaptionBar::RemoveIcon  
 Entfernt das Symbol in der Titelleiste an.  
  
```  
void RemoveIcon();
```  
  
##  <a name="removetext"></a>CMFCCaptionBar::RemoveText  
 Entfernt die Beschriftung in der Titelleiste an.  
  
```  
void RemoveText();
```  
  
##  <a name="setbitmap"></a>CMFCCaptionBar::SetBitmap  
 Legt das Bitmap-Bild für die Titelleiste.  
  
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
 [in] `hBitmap`  
 Das Handle für die Bitmap festgelegt.  
  
 [in] `clrTransparent`  
 Ein RGB-Wert, der die transparente Farbe des Bitmaps angibt.  
  
 [in] `bStretch`  
 Wenn `TRUE`, Bitmap gestreckt wird, wenn es nicht zu dem Bild, das umgebende Rechteck passt. Andernfalls wird die Bitmap nicht gestreckt.  
  
 [in] `bmpAlignment`  
 Die Ausrichtung der Bitmap.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Bitmap für eine Titelleiste festzulegen.  
  
 Die vorherigen Bitmap wird automatisch zerstört. Wenn die Titelleiste ein Symbol angezeigt, da Sie aufgerufen der [CMFCCaptionBar::SetIcon](#seticon) -Methode, die Bitmap wird nicht angezeigt, es sei denn, Sie entfernen Sie das Symbol "durch den Aufruf [CMFCCaptionBar::RemoveIcon](#removeicon).  
  
 Die Bitmap ausgerichtet wird nach den Angaben von der `bmpAlignment` Parameter.  Dieser Parameter kann einen der folgenden `BarElementAlignment`-Werte aufweisen:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize  
 Legt fest, der Border Size Rand der Titelleiste.  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nSize`  
 Die neue Größe des Rahmens Leiste Beschriftung in Pixel.  
  
##  <a name="setbutton"></a>CMFCCaptionBar::SetButton  
 Legt die Schaltfläche für die Titelleiste.  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszLabel`  
 Die Bezeichnung der Schaltfläche-Befehl.  
  
 `uiCmdUI`  
 Die Befehlsschaltfläche-ID.  
  
 `btnAlignmnet`  
 Die Schaltfläche Ausrichtung.  
  
 `bHasDropDownArrow`  
 `TRUE`Wenn die Schaltfläche einen Dropdownpfeil angezeigt `FALSE` andernfalls.  
  
##  <a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed  
 Gibt an, ob die Schaltfläche gedrückt bleibt.  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bPresed`  
 `TRUE`Wenn die Schaltfläche mit der der Zustand "gedrückt" beibehält `FALSE` andernfalls.  
  
##  <a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip  
 Legt die QuickInfo für die Schaltfläche fest.  
  
```  
void SetButtonToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszToolTip`  
 Die QuickInfo-Beschriftung.  
  
 [in] `lpszDescription`  
 Die QuickInfo-Beschreibung.  
  
##  <a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder  
 Legt die Rahmenart der Titelleiste an.  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bFlat`  
 `TRUE`Wenn am Rand der Titelleiste flach ist. `FALSE`Wenn der Rahmen 3D ist.  
  
##  <a name="seticon"></a>CMFCCaptionBar::SetIcon  
 Legt das Symbol für eine Titelleiste an.  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hIcon`  
 Das Handle für das Symbol "festgelegt.  
  
 [in] `iconAlignment`  
 Die Ausrichtung des Symbols.  
  
### <a name="remarks"></a>Hinweise  
 Titelleisten können Symbolen oder Bitmaps anzeigen. Finden Sie unter [CMFCCaptionBar::SetBitmap](#setbitmap) um herauszufinden, wie eine Bitmap angezeigt. Wenn Sie ein Symbol und eine Bitmap festlegen, wird das Symbol immer angezeigt. Rufen Sie [CMFCCaptionBar::RemoveIcon](#removeicon) So entfernen Sie ein Symbol in der Titelleiste.  
  
 Das Symbol wird entsprechend dem ausgerichtet der `iconAlignment` Parameter. Es kann eine der folgenden `BarElementAlignment` Werte:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip  
 Legt die QuickInfo für das Bild in der Titelleiste fest.  
  
```  
void SetImageToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszToolTip`  
 Der Text der QuickInfo.  
  
 [in] `lpszDescription`  
 Die QuickInfo-Beschreibung.  
  
##  <a name="setmargin"></a>CMFCCaptionBar::SetMargin  
 Legt den Abstand zwischen dem Rand das Caption-Element und dem Rand des Steuerelements Beschriftung.  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nMargin`  
 Der Abstand zwischen dem Rand der Beschriftung menübandleisten-Elementen und den Rand des Steuerelements Beschriftung in Pixel.  
  
##  <a name="settext"></a>CMFCCaptionBar::SetText  
 Legt die Beschriftung für die Titelleiste.  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strText`  
 Die Textzeichenfolge festlegen.  
  
 [in] `textAlignment`  
 Die Ausrichtung des Texts.  
  
### <a name="remarks"></a>Hinweise  
 Die Beschriftung ausgerichtet wird nach den Angaben von der `textAlignment` Parameter. Es kann eine der folgenden `BarElementAlignment` Werte:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
