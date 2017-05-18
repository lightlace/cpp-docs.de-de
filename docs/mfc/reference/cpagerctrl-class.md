---
title: Klasse CPagerCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
dev_langs:
- C++
helpviewer_keywords:
- CPagerCtrl class
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
caps.latest.revision: 26
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
ms.openlocfilehash: 8b8bf05873239f274a9b1285797c01123fe071f7
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cpagerctrl-class"></a>CPagerCtrl-Klasse
Die Klasse `CPagerCtrl` kapselt das Windows-Pagersteuerelement, in dem der Benutzer einen Bildlauf durchführen kann, um ein Fenster innerhalb eines anderen Fensters in den sichtbaren Bereich zu verschieben, sofern es größer ist als das umgebende Fenster.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Erstellt ein `CPagerCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPagerCtrl::Create](#create)|Erstellt ein Pagersteuerelement mit der angegebenen Formate und fügt ihn der aktuellen `CPagerCtrl` Objekt.|  
|[CPagerCtrl::CreateEx](#createex)|Erstellt ein Pagersteuerelement mit dem angegebenen erweiterten Stile und fügt ihn der aktuellen `CPagerCtrl` Objekt.|  
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Aktiviert oder deaktiviert die Weiterleitung [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) Nachrichten an das Fenster, das in das aktuelle Pagersteuerelement enthalten ist.|  
|[CPagerCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::GetBorder](#getborder)|Ruft die Rahmenstärke des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Ruft die Größe der Schaltfläche des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Ruft den Zustand der angegebenen Schaltfläche in der aktuellen Pagersteuerelement.|  
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle für das aktuelle Pagersteuerelement.|  
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Ruft die Bildlaufposition des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `pressed` Zustand.|  
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `grayed` Zustand.|  
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `hot` Zustand.|  
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `invisible` Zustand.|  
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `normal` Zustand.|  
|[CPagerCtrl::RecalcSize](#recalcsize)|Bewirkt, dass das aktuelle Pagersteuerelement die Größe des Fensters enthaltenen neu berechnet.|  
|[CPagerCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe des aktuellen Pager-Steuerelements fest.|  
|[CPagerCtrl::SetBorder](#setborder)|Legt die Rahmengröße des aktuellen Pager-Steuerelements.|  
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Legt die Größe der Schaltfläche des aktuellen Pager-Steuerelements fest.|  
|[CPagerCtrl::SetChild](#setchild)|Legt den im Fenster für das aktuelle Pagersteuerelement fest.|  
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Legt die Bildlaufposition des aktuellen Pager-Steuerelements fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Pagersteuerelement ist ein Fenster, das ein anderes Fenster enthält, das ist linear und größer als das Fenster, und ermöglicht es Ihnen, den im Fenster ein Bildlauf. Das Pagersteuerelement zeigt zwei Bildlaufschaltflächen, die automatisch aufgehoben, wenn Sie der im Fenster ein Bildlauf durchgeführt wird, die am weitesten Block, und andernfalls wieder angezeigt. Sie können einem Pagersteuerelement erstellen, der entweder horizontal oder vertikal verschiebt.  
  
 Beispielsweise verfügt die Anwendung eine Symbolleiste, die nicht breit genug ist, um alle Elemente anzuzeigen, können Sie die Symbolleiste in einem Pagersteuerelement zuweisen, und Benutzern werden auf die Symbolleiste nach links oder rechts, um Zugriff auf alle Elemente zu blättern. Microsoft Internet Explorer Version 4.0 (commctrl.dll Version 4.71) führt das Pagersteuerelement.  
  
 Die `CPagerCtrl` abgeleitete Klasse wird von der [CWnd](../../mfc/reference/cwnd-class.md) Klasse. Weitere Informationen und einem Pagersteuerelement veranschaulicht, finden Sie unter [Paginierungssteuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="cpagerctrl"></a>CPagerCtrl::CPagerCtrl  
 Erstellt ein `CPagerCtrl`-Objekt.  
  
```  
CPagerCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode, um einem Pagersteuerelement erstellen und Anfügen an die `CPagerCtrl` Objekt.  
  
##  <a name="create"></a>CPagerCtrl::Create  
 Erstellt ein Pagersteuerelement mit der angegebenen Formate und fügt ihn der aktuellen `CPagerCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwStyle`|Eine bitweise Kombination (OR) [Fensterstile](../../mfc/reference/window-styles.md) und [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859) auf das Steuerelement angewendet werden.|  
