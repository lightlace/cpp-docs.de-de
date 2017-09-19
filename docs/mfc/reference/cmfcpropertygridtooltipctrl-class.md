---
title: Klasse CMFCPropertyGridToolTipCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCPropertyGridToolTipCtrl class
- CMFCPropertyGridToolTipCtrl class, destructor
- PreTranslateMessage method
- ~CMFCPropertyGridToolTipCtrl destructor
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 24
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
ms.openlocfilehash: e5290706799dcd253205ac74dad72cd7783d19dd
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl-Klasse
Implementiert eine QuickInfo zu steuern, die die [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md) verwendet, um QuickInfos anzuzeigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Gibt die Koordinaten der letzten Position der Tooltip-Steuerelements zurück.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Blendet die QuickInfo-Steuerelement.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Von der Klasse verwendet [CWinApp](../../mfc/reference/cwinapp-class.md) auf fenstermeldungen zu übersetzen, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Legt den Abstand zwischen den QuickInfo-Text und Rahmen des QuickInfo-Fensters fest.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Zeigt das QuickInfo-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 QuickInfos werden angezeigt, wenn der Mauszeiger auf einen Eigenschaftsnamen gezeigt. Die [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) Klasse wird ein QuickInfo angezeigt, sodass er vom Benutzer leicht lesbar ist. Die Position einer QuickInfo wird in der Regel durch die Position des Zeigers bestimmt. Durch die Verwendung dieser Klasse, die QuickInfo wird über den Namen der Eigenschaft angezeigt und ähnelt die eigenschaftenerweiterung natürliche-, damit der Eigenschaftsname vollständig sichtbar ist.  
  
 MFC erstellt dieses Steuerelement automatisch und verwendet es in der [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCPropertyGridToolTipCtrl` -Klasse, und wie das QuickInfo-Steuerelement angezeigt.  
  
 [!code-cpp[NVC_MFC_RibbonApp&23;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertygridtooltipctrl.h  
  
##  <a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 Erstellt ein `CMFCPropertyGridToolTipCtrl`-Objekt.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>CMFCPropertyGridToolTipCtrl::Create  
 Erstellt ein Fenster für das QuickInfo-Steuerelement.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Fenster erfolgreich erstellt wurde. andernfalls "false".  
  
##  <a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Deactivate  
 Deaktiviert, und blendet das QuickInfo-Steuerelement.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird die letzte Position und den Text auf leere Werte, damit zukünftige Aufrufe [CMFCPropertyGridToolTipCtrl::Track](#track) die QuickInfo angezeigt.  
  
##  <a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect  
 Gibt die Koordinaten der letzten Position der Tooltip-Steuerelements zurück.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Enthält die letzte Position des Tooltip-Steuerelements.  
  
##  <a name="hide"></a>CMFCPropertyGridToolTipCtrl::Hide  
 Blendet die QuickInfo-Steuerelement.  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Legt den Abstand zwischen den QuickInfo-Text und Rahmen des QuickInfo-Fensters fest.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTextMargin`  
 Gibt den Abstand zwischen den QuickInfo-Text-Steuerelement und dem Rahmen des QuickInfo-Fenster. Der Standardwert ist 10 Pixel.  
  
##  <a name="track"></a>CMFCPropertyGridToolTipCtrl::Track  
 Zeigt das QuickInfo-Steuerelement.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Gibt die Position und Größe des Tooltip-Steuerelements.  
  
 [in] `strText`  
 Gibt den Text in der QuickInfo angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode zeigt das QuickInfo-Steuerelement an der Position und Größe von `rect`. Wenn die Position, Größe und Text nicht seit dem letzten geändert haben, die diese Methode aufgerufen wurde, hat diese Methode keine Auswirkung.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

