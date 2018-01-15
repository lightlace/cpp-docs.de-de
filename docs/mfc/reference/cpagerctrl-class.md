---
title: CPagerCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c79fa877023c7a01c4814f61d75a54cb0dd64b51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cpagerctrl-class"></a>CPagerCtrl-Klasse
Die Klasse `CPagerCtrl` kapselt das Windows-Pagersteuerelement, in dem der Benutzer einen Bildlauf durchführen kann, um ein Fenster innerhalb eines anderen Fensters in den sichtbaren Bereich zu verschieben, sofern es größer ist als das umgebende Fenster.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Erstellt ein `CPagerCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPagerCtrl::Create](#create)|Erstellt eine Pagersteuerelement mit der angegebenen Formate und fügt ihn der aktuellen `CPagerCtrl` Objekt.|  
|[CPagerCtrl::CreateEx](#createex)|Erstellt eine Pagersteuerelement mit dem angegebenen erweiterten Stile und fügt ihn der aktuellen `CPagerCtrl` Objekt.|  
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Aktiviert oder deaktiviert die Weiterleitung [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) Nachrichten an das Fenster, das in der aktuellen Pagersteuerelement enthalten ist.|  
|[CPagerCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::GetBorder](#getborder)|Ruft die Rahmengröße des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Ruft die Größe der Schaltfläche des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Ruft den Zustand der angegebenen Schaltfläche in der aktuellen Pagersteuerelement.|  
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle für das aktuelle Pagersteuerelement.|  
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Ruft die Bildlaufposition des aktuellen Pager-Steuerelements ab.|  
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `pressed` Zustand.|  
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `grayed` Zustand.|  
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `hot` Zustand.|  
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `invisible` Zustand.|  
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager-Steuerelements in `normal` Zustand.|  
|[CPagerCtrl::RecalcSize](#recalcsize)|Bewirkt, dass der aktuelle Pagersteuerelement, die Größe des Fensters enthaltenen neu zu berechnen.|  
|[CPagerCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe des aktuellen Pager-Steuerelements fest.|  
|[CPagerCtrl::SetBorder](#setborder)|Legt die Rahmengröße des aktuellen Pager-Steuerelements.|  
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Legt die Größe der Schaltfläche des aktuellen Pager-Steuerelements fest.|  
|[CPagerCtrl::SetChild](#setchild)|Legt den im Fenster für das aktuelle Pagersteuerelement fest.|  
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Legt die Bildlaufposition des aktuellen Pager-Steuerelements fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Pagersteuerelement ist ein Fenster, das ein anderes Fenster enthält ist linear und größer als das Fenster, und ermöglicht es Ihnen, Fenster enthaltenen Bildlauf. Das Pagersteuerelement zeigt zwei Bildlaufschaltflächen, die automatisch aufgehoben, wenn Fenster enthaltenen Bildlauf durchgeführt wird, die am weitesten entfernten Block und erneut angezeigt, andernfalls. Sie können einem Pagersteuerelement erstellen, die horizontal oder vertikal ein Bildlauf durchgeführt.  
  
 Beispielsweise verfügt Ihre Anwendung eine Symbolleiste, die nicht breit genug, um alle Elemente angezeigt wird, können Sie einem Pagersteuerelement die Symbolleiste zuweisen, und Benutzer werden in der Lage, die Symbolleiste, um Links oder rechts den Zugriff auf alle Elemente zu blättern. Microsoft Internet Explorer Version 4.0 (commctrl.dll Version 4.71) führt das Pagersteuerelement.  
  
 Die `CPagerCtrl` abgeleitete Klasse wird von der [CWnd](../../mfc/reference/cwnd-class.md) Klasse. Weitere Informationen und einem Pagersteuerelement veranschaulicht, finden Sie unter [Pager-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Verwenden der [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode zum Erstellen von einem Pagersteuerelement, und fügen Sie es auf die `CPagerCtrl` Objekt.  
  
##  <a name="create"></a>CPagerCtrl::Create  
 Erstellt eine Pagersteuerelement mit der angegebenen Formate und fügt ihn der aktuellen `CPagerCtrl` Objekt.  
  
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
|[in] `dwStyle`|Eine bitweise Kombination (OR) [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859) auf das Steuerelement angewendet werden soll.|  
|[in] `rect`|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements in Clientkoordinaten enthält.|  
|[in] `pParentWnd`|Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt, das das übergeordnete Fenster des Steuerelements darstellt. Dieser Parameter darf nicht sein `NULL`.|  
|[in] `nID`|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Um einem Pagersteuerelement zu erstellen, deklarieren einen `CPagerCtrl` Variable, rufen Sie anschließend die [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode mit dieser Variable.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, um eine sehr lange Button-Steuerelement mit dem Pagersteuerelement zuzuordnen. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="createex"></a>CPagerCtrl::CreateEx  
 Erstellt eine Pagersteuerelement mit dem angegebenen erweiterten Stile und fügt ihn der aktuellen `CPagerCtrl` Objekt.  
  
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
|[in] `dwExStyle`|Eine bitweise Kombination der erweiterten Stile, die auf das Steuerelement angewendet werden soll. Weitere Informationen finden Sie unter der `dwExStyle` Parameter von der [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Funktion.|  
|[in] `dwStyle`|Eine bitweise Kombination (OR) [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859) auf das Steuerelement angewendet werden soll.|  
|[in] `rect`|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements in Clientkoordinaten enthält.|  
|[in] `pParentWnd`|Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt, das das übergeordnete Fenster des Steuerelements darstellt. Dieser Parameter darf nicht sein `NULL`.|  
|[in] `nID`|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Um einem Pagersteuerelement zu erstellen, deklarieren einen `CPagerCtrl` Variable, rufen Sie anschließend die [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode mit dieser Variable.  
  
##  <a name="forwardmouse"></a>CPagerCtrl::ForwardMouse  
 Aktiviert oder deaktiviert die Weiterleitung [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) Nachrichten an das Fenster, das in der aktuellen Pagersteuerelement enthalten ist.  
  
```  
void ForwardMouse(BOOL bForward);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `bForward`|`true`zum Weiterleiten von Nachrichten von Maus, oder `false` keine Maus Nachrichten weiterleiten.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_FORWARDMOUSE](http://msdn.microsoft.com/library/windows/desktop/bb760867) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getborder"></a>CPagerCtrl::GetBorder  
 Ruft die Rahmengröße des aktuellen Pager-Steuerelements ab.  
  
```  
int GetBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Rahmengröße, gemessen in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760869) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::GetBorder](#getborder) Methode, um die Stärke des Rahmens für den des Pagersteuerelements abzurufen.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]  
  
##  <a name="getbkcolor"></a>CPagerCtrl::GetBkColor  
 Ruft die Hintergrundfarbe des aktuellen Pager-Steuerelements ab.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die aktuelle Hintergrundfarbe des Steuerelements Pager enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760868) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::SetBkColor](#setbkcolor) Methode, um die Hintergrundfarbe des Steuerelements Pager sich in Rot, einzurichten und die [CPagerCtrl::GetBkColor](#getbkcolor) Methode, um sicherzustellen, dass die Änderung vorgenommen wurde.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="getbuttonsize"></a>CPagerCtrl::GetButtonSize  
 Ruft die Größe der Schaltfläche des aktuellen Pager-Steuerelements ab.  
  
```  
int GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Schaltflächengröße, gemessen in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760870) Nachricht, die im Windows SDK beschrieben wird.  
  
 Wenn das Pagersteuerelement verfügt der `PGS_HORZ` Stil, die Größe der Schaltfläche bestimmt die Breite der Pagerschaltflächen, und wenn die Pagersteuerelement verfügt der `PGS_VERT` Stil, die Größe der Schaltfläche bestimmt die Höhe der Pagerschaltflächen. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