|[in] `rect`|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements in Clientkoordinaten enthält.|  
|[in] `pParentWnd`|Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist. Dieser Parameter darf nicht `NULL`.|  
|[in] `nID`|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Um ein Pager-Steuerelement zu erstellen, deklarieren einen `CPagerCtrl` Variable, rufen Sie dann die [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode für diese Variable.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird ein Pagersteuerelement erstellt, dann werden die [CPagerCtrl::SetChild](#setchild) Methode, um ein sehr langes Button-Steuerelement das Pagersteuerelement zuordnen. Das Beispiel verwendet dann die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens auf 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="createex"></a>CPagerCtrl::CreateEx  
 Erstellt ein Pagersteuerelement mit dem angegebenen erweiterten Stile und fügt ihn der aktuellen `CPagerCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwExStyle`|Eine bitweise Kombination von erweiterten Stile, die auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter der `dwExStyle` Parameter von der [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Funktion.|  
|[in] `dwStyle`|Eine bitweise Kombination (OR) [Fensterstile](../../mfc/reference/window-styles.md) und [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859) auf das Steuerelement angewendet werden.|  
|[in] `rect`|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements in Clientkoordinaten enthält.|  
|[in] `pParentWnd`|Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist. Dieser Parameter darf nicht `NULL`.|  
|[in] `nID`|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Um ein Pager-Steuerelement zu erstellen, deklarieren einen `CPagerCtrl` Variable, rufen Sie dann die [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode für diese Variable.  
  
##  <a name="forwardmouse"></a>CPagerCtrl::ForwardMouse  
 Aktiviert oder deaktiviert die Weiterleitung [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) Nachrichten an das Fenster, das in das aktuelle Pagersteuerelement enthalten ist.  
  
```  
void ForwardMouse(BOOL bForward);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `bForward`|`true`Mausnachrichten weiterleiten oder `false` nicht Mausnachrichten weiterleiten.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_FORWARDMOUSE](http://msdn.microsoft.com/library/windows/desktop/bb760867) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getborder"></a>CPagerCtrl::GetBorder  
 Ruft die Rahmenstärke des aktuellen Pager-Steuerelements ab.  
  
```  
int GetBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Rahmengröße in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760869) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::GetBorder](#getborder) Methode, um die Breite des Rahmens für das Pagersteuerelement abzurufen.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2&5;](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]  
  
##  <a name="getbkcolor"></a>CPagerCtrl::GetBkColor  
 Ruft die Hintergrundfarbe des aktuellen Pager-Steuerelements ab.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die aktuelle Hintergrundfarbe des Steuerelements Pager enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760868) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::SetBkColor](#setbkcolor) Methode, um die Hintergrundfarbe des Steuerelements Pager auf Rot festgelegt und die [CPagerCtrl::GetBkColor](#getbkcolor) Methode, um sicherzustellen, dass die Änderung vorgenommen wurde.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2&4;](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="getbuttonsize"></a>CPagerCtrl::GetButtonSize  
 Ruft die Größe der Schaltfläche des aktuellen Pager-Steuerelements ab.  
  
```  
int GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Schaltflächengröße in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760870) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Verfügt das Pagersteuerelement der `PGS_HORZ` Stil, die Größe der Schaltfläche bestimmt die Breite der Pagerschaltflächen, und wenn das Pagersteuerelement verfügt die `PGS_VERT` Stil, die Größe der Schaltfläche bestimmt die Höhe der Pagerschaltflächen. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
##  <a name="getbuttonstate"></a>CPagerCtrl::GetButtonState  
 Ruft den Zustand der angegebenen Bildlaufschaltfläche in der aktuellen Pagersteuerelement.  
  
```  
DWORD GetButtonState(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen wird. Wenn die Pager-Steuerelement ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für die Rechte Taste. Wenn das Steuerelement Pagerformat ist `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zustand der Schaltfläche angegeben wird, indem die `iButton` Parameter. The state is either `PGF_INVISIBLE`, `PGF_NORMAL`, `PGF_GRAYED`, `PGF_DEPRESSED`, or `PGF_HOT`. Weitere Informationen finden Sie im Abschnitt Return-Wert, der die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdroptarget"></a>CPagerCtrl::GetDropTarget  
 Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle für das aktuelle Pagersteuerelement.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IDropTarget` Schnittstelle für das aktuelle Pagersteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 `IDropTarget`ist eine der Schnittstellen, um die implementieren Unterstützung von Drag & Drop-Operationen in Ihrer Anwendung.  
  
 Diese Methode sendet die [PGM_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb760872) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Der Aufrufer dieser Methode ist verantwortlich für das Aufrufen der `Release` Mitglied der [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle, wenn die Schnittstelle nicht mehr benötigt wird.  
  
##  <a name="getscrollpos"></a>CPagerCtrl::GetScrollPos  
 Ruft die Bildlaufposition des aktuellen Pager-Steuerelements ab.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Bildlaufposition in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760874) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::GetScrollPos](#getscrollpos) Methode zum Abrufen der aktuellen Position des Pager-Steuerelements. Wenn das Pagersteuerelement nicht bereits auf&0; (null), die am weitesten links stehende Position ein Bildlauf durchgeführt wird im Beispiel wird die [CPagerCtrl::SetScrollPos](#setscrollpos) Methode, um die Bildlaufposition auf&0; (null) festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]  
  
##  <a name="isbuttondepressed"></a>CPagerCtrl::IsButtonDepressed  
 Gibt an, ob die angegebenen Bildlaufschaltfläche der aktuellen Pagersteuerelement im gedrückten Zustand ist.  
  
```  
BOOL IsButtonDepressed(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen wird. Wenn die Pager-Steuerelement ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für die Rechte Taste. Wenn das Steuerelement Pagerformat ist `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche im gedrückten Zustand ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Anschließend wird geprüft, ob der Zustand, der zurückgegeben wird `PGF_DEPRESSED`. Weitere Informationen finden Sie im Abschnitt Return-Wert, der die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="isbuttongrayed"></a>CPagerCtrl::IsButtonGrayed  
 Gibt an, ob die angegebenen Bildlaufschaltfläche der aktuellen Pagersteuerelement grau dargestellt ist.  
  
```  
BOOL IsButtonGrayed(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen wird. Wenn die Pager-Steuerelement ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für die Rechte Taste. Wenn das Steuerelement Pagerformat ist `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche abgeblendet ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Anschließend wird geprüft, ob der Zustand, der zurückgegeben wird `PGF_GRAYED`. Weitere Informationen finden Sie im Abschnitt Return-Wert, der die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="isbuttonhot"></a>CPagerCtrl::IsButtonHot  
 Gibt an, ob die angegebenen Bildlaufschaltfläche der aktuellen Pagersteuerelement im aktiven Zustand ist.  
  
```  
BOOL IsButtonHot(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen wird. Wenn die Pager-Steuerelement ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für die Rechte Taste. Wenn das Steuerelement Pagerformat ist `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche im aktiven Zustand ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Anschließend wird geprüft, ob der Zustand, der zurückgegeben wird `PGF_HOT`. Weitere Informationen finden Sie im Abschnitt Return-Wert, der die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="isbuttoninvisible"></a>CPagerCtrl::IsButtonInvisible  
 Gibt an, ob die angegebenen Bildlaufschaltfläche der aktuellen Pagersteuerelement nicht sichtbar ist.  
  
```  
BOOL IsButtonInvisible(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen wird. Wenn die Pager-Steuerelement ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für die Rechte Taste. Wenn das Steuerelement Pagerformat ist `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche nicht sichtbar ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Windows wird die Schaltfläche in einer bestimmten Richtung unsichtbar bei der im Fenster in der am weitesten Umfang Bildlauf durchgeführt wird, da Sie auf die Schaltfläche Weiter mehr von den im Fenster in der Ansicht erscheinen kann nicht.  
  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Anschließend wird geprüft, ob der Zustand, der zurückgegeben wird `PGF_INVISIBLE`. Weitere Informationen finden Sie im Abschnitt Return-Wert, der die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) Methode, um zu bestimmen, ob das Pagersteuerelement linken und rechten Bildlaufschaltflächen sichtbar sind.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2&6;](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]  
  
##  <a name="isbuttonnormal"></a>CPagerCtrl::IsButtonNormal  
 Gibt an, ob die angegebenen Bildlaufschaltfläche der aktuellen Pagersteuerelement im normalen Zustand ist.  
  
```  
BOOL IsButtonNormal(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen wird. Wenn die Pager-Steuerelement ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für die Rechte Taste. Wenn das Steuerelement Pagerformat ist `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche im normalen Zustand ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Anschließend wird geprüft, ob der Zustand, der zurückgegeben wird `PGF_NORMAL`. Weitere Informationen finden Sie im Abschnitt Return-Wert, der die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="recalcsize"></a>CPagerCtrl::RecalcSize  
 Bewirkt, dass das aktuelle Pagersteuerelement die Größe des Fensters enthaltenen neu berechnet.  
  
```  
void RecalcSize();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_RECALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760876) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Das Pagersteuerelement daher sendet die [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) Benachrichtigung an den bildlauffähigen Dimensionen von den im Fenster zu erhalten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::RecalcSize](#recalcsize) Methode, um das aktuelle Pagersteuerelement seine Größe neu berechnen anzufordern.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2&3;](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird [Nachricht Reflektion](../../mfc/tn062-message-reflection-for-windows-controls.md) ermöglichen das Pagersteuerelement, seine eigene Größe anstatt des Steuerelements übergeordneten Dialogfeld zum Durchführen der Berechnung neu zu berechnen. Im Beispiel wird abgeleitet der `MyPagerCtrl` -Klasse von der [CPagerCtrl Klasse](../../mfc/reference/cpagerctrl-class.md), dann mithilfe einer Zuordnung Nachricht Zuordnen der [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) Benachrichtigung mit der `OnCalcsize` benachrichtigungsbehandlung. In diesem Beispiel legt die benachrichtigungsbehandlung die Breite und Höhe des Steuerelements Pager festen Werten fest.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]  
  
##  <a name="setbkcolor"></a>CPagerCtrl::SetBkColor  
 Legt die Hintergrundfarbe des aktuellen Pager-Steuerelements fest.  
  
```  
COLORREF SetBkColor(COLORREF clrBk);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `clrBk`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die neue Hintergrundfarbe des Steuerelements Pager enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die vorherige Hintergrundfarbe des Steuerelements Pager enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760878) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::SetBkColor](#setbkcolor) Methode, um die Hintergrundfarbe des Steuerelements Pager auf Rot festgelegt und die [CPagerCtrl::GetBkColor](#getbkcolor) Methode, um sicherzustellen, dass die Änderung vorgenommen wurde.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2&4;](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="setborder"></a>CPagerCtrl::SetBorder  
 Legt die Rahmengröße des aktuellen Pager-Steuerelements.  
  
```  
int SetBorder(int iBorder);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iBorder`|Neue Rahmengröße in Pixel gemessen. Wenn die `iBorder` Parameter negativ ist, die Rahmengröße auf NULL festgelegt ist.|  
  
### <a name="return-value"></a>Rückgabewert  
 Vorherige Rahmengröße in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760880) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird ein Pagersteuerelement erstellt, dann werden die [CPagerCtrl::SetChild](#setchild) Methode, um ein sehr langes Button-Steuerelement das Pagersteuerelement zuordnen. Das Beispiel verwendet dann die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens auf 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setbuttonsize"></a>CPagerCtrl::SetButtonSize  
 Legt die Größe der Schaltfläche des aktuellen Pager-Steuerelements fest.  
  
```  
int SetButtonSize(int iButtonSize);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButtonSize`|Die neue Schaltflächengröße in Pixel gemessen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Schaltflächengröße in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760886) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Verfügt das Pagersteuerelement der `PGS_HORZ` Stil, die Größe der Schaltfläche bestimmt die Breite der Pagerschaltflächen, und wenn das Pagersteuerelement verfügt die `PGS_VERT` Stil, die Größe der Schaltfläche bestimmt die Höhe der Pagerschaltflächen. Die Standardgröße der Schaltfläche ist drei Viertel der Breite der Bildlaufleiste, und die minimale Schaltflächengröße beträgt 12 Pixel. Weitere Informationen finden Sie unter [Pager Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird ein Pagersteuerelement erstellt, dann werden die [CPagerCtrl::SetChild](#setchild) Methode, um ein sehr langes Button-Steuerelement das Pagersteuerelement zuordnen. Das Beispiel verwendet dann die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens auf 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setchild"></a>CPagerCtrl::SetChild  
 Legt den im Fenster für das aktuelle Pagersteuerelement fest.  
  
```  
void SetChild(HWND hwndChild);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hwndChild`|Handle für das Fenster enthalten ist.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETCHILD](http://msdn.microsoft.com/library/windows/desktop/bb760884) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Diese Methode ändert nicht das übergeordnete Element des Fensters enthalten. Es weist ein Fensterhandle nur das Pagersteuerelement für den Bildlauf. In den meisten Fällen werden im Fenster ein untergeordnetes Fenster, das Pagersteuerelement.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird ein Pagersteuerelement erstellt, dann werden die [CPagerCtrl::SetChild](#setchild) Methode, um ein sehr langes Button-Steuerelement das Pagersteuerelement zuordnen. Das Beispiel verwendet dann die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens auf 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setscrollpos"></a>CPagerCtrl::SetScrollPos  
 Legt die Bildlaufposition des aktuellen Pager-Steuerelements fest.  
  
```  
void SetScrollPos(int iPos);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iPos`|Die neue Bildlaufposition in Pixel gemessen.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760886) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CPagerCtrl-Klasse](../../mfc/reference/cpagerctrl-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Pager-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760855)




