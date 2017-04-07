---
title: CReBar-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- rebar controls, control bar
- CReBar class
- Internet Explorer 4.0 common controls
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: 22
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
ms.openlocfilehash: 38ac4611503bec70ea9f809a4d4f9d4b5133e30e
ms.lasthandoff: 02/24/2017

---
# <a name="crebar-class"></a>CReBar-Klasse
Eine Steuerleiste, die Layout-, Persistenz- und Zustandsinformationen für Grundleisten-Steuerelemente bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CReBar : public CControlBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CReBar::AddBar](#addbar)|Eine Infoleiste hinzugefügt ein Band.|  
|[CReBar::Create](#create)|Erstellt das Grundleistensteuerelement und fügt es der `CReBar` Objekt.|  
|[CReBar:: GetReBarCtrl](#getrebarctrl)|Ermöglicht den direkten Zugriff auf das zugrunde liegende Standardsteuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Grundleisten-Objekt kann eine Vielzahl untergeordneter Fenster, in der Regel andere Steuerelemente, einschließlich Bearbeitungsfelder, Symbolleisten und Listenfelder enthalten. Ein Grundleisten-Objekt kann über eine angegebene Bitmap zugehöriges untergeordnetes Fenster anzuzeigen. Ihre Anwendung kann automatisch die Größe der Infoleiste oder des Benutzers kann manuell Infoleiste durch Klicken oder ziehen die Ziehleiste.  
  
 ![Beispiel eines grundleistenmenüs](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Grundleisten-Steuerelement  
 Ein Grundleisten-Objekt verhält sich ähnlich wie ein Toolbar-Objekt. Eine Infoleiste mithilfe des Mechanismus klicken und ziehen die Bändern Größe ändern. Einem Grundleisten-Steuerelement kann eine oder mehrere Bänder für jedes Band müssen eine beliebige Kombination aus einem Ziehleiste, eine Bitmap, eine Bezeichnung und ein untergeordnetes Fenster enthalten. Bänder dürfen jedoch nicht mehr als ein untergeordnetes Fenster.  
  
 **CReBar** verwendet die [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Klasse, um die Implementierung bereitzustellen. Sie erreichen das Grundleistensteuerelement durch [GetReBarCtrl](#getrebarctrl) des Steuerelements Anpassungsoptionen nutzen. Weitere Informationen zu Grundleisten-Steuerelemente, finden Sie unter `CReBarCtrl`. Weitere Informationen zur Verwendung von Grundleisten-Steuerelemente finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  Infoleiste und Grundleisten-Steuerelement-Objekte unterstützen keine MFC Steuerleiste andocken. Wenn **CRebar::EnableDocking** aufgerufen wird, wird die Anwendung anfordern.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="addbar"></a>CReBar::AddBar  
 Rufen Sie diese Memberfunktion Infoleiste ein Band hinzugefügt.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

 
BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Ein Zeiger auf ein `CWnd` Objekt, das das untergeordnete Fenster in der Infoleiste eingefügt werden soll. Das referenzierte Objekt benötigen eine **WS_CHILD**.  
  
 `lpszText`  
 Ein Zeiger auf eine Zeichenfolge mit dem Text auf der Infoleiste angezeigt werden sollen. **NULL** standardmäßig. Der Text in `lpszText` ist nicht Teil des untergeordneten Fensters; es ist für die Infoleiste selbst.  
  
 `pbmp`  
 Ein Zeiger auf ein `CBitmap` Objekt, das im Hintergrund Infoleiste angezeigt werden. **NULL** standardmäßig.  
  
 `dwStyle`  
 Ein `DWORD` mit dem Stil Infoleiste zuweisen. Finden Sie unter der **fStyle** funktionsbeschreibung in der Win32-Struktur [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) für eine vollständige Liste der Stile von Band.  
  
 *clrFore*  
 Ein **COLORREF** -Wert, der die Vordergrundfarbe der Infoleiste darstellt.  
  
 *clrBack*  
 Ein **COLORREF** -Wert, der die Hintergrundfarbe der Infoleiste darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#1;](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]  
  
##  <a name="create"></a>CReBar::Create  
 Rufen Sie diese Memberfunktion zum Erstellen einer Infoleiste.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Zeiger auf die `CWnd` -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist. Normalerweise Ihr Rahmenfenster.  
  
 `dwCtrlStyle`  
 Format des Grundleisten-Steuerelements. In der Standardeinstellung **RBS_BANDBORDERS**, welche zeigt einschränken Zeilen um benachbarte Bänder im Grundleisten-Steuerelement zu trennen. Finden Sie unter [Grundleisten-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb774377) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste der Formate.  
  
 `dwStyle`  
 Die Infoleiste Fensterstile.  
  
 `nID`  
 Die Infoleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CReBar::AddBar](#addbar).  
  
##  <a name="getrebarctrl"></a>CReBar:: GetReBarCtrl  
 Diese Memberfunktion ermöglicht den direkten Zugriff auf das zugrunde liegende Standardsteuerelement.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die Funktionalität der Infoleiste allgemeinen Windows-Steuerelements bei der Anpassung Ihrer Infoleiste nutzen. Beim Aufruf von `GetReBarCtrl`, es gibt ein Verweisobjekt an die `CReBarCtrl` Objekt, damit Sie beide Sätze von Memberfunktionen verwenden können.  
  
 Weitere Informationen zur Verwendung von `CReBarCtrl` zum Anpassen der Infoleiste finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#2;](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCIE](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




