---
title: Klasse CMFCCaptionButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton class
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
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
ms.openlocfilehash: 9d6342f87622c34b671ad5ea443eb78ffd8c3838
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton-Klasse
Die `CMFCCaptionButton` -Klasse implementiert eine Schaltfläche, die auf der Titelleiste für einen andockbaren Bereich oder ein Minirahmenfenster angezeigt wird. In der Regel erstellt das Framework Beschriftungsschaltflächen automatisch.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="constructors"></a>Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Erstellt ein CMFCCaptionButton-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Gibt den Befehl, der durch die Schaltfläche dargestellt.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|Gibt die der Schaltfläche zugeordnete Bild-ID zurück.|  
|[CMFCCaptionButton::GetRect](#getrect)|Gibt das Rechteck von der Schaltfläche zurück.|  
|[CMFCCaptionButton::GetSize](#getsize)|Gibt die Breite und Höhe der Schaltfläche.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Gibt an, ob die Höhe der Titelleiste auf die kleine Größe festgelegt ist.|  
|[CMFCCaptionButton::Move](#move)|Legt das Schaltfläche zeichnen Speicherort und den Fensterzustand anzeigen.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Zeichnet die Titelleistenschaltfläche.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Legt die kleine Größe der Titelleiste angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Leiten Sie können eine Klasse von [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md) und verwenden Sie die geschützte Methode `AddButton`, um ein Mini Rahmenfenster Titelleistenschaltflächen hinzuzufügen.  
  
 CPaneFrameWnd.h definiert die Befehls-IDs für zwei Arten von Schaltflächen mit Beschriftung:  
  
- `AFX_CAPTION_BTN_PIN`, woraufhin eine Pin-Schaltfläche unterstützt die andockbare Bereich automatisch ausgeblendet.  
  
- `AFX_CAPTION_BTN_CLOSE`, welche zeigt eine **schließen** -Schaltfläche, wenn der Bereich geschlossen oder ausgeblendet werden kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCCaptionButton` Objekt, und legen Sie die kleine Größe der Titelleiste angezeigt.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#43;](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Der mit der Schaltfläche verknüpfte Befehl.  
  
 [in] `bLeftAlign`  
 Gibt an, ob die Schaltfläche auf der linken Seite ausgerichtet ist.  
  
 Die folgende Tabelle enthält die möglichen Werte für die `nHit` Parameter.  
  
|Wert|Befehl|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Schaltfläche "Schließen".|  
|`HTMINBUTTON`|Minimieren Sie-Schaltfläche.|  
|`HTMAXBUTTON`|Maximieren Sie-Schaltfläche.|  
|`AFX_HTLEFTBUTTON`|Pfeil nach links.|  
|`AFX_HTRIGHTBUTTON`|Pfeil nach rechts.|  
|`AFX_HTMENU`|Abwärtspfeil Menü.|  
|`HTNOWHERE`|Der Standardwert. stellt keinen Befehl.|  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig sind Titelleistenschaltflächen keinem Befehl zugeordnet.  
  
 Titelleistenschaltflächen werden entweder nach rechts oder links ausgerichtet.  
  
##  <a name="gethit"></a>CMFCCaptionButton::GetHit  
 Gibt den Befehl, der durch die Schaltfläche dargestellt.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Befehl, der durch die Schaltfläche dargestellt.  
  
 In der folgenden Tabelle werden die möglichen Rückgabewerte aufgelistet.  
  
|Wert|Befehl|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Schaltfläche "Schließen".|  
|`HTMINBUTTON`|Minimieren Sie-Schaltfläche.|  
|`HTMAXBUTTON`|Maximieren Sie-Schaltfläche.|  
|`AFX_HTLEFTBUTTON`|Pfeil nach links.|  
|`AFX_HTRIGHTBUTTON`|Pfeil nach rechts.|  
|`AFX_HTMENU`|Abwärtspfeil Menü.|  
|`HTNOWHERE`|Der Standardwert. stellt keinen Befehl.|  
  
##  <a name="geticonid"></a>CMFCCaptionButton::GetIconID  
 Gibt die der Schaltfläche zugeordnete Bild-ID zurück.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHorz`  
 `TRUE`Bild-IDs für nach links oder rechts-Pfeil; `FALSE` für Bild nach oben oder unten IDs.  
  
 [in] `bMaximized`  
 `TRUE`Abbild-ID für eine maximieren; `FALSE` Bild-ID für ein minimieren  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bild-ID.  
  
### <a name="remarks"></a>Hinweise  
 Die Parameter geben Sie die Image-IDs für Minimieren oder maximieren Titelleistenschaltflächen.  
  
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
 Die äußere Dimensionen der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Größe umfasst Schaltfläche Rand- und Rahmen.  
  
##  <a name="isminiframebutton"></a>CMFCCaptionButton::IsMiniFrameButton  
 Gibt an, ob die Höhe der Titelleiste auf die kleine Größe festgelegt ist.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Beschriftung Mini Größe festgelegt ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="move"></a>CMFCCaptionButton::Move  
 Legt das Schaltfläche zeichnen Speicherort und den Fensterzustand anzeigen.  
  
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
 Ein Zeiger auf einen Gerätekontext für die Schaltfläche.  
  
 [in] `bActive`  
 Ob ein Bild der aktiven Schaltfläche gezeichnet werden soll.  
  
 [in] `bHorz`  
 Reserviert für die Verwendung in einer abgeleiteten Klasse.  
  
 [in] `bMaximized`  
 Ob ein Schaltflächenbild maximierten gezeichnet werden soll.  
  
 [in] `bDisabled`  
 Ob eine aktivierte Schaltflächenbild gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die `bMaximized` Parameter verwendet wird, wird die Schaltfläche ein Maximieren oder Minimieren-Schaltfläche.  
  
##  <a name="setminiframebutton"></a>CMFCCaptionButton::SetMiniFrameButton  
 Legt die kleine Größe der Titelleiste angezeigt.  
  
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

