---
title: CMFCCaptionButton Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs: C++
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 857054bd60e206cc3a563aa5f00b872f67c58d3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton-Klasse
Die `CMFCCaptionButton` Klasse implementiert eine Schaltfläche, die auf der Titelleiste für einen andockbaren Bereich oder ein Minirahmenfenster angezeigt wird. In der Regel erstellt das Framework Beschriftungsschaltflächen automatisch.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="constructors"></a>Konstruktoren  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Erstellt ein CMFCCaptionButton-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Gibt den Befehl durch die Schaltfläche "" dargestellt.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|Gibt die Bild-ID der Schaltfläche zugeordnet.|  
|[CMFCCaptionButton::GetRect](#getrect)|Gibt das Rechteck von der Schaltfläche zurück.|  
|[CMFCCaptionButton::GetSize](#getsize)|Gibt die Breite und Höhe der Schaltfläche.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Gibt an, ob die Höhe der Titelleiste auf Mini Größe festgelegt ist.|  
|[CMFCCaptionButton::Move](#move)|Legt fest, den Schaltfläche zeichnen Speicherort und den Zustand der Fenster anzeigen.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Zeichnet die Titelleistenschaltfläche.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Legt die Mini Größe der Titelleiste angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Leiten Sie können eine Klasse von [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md) und verwenden Sie die geschützte Methode `AddButton`, um einem kurzen Rahmenfenster Beschriftungsschaltflächen hinzuzufügen.  
  
 CPaneFrameWnd.h definiert die Befehls-IDs für zwei Arten von Schaltflächen mit Beschriftung:  
  
- `AFX_CAPTION_BTN_PIN`, woraufhin eine Pin-Schaltfläche andockbare Bereich automatisch im Hintergrund-Modus unterstützt.  
  
- `AFX_CAPTION_BTN_CLOSE`, welche zeigt eine **schließen** -Schaltfläche, wenn der Bereich geschlossen oder ausgeblendet werden kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCCaptionButton` Objekt, und legen Sie den Mini Größe der Titelleiste.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>CMFCCaptionButton::CMFCCaptionButton  
 Erstellt ein `CMFCCaptionButton`-Objekt.  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHit`  
 Der Befehl der Schaltfläche zugeordnet ist.  
  
 [in] `bLeftAlign`  
 Gibt an, ob die Schaltfläche links ausgerichtet ist.  
  
 Die folgende Tabelle enthält die möglichen Werte für die `nHit` Parameter.  
  
|Wert|Befehl|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Schaltfläche "Schließen".|  
|`HTMINBUTTON`|Minimieren Sie-Schaltfläche.|  
|`HTMAXBUTTON`|Maximieren Sie-Schaltfläche.|  
|`AFX_HTLEFTBUTTON`|-Links-Taste.|  
|`AFX_HTRIGHTBUTTON`|Pfeil nach rechts.|  
|`AFX_HTMENU`|Nach-unten-Menü-Taste.|  
|`HTNOWHERE`|Der Standardwert; stellt kein Befehl an.|  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden die Beschriftungsschaltflächen nicht mit einem Befehl verknüpft.  
  
 Beschriftungsschaltflächen werden entweder auf Links oder rechts ausgerichtet.  
  
##  <a name="gethit"></a>CMFCCaptionButton::GetHit  
 Gibt den Befehl durch die Schaltfläche "" dargestellt.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Befehl, der durch die Schaltfläche "" dargestellt wird.  
  
 In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet.  
  
|Wert|Befehl|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Schaltfläche "Schließen".|  
|`HTMINBUTTON`|Minimieren Sie-Schaltfläche.|  
|`HTMAXBUTTON`|Maximieren Sie-Schaltfläche.|  
|`AFX_HTLEFTBUTTON`|-Links-Taste.|  
|`AFX_HTRIGHTBUTTON`|Pfeil nach rechts.|  
|`AFX_HTMENU`|Nach-unten-Menü-Taste.|  
|`HTNOWHERE`|Der Standardwert; stellt kein Befehl an.|  
  
##  <a name="geticonid"></a>CMFCCaptionButton::GetIconID  
 Gibt die Bild-ID der Schaltfläche zugeordnet.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHorz`  
 `TRUE`Bild-IDs für nach links oder rechts-Pfeil; `FALSE` für nach oben oder nach-unten ein Abbild IDs.  
  
 [in] `bMaximized`  
 `TRUE`Abbild-ID für eine maximieren; `FALSE` für eine Minimieren-Abbild-ID  
  
### <a name="return-value"></a>Rückgabewert  
 Die Bild-ID.  
  
### <a name="remarks"></a>Hinweise  
 Die Parameter geben Sie die Image-IDs für Minimieren oder Beschriftungsschaltflächen zu maximieren.  
  
##  <a name="getrect"></a>CMFCCaptionButton::GetRect  
 Gibt das Rechteck von der Schaltfläche zurück.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Rechteck, das die Position der Schaltfläche darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche nicht angezeigt wird, ist die zurückgegebene Größe 0.  
  
##  <a name="getsize"></a>CMFCCaptionButton::GetSize  
 Gibt die Breite und Höhe der Schaltfläche.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die äußeren Dimensionen der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Größe enthält Schaltfläche Rand- und Rahmen.  
  
##  <a name="isminiframebutton"></a>CMFCCaptionButton::IsMiniFrameButton  
 Gibt an, ob die Höhe der Titelleiste auf Mini Größe festgelegt ist.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Beschriftung Mini Größe festgelegt ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="move"></a>CMFCCaptionButton::Move  
 Legt fest, den Schaltfläche zeichnen Speicherort und den Zustand der Fenster anzeigen.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptTo`  
 Der neue Speicherort.  
  
 [in] `bHide`  
 Ob die Schaltfläche anzuzeigen.  
  
##  <a name="ondraw"></a>CMFCCaptionButton::OnDraw  
 Zeichnet die Titelleistenschaltfläche.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für die Schaltfläche.  
  
 [in] `bActive`  
 Ob ein Schaltflächenbild der aktiven gezeichnet werden soll.  
  
 [in] `bHorz`  
 Reserviert für die Verwendung in einer abgeleiteten Klasse.  
  
 [in] `bMaximized`  
 Ob ein Schaltflächenbild maximierten gezeichnet werden soll.  
  
 [in] `bDisabled`  
 Ob eine aktivierte Schaltflächenbild gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die `bMaximized` Parameter wird verwendet, wenn die Schaltfläche eine maximieren ist oder Minimieren-Schaltfläche.  
  
##  <a name="setminiframebutton"></a>CMFCCaptionButton::SetMiniFrameButton  
 Legt die Mini Größe der Titelleiste angezeigt.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`für Mini Höhe der Titelleiste; `FALSE` für die Höhe der Titelleiste Standard.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd-Klasse](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
