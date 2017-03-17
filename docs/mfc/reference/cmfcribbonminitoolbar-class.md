---
title: Klasse CMFCRibbonMiniToolBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMiniToolBar class
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7c69880578c0aba88a8463112f4d1e05f6032497
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar-Klasse
Implementiert eine kontextbezogene Popup-Symbolleiste.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Standardkonstruktor|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Überschreibt `CMFCPopupMenu::IsRibbonMiniToolBar`.)|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Legt die Liste der auf der Symbolleiste anzuzeigenden Befehle fest.|  
|[CMFCRibbonMiniToolBar::Show](#show)|Zeigt die Minisymbolleiste an den angegebenen Bildschirmkoordinaten an.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Zeigt die Minisymbolleiste zusammen mit einem Kontextmenü an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Minisymbolleiste wird meist angezeigt, nachdem ein Benutzer ein Objekt in einem Dokument ausgewählt hat. Nachdem der Benutzer einen Textblock in einem Textverarbeitungsprogramm auswählt, zeigt die Anwendung z. B. eine Minisymbolleiste mit Textformatierungsbefehlen an.  
  
 Die Minisymbolleiste wird transparent, wenn der Mauszeiger sich außerhalb des gültigen Bereichs der Minisymbolleiste befindet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>CMFCRibbonMiniToolBar::SetCommands  
 Legt die Liste der auf der Symbolleiste anzuzeigenden Befehle fest.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRibbonBar`  
 Die menübandleiste, die die Minisymbolleiste für die anzuzeigenden Schaltflächen sucht.  
  
 [in] `lstCommands`  
 Die Liste der Befehle, die auf die Minisymbolleiste angezeigt werden. Alle menübandkategorien werden durchsucht, um die zugehörigen Schaltflächen zu suchen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Liste der Befehle in die Minisymbolleiste angezeigt werden sollen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetCommands` Methode der `CMFCRibbonMiniToolBar` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#9;](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>CMFCRibbonMiniToolBar::Show  
 Zeigt die Minisymbolleiste an den angegebenen Bildschirmkoordinaten an.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `x`  
 Gibt die horizontale Position von der Minisymbolleiste in Bildschirmkoordinaten.  
  
 [in] `y`  
 Gibt die vertikale Position von der Minisymbolleiste in Bildschirmkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Minisymbolleiste erfolgreich angezeigt wurde. andernfalls `FALSE`.  
  
##  <a name="showwithcontextmenu"></a>CMFCRibbonMiniToolBar::ShowWithContextMenu  
 Zeigt die Minisymbolleiste zusammen mit einem Kontextmenü an.  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `x`  
 Gibt die horizontale Position des Kontextmenüs in Bildschirmkoordinaten.  
  
 [in] `y`  
 Gibt die vertikale Position des Kontextmenüs in Bildschirmkoordinaten.  
  
 [in] `uiMenuResID`  
 Gibt die Ressourcen-ID des Kontextmenüs angezeigt.  
  
 [in] `pWndOwner`  
 Identifiziert das Fenster, das empfängt Nachrichten aus dem Kontextmenü.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Kontextmenü erfolgreich angezeigt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um eine Minisymbolleiste anzuzeigen, die über ein Kontextmenü verfügt. Das Kontextmenü ist positionierte 15 Pixel unterhalb der Minisymbolleiste.  
  
##  <a name="iscontextmenumode"></a>CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isribbonminitoolbar"></a>CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

