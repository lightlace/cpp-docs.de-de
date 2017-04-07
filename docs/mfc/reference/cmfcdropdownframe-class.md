---
title: Klasse CMFCDropDownFrame | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCDropDownFrame class
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5f045e4a3b580f12e64758737495c32963bea6db
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame-Klasse
Der Funktionsumfang Dropdown-Frame Fenster Dropdown-Symbolleisten und Dropdown Schaltflächen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|`CMFCDropDownFrame::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Verschiebt den Dropdown-Frame.|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Legt fest, ob das untergeordnete Dropdown-Symbolleisten-Fenster automatisch zerstört wird.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse kann nicht direkt aus dem Code verwendet werden.  
  
 Das Framework verwendet diese Klasse Verhalten Frame zum Bereitstellen der `CMFCDropDownToolbar` und `CMFCDropDownToolbarButton` Klassen. Weitere Informationen zu diesen Klassen finden Sie unter [CMFCDropDownToolBar Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) und [CMFCDropDownToolbarButton Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Abrufen von eines Zeigers auf eine `CMFCDropDownFrame` -Objekt aus eine `CFrameWnd` -Klasse, und wie Sie das untergeordnete Element Dropdown-im Symbolleistenfenster automatisch gelöscht werden, festlegen.  
  
 [!code-cpp[NVC_MFC_RibbonApp Nr.&36;](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdropdowntoolbar.h  
  
##  <a name="create"></a>CMFCDropDownFrame::Create  
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
|[in] `pWndParent`|Das übergeordnete Fenster des Dropdown-Frames.|  
|[in] `x`|Die horizontale Bildschirmkoordinate für die Position des Dropdown-Frames.|  
|[in] `y`|Die vertikale Bildschirmkoordinate für die Position des Dropdown-Frames.|  
|[in] `pWndOriginToolbar`|Die Symbolleiste mit den Dropdown-Schaltflächen, die diese Methode verwendet, um das neue Dropdown-Frameobjekt füllen.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Dropdown-Frame erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) Methode zum Erstellen des Dropdown-Frame-Fensters mit den `WS_POPUP` Stil. Das Dropdown-Frame-Fenster wird angezeigt, an den angegebenen Bildschirmkoordinaten. Diese Methode schlägt fehl, wenn die [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) -Methode gibt `FALSE`.  
  
 Die `CMFCDropDownFrame` Klasse erstellt eine Kopie des bereitgestellten `CMFCDropDownToolBar` Parameter. Diese Methode kopiert die Bilder und der Schaltflächenstatus aus der `pWndOriginToolbar` Parameter, um den `m_pWndOriginToolbar` -Datenmember.  
  
##  <a name="getparentmenubar"></a>CMFCDropDownFrame::GetParentMenuBar  
 Ruft die übergeordnete Menüleiste des Dropdown-Frames ab.  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete Menüleiste im Dropdown-Fenster oder `NULL` Frames kein übergeordnetes Element besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die übergeordnete Menüleiste in der übergeordneten Schaltfläche. Diese Methode gibt `NULL` Wenn der Dropdown-Rahmen keine übergeordnete Schaltfläche enthält oder die übergeordnete Schaltfläche keine übergeordnete Menüleiste besitzt.  
  
##  <a name="getparentpopupmenu"></a>CMFCDropDownFrame::GetParentPopupMenu  
 Ruft die übergeordnete im Popupmenü des Dropdown-Frames ab.  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das übergeordnete Dropdown-Menü im Dropdown-Fenster oder `NULL` Frames kein übergeordnetes Element besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft im übergeordneten Menü ab, in der übergeordneten-Schaltfläche. Diese Methode gibt `NULL` Dropdown-Frames verfügt über keine übergeordneten Schaltfläche oder die Schaltfläche "übergeordnete" verfügt über keine übergeordneten Menü.  
  
##  <a name="recalclayout"></a>CMFCDropDownFrame::RecalcLayout  
 Verschiebt den Dropdown-Frame.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `bNotify`|Nicht verwendet.|  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn der Dropdown-Frame erstellt wird, oder wird die Größe des übergeordneten Fensters geändert. Diese Methode berechnet die Position und Größe des Dropdown-Frames, indem Sie die Position und Größe des übergeordneten Fensters.  
  
##  <a name="setautodestroy"></a>CMFCDropDownFrame::SetAutoDestroy  
 Legt fest, ob das untergeordnete Dropdown-Symbolleisten-Fenster automatisch zerstört wird.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAutoDestroy`  
 `TRUE`Das Symbolleistenfenster zugeordneten Dropdown-automatisch zerstört; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bAutoDestroy` ist `TRUE`, und klicken Sie dann die `CMFCDropDownFrame` Destruktor zerstört das Symbolleistenfenster zugeordneten Dropdown-. Der Standardwert ist `TRUE`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

