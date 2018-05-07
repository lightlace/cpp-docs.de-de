---
title: CMFCPropertyGridToolTipCtrl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cddd48c51e1e9b5d206cefa56e2879dfb3ace3b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl-Klasse
Implementiert eine QuickInfo zu steuern, die die [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md) verwendet, um QuickInfos anzuzeigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Erstellt ein `CMFCPropertyGridToolTipCtrl`-Objekt.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Erstellt ein Fenster für das QuickInfo-Steuerelement.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Deaktiviert, und blendet das QuickInfo-Steuerelement.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Gibt die Koordinaten der letzten Position der QuickInfo-Steuerelement zurück.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Blendet das QuickInfo-Steuerelement aus.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Legt den Abstand zwischen der QuickInfo-Text und den Rahmen des QuickInfo-Fenster an.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Zeigt das QuickInfo-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 QuickInfos werden angezeigt, wenn der Zeiger auf einen Eigenschaftsnamen verbleibt. Die [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) Klasse wird ein QuickInfo angezeigt, sodass sie vom Benutzer leicht lesbar ist. In der Regel wird die Position einer QuickInfo durch die Position des Zeigers bestimmt. Durch die Verwendung dieser Klasse die QuickInfo wird angezeigt, über den Namen der Eigenschaft und ähnelt dem natürlichen eigenschaftenerweiterung, damit der Eigenschaftsname vollständig sichtbar ist.  
  
 MFC automatisch dieses Steuerelements erstellt und verwendet ihn in die [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCPropertyGridToolTipCtrl` -Klasse, und wie das QuickInfo-Steuerelement angezeigt.  
  
 [!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertygridtooltipctrl.h  
  
##  <a name="cmfcpropertygridtooltipctrl"></a>  CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 Erstellt ein `CMFCPropertyGridToolTipCtrl`-Objekt.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>  CMFCPropertyGridToolTipCtrl::Create  
 Erstellt ein Fenster für das QuickInfo-Steuerelement.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Fenster erfolgreich erstellt wurde. andernfalls "false".  
  
##  <a name="deactivate"></a>  CMFCPropertyGridToolTipCtrl::Deactivate  
 Deaktiviert, und blendet das QuickInfo-Steuerelement.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die letzte Position und den Text auf leere Werte ein, sodass Aufrufe der Zukunft zu [CMFCPropertyGridToolTipCtrl::Track](#track) der QuickInfo angezeigt.  
  
##  <a name="getlastrect"></a>  CMFCPropertyGridToolTipCtrl::GetLastRect  
 Gibt die Koordinaten der letzten Position der QuickInfo-Steuerelement zurück.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Enthält die letzte Position des QuickInfo-Steuerelements an.  
  
##  <a name="hide"></a>  CMFCPropertyGridToolTipCtrl::Hide  
 Blendet das QuickInfo-Steuerelement aus.  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Legt den Abstand zwischen der QuickInfo-Text und den Rahmen des QuickInfo-Fenster an.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTextMargin`  
 Gibt den Abstand zwischen der QuickInfo-Text-Steuerelement und den Rahmen des QuickInfo-Fenster. Der Standardwert ist 10 Pixel.  
  
##  <a name="track"></a>  CMFCPropertyGridToolTipCtrl::Track  
 Zeigt das QuickInfo-Steuerelement.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Gibt die Position und Größe des QuickInfo-Steuerelements.  
  
 [in] `strText`  
 Gibt den Text, in der QuickInfo angezeigt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode zeigt das QuickInfo-Steuerelement an der Position und Größe von angegebenen `rect`. Wenn die Position, Größe und Text nicht seit der letzten Ausführung geändert haben, wenn, die diese Methode aufgerufen wurde, hat diese Methode keine Auswirkung.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
