---
title: Klasse CMFCCaptionBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CMFCCaptionBar class
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c9be93449392de9d04e4869db8dcd73e08125c88
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar-Klasse
Ein `CMFCCaptionBar` -Objekt ist eine Steuerleiste, die drei Elemente anzeigen kann: eine Schaltfläche, eine Bezeichnung und eine Bitmap. Es kann jeweils nur ein Element eines Typs angezeigt werden. Sie können jedes Element links, rechts oder in der Mitte des Steuerelements positionieren. Sie können zudem den oberen und unteren Rand der Titelleiste flach oder dreidimensional darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::Create](#create)|Erstellt das Steuerelement Beschriftung und fügt es der `CMFCCaptionBar` Objekt.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Gibt an, ob ein weiterer Bereich dynamisch zwischen der Titelleiste und seiner übergeordneten Frame eingefügt werden kann. (Überschreibt [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|Aktiviert oder deaktiviert die Schaltfläche in der Titelleiste.|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|Gibt die Ausrichtung des angegebenen Elements zurück.|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Gibt die Randgröße der Titelleiste.|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Ruft das umschließende Rechteck der Schaltfläche in der Titelleiste an.|  
|[CMFCCaptionBar::GetMargin](#getmargin)|Gibt den Abstand zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung.|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Gibt an, ob die Titelleiste in der Leiste Nachrichtenmodus.|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Entfernt das Bitmap-Bild von der Titelleiste an.|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|Entfernt die Schaltfläche in der Titelleiste an.|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Entfernt das Symbol in der Titelleiste an.|  
|[CMFCCaptionBar::RemoveText](#removetext)|Entfernt die Beschriftung in der Titelleiste an.|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Legt das Bitmapbild der Titelleiste an.|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Legt die Randgröße der Titelleiste.|  
|[CMFCCaptionBar::SetButton](#setbutton)|Legt die Schaltfläche für die Titelleiste an.|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Gibt an, ob die Schaltfläche gedrückt bleibt.|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Legt die QuickInfo für die Schaltfläche fest.|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Legt die Rahmenart der Titelleiste an.|  
|[CMFCCaptionBar::SetIcon](#seticon)|Wird das Symbol für eine Titelleiste.|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Legt die QuickInfo für das Bild für die Titelleiste an.|  
|[CMFCCaptionBar::SetMargin](#setmargin)|Legt den Abstand zwischen dem Rand das Caption-Element und dem Rand des Steuerelements Beschriftung fest.|  
|[CMFCCaptionBar::SetText](#settext)|Legt die Beschriftung für die Titelleiste an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Vom Framework zum Ausfüllen der Titelleiste aufgerufen.|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Vom Framework aufgerufen wird zum Zeichnen des Rahmens, der Titelleiste.|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Aufgerufen, die Beschriftung Leiste Schaltfläche gezeichnet werden soll.|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Aufgerufen, die Beschriftung Leiste Bild gezeichnet werden soll.|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Aufgerufen, um den Text der Beschriftung zu zeichnen.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Die Hintergrundfarbe der Titelleiste.|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Die Farbe des Rahmens der Titelleiste.|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Die Farbe des Textes der Titelleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Gehen Sie folgendermaßen vor, um eine Titelleiste zu erstellen:  
  
1.  Erstellen der `CMFCCaptionBar` Objekt. In der Regel würden Sie die Titelleiste, einem Rahmenfenster (Klasse) hinzufügen.  
  
2.  Rufen Sie die [CMFCCaptionBar::Create](#create) Methode, um die Beschriftung Statusleisten-Steuerelement erstellen und Anfügen an die `CMFCCaptionBar` Objekt.  
  
3.  Rufen Sie [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), und [CMFCCaptionBar::SetBitmap](#setbitmap) die Elemente der Beschriftung festlegen.  
  
 Wenn Sie das Button-Element festlegen, müssen Sie die Schaltfläche eine Befehls-ID zuweisen. Wenn der Benutzer auf die Schaltfläche, die Beschriftung Leiste Routen klickt der `WM_COMMAND` Nachrichten, die diese ID mit der übergeordneten Rahmenfensters haben.  
  
 Die Titelleiste kann auch im Modus Balken, arbeiten die Statusleiste emuliert, die in Microsoft Office 2007-Anwendung angezeigt wird. Im Modus Balken zeigt die Titelleiste einer Bitmap, eine Nachricht und eine Schaltfläche (die normalerweise ein Dialogfeld wird geöffnet.) Sie können eine QuickInfo für die Bitmap zuweisen.  
  
 Rufen Sie zum Aktivieren der Leiste Nachrichtenmodus [CMFCCaptionBar::Create](#create) und legen Sie den vierten Parameter (bIsMessageBarMode) auf `TRUE`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCCaptionBar` Klasse. Im Beispiel wird veranschaulicht, wie das Caption-Steuerelement erstellen, legen Sie eine 3D-Rahmens der Titelleiste, legen Sie den Abstand zwischen dem Rand der Beschriftung Balken Elemente und dem Rand des Steuerelements Beschriftung in Pixel, legen Sie die Schaltfläche für die Titelleiste, Festlegen der QuickInfo für die Schaltfläche, legen Sie die Beschriftung für die Titelleiste, legen die Bitmap für die Titelleiste , und legen Sie die QuickInfo für das Bild in der Titelleiste. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#1;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo&#2;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcaptionbar.h  
  
##  <a name="create"></a>CMFCCaptionBar::Create  
 Erstellt das Steuerelement Beschriftung und fügt es der `CMFCCaptionBar` Objekt.  
  
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
 Die Höhe der Beschriftung des Steuerelements in Pixel. Wenn sie-1 ist, wird die Höhe berechnet, entsprechend der Höhe der das Symbol, den Text und die Schaltfläche, die Beschriftung Statusleisten-Steuerelement anzeigt.  
  
 `bIsMessageBarMode`  
 `TRUE`Wenn die Titelleiste in der Leiste Nachrichtenmodus ist. `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Steuerelement Beschriftung erfolgreich erstellt wurde; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CMFCCaptionBar` Objekt in zwei Schritten. Zuerst rufen Sie den Konstruktor aus, und rufen dann die `Create` -Methode, die das Windows-Steuerelement erstellt, und fügt es der `CMFCCaptionBar` Objekt.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore  
 Gibt an, ob ein weiterer Bereich dynamisch zwischen der Titelleiste und seiner übergeordneten Frame eingefügt werden kann.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` außer außer Kraft gesetzt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablebutton"></a>CMFCCaptionBar::EnableButton  
 Aktiviert oder deaktiviert die Schaltfläche in der Titelleiste.  
  
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
 Ein Caption-Element der Leiste für die Ausrichtung abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ausrichtung eines Elements, z. B. eine Schaltfläche, eine Bitmap, Text oder ein Symbol.  
  
### <a name="remarks"></a>Hinweise  
 Die Ausrichtung des Elements kann einen der folgenden Werte sein:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize  
 Gibt die Randgröße der Titelleiste.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Rahmens in Pixel.  
  
##  <a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect  
 Ruft das umschließende Rechteck der Schaltfläche in der Titelleiste an.  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das die Koordinaten des umschließenden Rechtecks der Schaltfläche auf der Titelleiste enthält.  
  
##  <a name="getmargin"></a>CMFCCaptionBar::GetMargin  
 Gibt den Abstand zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung.  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abstand zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung in Pixel.  
  
##  <a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode  
 Gibt an, ob die Titelleiste in der Leiste Nachrichtenmodus.  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Titelleiste in der Leiste Nachrichtenmodus ist. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 In der Leiste Nachrichtenmodus zeigt die Titelleiste ein Bild mit einer QuickInfo, einen Nachrichtentext und eine Schaltfläche.  
  
##  <a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground  
 Die Hintergrundfarbe der Titelleiste.  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder  
 Die Farbe des Rahmens der Titelleiste.  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText  
 Die Farbe des Textes der Titelleiste.  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground  
 Vom Framework zum Ausfüllen der Titelleiste aufgerufen.  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der Titelleiste.  
  
 [in] `rect`  
 Das umschließende Rechteck zu füllen.  
  
### <a name="remarks"></a>Hinweise  
 Die `OnDrawBackground` Methode wird aufgerufen, wenn der Hintergrund der Titelleiste gerade ausgefüllt werden. Die standardmäßige Implementierung füllt den Hintergrund mithilfe der [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) Farbe.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste anzupassen.  
  
##  <a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder  
 Vom Framework aufgerufen wird zum Zeichnen des Rahmens, der Titelleiste.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Einen Gerätekontext, der verwendet wird, um die Rahmen anzuzeigen.  
  
 [in] `rect`  
 Das umschließende Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verfügen die Ränder die flache Darstellung.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste Rahmen anpassen.  
  
##  <a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton  
 Aufgerufen, die Beschriftung Leiste Schaltfläche gezeichnet werden soll.  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext, der verwendet wird, um die Schaltfläche anzuzeigen.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] `strButton`  
 Die Beschriftung der Schaltfläche Text.  
  
 [in] `bEnabled`  
 `TRUE`Wenn die Schaltfläche aktiviert ist. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung der Titelleiste Schaltfläche anzupassen.  
  
##  <a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage  
 Aufgerufen, die Beschriftung Leiste Bild gezeichnet werden soll.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext, der verwendet wird, um das Bild anzuzeigen.  
  
 [in] `rect`  
 Gibt das umschließende Rechteck des Bilds an.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung des Bilds anzupassen.  
  
##  <a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText  
 Aufgerufen, um den Text der Beschriftung zu zeichnen.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext, der verwendet wird, um die Schaltfläche anzuzeigen.  
  
 [in] `rect`  
 Das umschließende Rechteck des Texts.  
  
 [in] `strText`  
 Die Textzeichenfolge angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung zeigt den Text mithilfe von `CDC::DrawText` und [CMFCCaptionBar::m_clrBarText](#m_clrbartext) Farbe.  
  
 Überschreiben Sie diese Methode in einer `CMFCCaptionBar` abgeleitete Klasse, um die Darstellung des Texts der Titelleiste anzupassen.  
  
##  <a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap  
 Entfernt das Bitmap-Bild von der Titelleiste an.  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>CMFCCaptionBar::RemoveButton  
 Entfernt die Schaltfläche in der Titelleiste an.  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Layout der Elemente der Beschriftung werden automatisch angepasst.  
  
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
 Legt das Bitmapbild der Titelleiste an.  
  
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
 RGB-Wert, der die transparente Farbe der Bitmap angibt.  
  
 [in] `bStretch`  
 Wenn `TRUE`, die Bitmap gestreckt wird, wenn es nicht auf das Bild, das umschließende Rechteck passt. Andernfalls wird die Bitmap nicht gestreckt.  
  
 [in] `bmpAlignment`  
 Die Ausrichtung der Bitmap.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Bitmap in eine Titelleiste festzulegen.  
  
 Die vorherige Bitmap wird automatisch gelöscht. Wenn die Titelleiste ein Symbol angezeigt, da Sie aufgerufen der [CMFCCaptionBar::SetIcon](#seticon) -Methode, die Bitmap wird nicht angezeigt, wenn Sie das Symbol durch Aufrufen von entfernen [CMFCCaptionBar::RemoveIcon](#removeicon).  
  
 Die Bitmap orientiert sich gemäß der `bmpAlignment` Parameter.  Dieser Parameter kann einen der folgenden `BarElementAlignment`-Werte aufweisen:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize  
 Legt die Randgröße der Titelleiste.  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nSize`  
 Die neue Größe des Rahmens Leiste Beschriftung in Pixel.  
  
##  <a name="setbutton"></a>CMFCCaptionBar::SetButton  
 Legt die Schaltfläche für die Titelleiste an.  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszLabel`  
 Die Beschriftung der Befehlsschaltfläche.  
  
 `uiCmdUI`  
 Die Befehlsschaltfläche-ID.  
  
 `btnAlignmnet`  
 Die Ausrichtung.  
  
 `bHasDropDownArrow`  
 `TRUE`Wenn die Schaltfläche eine Dropdown-Pfeil zeigt `FALSE` andernfalls.  
  
##  <a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed  
 Gibt an, ob die Schaltfläche gedrückt bleibt.  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bPresed`  
 `TRUE`Wenn die Schaltfläche seine gedrückt hält `FALSE` andernfalls.  
  
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
 `TRUE`Wenn der Rand der Titelleiste flach ist. `FALSE`Wenn der Rahmen 3D ist.  
  
##  <a name="seticon"></a>CMFCCaptionBar::SetIcon  
 Wird das Symbol für eine Titelleiste.  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hIcon`  
 Das Handle für das Symbol festlegen.  
  
 [in] `iconAlignment`  
 Die Ausrichtung des Symbols.  
  
### <a name="remarks"></a>Hinweise  
 Titelleisten können Symbolen oder Bitmaps angezeigt. Finden Sie unter [CMFCCaptionBar::SetBitmap](#setbitmap) um herauszufinden, wie Sie eine Bitmap anzeigen. Wenn Sie ein Symbol und eine Bitmap festlegen, wird das Symbol immer angezeigt. Rufen Sie [CMFCCaptionBar::RemoveIcon](#removeicon) ein Symbol in der Titelleiste zu entfernen.  
  
 Das Symbol orientiert sich gemäß der `iconAlignment` Parameter. Es kann eine der folgenden `BarElementAlignment` Werte:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip  
 Legt die QuickInfo für das Bild in der Titelleiste an.  
  
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
 Legt den Abstand zwischen dem Rand das Caption-Element und dem Rand des Steuerelements Beschriftung fest.  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nMargin`  
 Der Abstand zwischen dem Rand der Elemente der Beschriftung und dem Rand des Steuerelements Beschriftung in Pixel.  
  
##  <a name="settext"></a>CMFCCaptionBar::SetText  
 Legt die Beschriftung für die Titelleiste an.  
  
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
 Die Beschriftung ausgerichtet wird gemäß der `textAlignment` Parameter. Es kann eine der folgenden `BarElementAlignment` Werte:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

