---
title: CMFCDropDownFrame Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c7264273f3db1dab1e6cab72333c0629a802e28
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041993"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame-Klasse
Bietet Dropdown-Frame Fensterfunktionalität Dropdownelement Symbolleisten und Dropdown Schaltflächen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|Standardkonstruktor|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCDropDownFrame::Create](#create)|Erstellt ein `CMFCDropDownFrame`-Objekt.|  
|`CMFCDropDownFrame::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Ruft die übergeordnete Menüleiste des Dropdown-Frames ab.|  
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Ruft die übergeordnete im Popupmenü des Dropdown-Frames ab.|  
|`CMFCDropDownFrame::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Positioniert den Dropdown-Frame.|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Legt fest, ob das untergeordnete Dropdown-Symbolleistenfenster automatisch zerstört wird.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse kann nicht direkt aus Ihrem Code verwendet werden.  
  
 Das Framework verwendet diese Klasse Verhalten Frame zum Bereitstellen der `CMFCDropDownToolbar` und `CMFCDropDownToolbarButton` Klassen. Weitere Informationen zu diesen Klassen finden Sie unter [CMFCDropDownToolBar Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) und [CMFCDropDownToolbarButton Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie einen Zeiger zum Abrufen einer `CMFCDropDownFrame` -Objekt aus einer `CFrameWnd` -Klasse, und wie das untergeordnete Element Dropdown-Symbolleiste im Fenster automatisch zerstört werden festgelegt.  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdropdowntoolbar.h  
  
##  <a name="create"></a>  CMFCDropDownFrame::Create  
 Erstellt ein `CMFCDropDownFrame`-Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pWndParent,  
    int x,  
    int y,  
    CMFCDropDownToolBar* pWndOriginToolbar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] *pWndParent*|Das übergeordnete Fenster des Dropdown-Frames.|  
|[in] *x*|Die horizontale Bildschirmkoordinate für die Position des Dropdown-Frames.|  
|[in] *y*|Die vertikale Bildschirmkoordinate für die Position des Dropdown-Frames.|  
|[in] *pWndOriginToolbar*|Die Symbolleiste mit den Dropdown-Schaltflächen, die diese Methode verwendet, um das neue Dropdown-Frameobjekt aufzufüllen.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Dropdown-Frame erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Basis [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) Methode zum Erstellen des Dropdown-Frame-Fensters mit den `WS_POPUP` Stil. Das Dropdown-Rahmenfenster wird an den angegebenen Bildschirmkoordinaten angezeigt. Diese Methode schlägt fehl, wenn die [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) -Methode zurückkehrt `FALSE`.  
  
 Die `CMFCDropDownFrame` Klasse erstellt eine Kopie des bereitgestellten `CMFCDropDownToolBar` Parameter. Diese Methode kopiert die Bilder und Schaltflächenzuständen aus der `pWndOriginToolbar` Parameter an die `m_pWndOriginToolbar` -Datenmember.  
  
##  <a name="getparentmenubar"></a>  CMFCDropDownFrame::GetParentMenuBar  
 Ruft die übergeordnete Menüleiste des Dropdown-Frames ab.  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete Menüleiste des Frames Dropdown- oder `NULL` Frames kein übergeordnetes Element besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Menüleiste übergeordneten Schaltfläche "übergeordnete" ab. Diese Methode gibt `NULL` , wenn der Dropdown-Frame keine Schaltfläche "Parent wurde" oder die Schaltfläche "übergeordnete" keine übergeordnete Menüleiste hat.  
  
##  <a name="getparentpopupmenu"></a>  CMFCDropDownFrame::GetParentPopupMenu  
 Ruft die übergeordnete im Popupmenü des Dropdown-Frames ab.  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete Dropdown-Menü des Frames Dropdownelement oder `NULL` Frames kein übergeordnetes Element besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Schaltfläche "übergeordnete" im übergeordneten Menü ab. Diese Methode gibt `NULL` , wenn der Dropdown-Frame keine Schaltfläche "Parent wurde" oder die Schaltfläche "übergeordnete" verfügt über keine übergeordneten Menü.  
  
##  <a name="recalclayout"></a>  CMFCDropDownFrame::RecalcLayout  
 Positioniert den Dropdown-Frame.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] *bNotify*|Nicht verwendet.|  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn der Dropdown-Frame erstellt wird oder das übergeordnete Fenster geändert wird. Diese Methode berechnet die Position und Größe des Dropdown-Frames mit die Position und Größe des übergeordneten Fensters.  
  
##  <a name="setautodestroy"></a>  CMFCDropDownFrame::SetAutoDestroy  
 Legt fest, ob das untergeordnete Dropdown-Symbolleistenfenster automatisch zerstört wird.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAutoDestroy*  
 `TRUE` Das Fenster zugeordneten Dropdown-Symbolleiste automatisch zerstört; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *bAutoDestroy* ist `TRUE`, und klicken Sie dann die `CMFCDropDownFrame` Destruktor zerstört den zugeordneten Dropdown-Symbolleiste im Fenster. Der Standardwert ist `TRUE`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
