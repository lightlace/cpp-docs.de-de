---
title: CMFCRibbonMiniToolBar Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07b20d43c53fc0f485d33f71805e73f885c1200a
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041749"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar-Klasse
Implementiert eine kontextbezogene Popup-Symbolleiste.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Standardkonstruktor|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Überschreibt `CMFCPopupMenu::IsRibbonMiniToolBar`.)|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Legt die Liste der auf der Symbolleiste anzuzeigenden Befehle fest.|  
|[CMFCRibbonMiniToolBar::Show](#show)|Zeigt die Minisymbolleiste an den angegebenen Bildschirmkoordinaten an.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Zeigt die Minisymbolleiste zusammen mit einem Kontextmenü an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Minisymbolleiste wird meist angezeigt, nachdem ein Benutzer ein Objekt in einem Dokument ausgewählt hat. Nachdem der Benutzer einen Textblock in einem Textverarbeitungsprogramm auswählt, zeigt die Anwendung z. B. eine Minisymbolleiste mit Textformatierungsbefehlen an.  
  
 Die Minisymbolleiste wird transparent, wenn der Mauszeiger sich außerhalb des gültigen Bereichs der Minisymbolleiste befindet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>  CMFCRibbonMiniToolBar::SetCommands  
 Legt die Liste der auf der Symbolleiste anzuzeigenden Befehle fest.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pRibbonBar*  
 Die menübandleiste, die für die anzuzeigenden Schaltflächen die Minisymbolleiste sucht.  
  
 [in] *LstCommands*  
 Die Liste der Befehle, die auf die Minisymbolleiste angezeigt werden. Alle menübandkategorien werden durchsucht, um die zugehörigen Schaltflächen zu suchen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion Festlegen der Liste der Befehle in die Minisymbolleiste angezeigt werden.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetCommands` Methode der `CMFCRibbonMiniToolBar` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007 Demobeispiel für](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>  CMFCRibbonMiniToolBar::Show  
 Zeigt die Minisymbolleiste an den angegebenen Bildschirmkoordinaten an.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *x*  
 Gibt die horizontale Position der Minisymbolleiste in Bildschirmkoordinaten.  
  
 [in] *y*  
 Gibt die vertikale Position der Minisymbolleiste in Bildschirmkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Minisymbolleiste erfolgreich angezeigt wurde. andernfalls `FALSE`.  
  
##  <a name="showwithcontextmenu"></a>  CMFCRibbonMiniToolBar::ShowWithContextMenu  
 Zeigt die Minisymbolleiste zusammen mit einem Kontextmenü an.  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *x*  
 Gibt die horizontale Position des Kontextmenüs in Bildschirmkoordinaten.  
  
 [in] *y*  
 Gibt die vertikale Position des Kontextmenüs in Bildschirmkoordinaten.  
  
 [in] *UiMenuResID*  
 Gibt die Ressourcen-ID des Kontextmenüs angezeigt.  
  
 [in] *pWndOwner*  
 Identifiziert das Fenster, das Nachrichten aus dem Kontextmenü empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn im Kontextmenü den Befehl erfolgreich angezeigt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um eine Minisymbolleiste anzuzeigen, die ein Kontextmenü enthält. Das Kontextmenü ist positionierte 15 Pixel unterhalb der Minisymbolleiste an.  
  
##  <a name="iscontextmenumode"></a>  CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isribbonminitoolbar"></a>  CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