##  <a name="getbuttonstate"></a>CPagerCtrl::GetButtonState  
 Ruft den Zustand der angegebenen Bildlaufschaltfläche in der aktuellen Pagersteuerelement.  
  
```  
DWORD GetButtonState(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen werden. Wenn das Steuerelement Pagerformat ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für mit der rechten Maustaste. Ist das Format des Steuerelements Pager `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zustand der Schaltfläche gemäß der `iButton` Parameter. Der Status ist entweder `PGF_INVISIBLE`, `PGF_NORMAL`, `PGF_GRAYED`, `PGF_DEPRESSED`, oder `PGF_HOT`. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getdroptarget"></a>CPagerCtrl::GetDropTarget  
 Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle für das aktuelle Pagersteuerelement.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IDropTarget` Schnittstelle für das aktuelle Pagersteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 `IDropTarget`ist eine der Schnittstellen, die Sie, um implementieren Drag & Drop-Operationen in Ihrer Anwendung zu unterstützen.  
  
 Diese Methode sendet die [PGM_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb760872) Nachricht, die im Windows SDK beschrieben wird. Der Aufrufer dieser Methode ist verantwortlich für das Aufrufen der `Release` Mitglied der [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle, wenn die Schnittstelle nicht mehr benötigt wird.  
  
##  <a name="getscrollpos"></a>CPagerCtrl::GetScrollPos  
 Ruft die Bildlaufposition des aktuellen Pager-Steuerelements ab.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Bildlaufposition in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760874) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::GetScrollPos](#getscrollpos) Methode, um die aktuelle Bildlaufposition des Steuerelements Pager abzurufen. Wenn die Pagersteuerelement nicht bereits auf 0 (null), die am weitesten links stehende Position Bildlauf durchgeführt wird im Beispiel wird die [CPagerCtrl::SetScrollPos](#setscrollpos) Methode, um die Bildlaufposition auf 0 (null) festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]  
  
##  <a name="isbuttondepressed"></a>CPagerCtrl::IsButtonDepressed  
 Gibt an, ob der angegebene Bildlaufschaltfläche des aktuellen Pager-Steuerelements im Zustand "gedrückt" ist.  
  
```  
BOOL IsButtonDepressed(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen werden. Wenn das Steuerelement Pagerformat ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für mit der rechten Maustaste. Ist das Format des Steuerelements Pager `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche im Zustand "gedrückt" ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht, die im Windows SDK beschrieben wird. Anschließend wird geprüft, ob der Status, der zurückgegeben wird `PGF_DEPRESSED`. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="isbuttongrayed"></a>CPagerCtrl::IsButtonGrayed  
 Gibt an, ob der angegebene Bildlaufschaltfläche des aktuellen Pager-Steuerelements in Grau Zustand befindet.  
  
```  
BOOL IsButtonGrayed(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen werden. Wenn das Steuerelement Pagerformat ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für mit der rechten Maustaste. Ist das Format des Steuerelements Pager `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche abgeblendet ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht, die im Windows SDK beschrieben wird. Anschließend wird geprüft, ob der Status, der zurückgegeben wird `PGF_GRAYED`. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="isbuttonhot"></a>CPagerCtrl::IsButtonHot  
 Gibt an, ob der angegebene Bildlaufschaltfläche des aktuellen Pager-Steuerelements im aktiven Zustand ist.  
  
```  
BOOL IsButtonHot(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen werden. Wenn das Steuerelement Pagerformat ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für mit der rechten Maustaste. Ist das Format des Steuerelements Pager `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche im aktiven Zustand ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht, die im Windows SDK beschrieben wird. Anschließend wird geprüft, ob der Status, der zurückgegeben wird `PGF_HOT`. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="isbuttoninvisible"></a>CPagerCtrl::IsButtonInvisible  
 Gibt an, ob die angegebenen Bildlaufschaltfläche des aktuellen Steuerelements Pager nicht sichtbar ist.  
  
```  
BOOL IsButtonInvisible(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen werden. Wenn das Steuerelement Pagerformat ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für mit der rechten Maustaste. Ist das Format des Steuerelements Pager `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche nicht sichtbar ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Windows unsichtbar Bildlaufschaltfläche in eine bestimmte Richtung bei der im Fenster auf die am weitesten entfernten Block Bildlauf durchgeführt wird, da Sie auf die Schaltfläche Weiter mehrere Fenster enthaltene Ansicht einbinden kann nicht.  
  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht, die im Windows SDK beschrieben wird. Anschließend wird geprüft, ob der Status, der zurückgegeben wird `PGF_INVISIBLE`. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) Methode, um zu bestimmen, ob das Pagersteuerelement linken und rechten Bildlaufschaltflächen sichtbar sind.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]  
  
##  <a name="isbuttonnormal"></a>CPagerCtrl::IsButtonNormal  
 Gibt an, ob der angegebene Bildlaufschaltfläche des aktuellen Pager-Steuerelements im Zustand "normal" ist.  
  
```  
BOOL IsButtonNormal(int iButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iButton`|Gibt die Schaltfläche für die der Status abgerufen werden. Wenn das Steuerelement Pagerformat ist `PGS_HORZ`, geben Sie `PGB_TOPORLEFT` für die linke Maustaste und `PGB_BOTTOMORRIGHT` für mit der rechten Maustaste. Ist das Format des Steuerelements Pager `PGS_VERT`, geben Sie `PGB_TOPORLEFT` für die oberste Schaltfläche und `PGB_BOTTOMORRIGHT` für die Schaltfläche unten. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die angegebene Schaltfläche im Zustand "normal" ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht, die im Windows SDK beschrieben wird. Anschließend wird geprüft, ob der Status, der zurückgegeben wird `PGF_NORMAL`. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Nachricht.  
  
##  <a name="recalcsize"></a>CPagerCtrl::RecalcSize  
 Bewirkt, dass der aktuelle Pagersteuerelement, die Größe des Fensters enthaltenen neu zu berechnen.  
  
```  
void RecalcSize();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_RECALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760876) Nachricht, die im Windows SDK beschrieben wird. Das Pagersteuerelement daher sendet die [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) Benachrichtigung an die bildlauffähigen Dimensionen von den im Fenster zu erhalten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::RecalcSize](#recalcsize) Methode zum Anfordern der aktuellen Pagersteuerelement, seine Größe neu zu berechnen.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird [Nachricht Reflektion](../../mfc/tn062-message-reflection-for-windows-controls.md) So aktivieren Sie das Pagersteuerelement, seine eigene Größe anstatt des Steuerelements übergeordneten Dialogfeld auf die Berechnung neu zu berechnen. Im Beispiel leitet der `MyPagerCtrl` -Klasse aus der [CPagerCtrl-Klasse](../../mfc/reference/cpagerctrl-class.md), klicken Sie dann zum Zuordnen eine meldungszuordnung verwendet der [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) Benachrichtigung mit der `OnCalcsize` Benachrichtigungshandler. In diesem Beispiel legt die Benachrichtigungshandler die Breite und Höhe des Steuerelements Pager auf feste Werte fest.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]  
  
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
 Diese Methode sendet die [PGM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760878) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [CPagerCtrl::SetBkColor](#setbkcolor) Methode, um die Hintergrundfarbe des Steuerelements Pager sich in Rot, einzurichten und die [CPagerCtrl::GetBkColor](#getbkcolor) Methode, um sicherzustellen, dass die Änderung vorgenommen wurde.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="setborder"></a>CPagerCtrl::SetBorder  
 Legt die Rahmengröße des aktuellen Pager-Steuerelements.  
  
```  
int SetBorder(int iBorder);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iBorder`|Die neue Rahmengröße, gemessen in Pixel. Wenn die `iBorder` Parameter ist ein negativer Wert, der Border Size auf 0 festgelegt ist.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Rahmengröße, gemessen in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760880) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, um eine sehr lange Button-Steuerelement mit dem Pagersteuerelement zuzuordnen. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
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
 Diese Methode sendet die [PGM_SETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760886) Nachricht, die im Windows SDK beschrieben wird.  
  
 Wenn das Pagersteuerelement verfügt der `PGS_HORZ` Stil, die Größe der Schaltfläche bestimmt die Breite der Pagerschaltflächen, und wenn die Pagersteuerelement verfügt der `PGS_VERT` Stil, die Größe der Schaltfläche bestimmt die Höhe der Pagerschaltflächen. Die Schaltfläche Standardgröße liegt bei drei Viertel der Breite der Schiebeleiste, und die minimale Schaltflächengröße beträgt 12 Pixel. Weitere Informationen finden Sie unter [Pager-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, um eine sehr lange Button-Steuerelement mit dem Pagersteuerelement zuzuordnen. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setchild"></a>CPagerCtrl::SetChild  
 Legt den im Fenster für das aktuelle Pagersteuerelement fest.  
  
```  
void SetChild(HWND hwndChild);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hwndChild`|Handle für das Fenster enthalten sein soll.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETCHILD](http://msdn.microsoft.com/library/windows/desktop/bb760884) Nachricht, die im Windows SDK beschrieben wird.  
  
 Diese Methode ändert nicht das übergeordnete Element des enthaltenen Fensters; Es weist nur ein Fensterhandle an das Pagersteuerelement Durchführen eines Bildlaufs. In den meisten Fällen werden die Fenster enthaltenen ein untergeordnetes Fenster den Pagersteuerelement.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, um eine sehr lange Button-Steuerelement mit dem Pagersteuerelement zuzuordnen. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe des Steuerelements Pager auf 20 Pixel festgelegt und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1 Pixel festgelegt.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setscrollpos"></a>CPagerCtrl::SetScrollPos  
 Legt die Bildlaufposition des aktuellen Pager-Steuerelements fest.  
  
```  
void SetScrollPos(int iPos);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iPos`|Die neue Position der Bildlaufleiste, gemessen in Pixel.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PGM_SETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760886) Nachricht, die im Windows SDK beschrieben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [CPagerCtrl-Klasse](../../mfc/reference/cpagerctrl-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Pager-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760855)



