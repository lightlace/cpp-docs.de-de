---
title: CReBar-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94fc1e0ccad8980e0ed5a1cc0f8c0262502e1398
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371141"
---
# <a name="crebar-class"></a>CReBar-Klasse
Eine Steuerleiste, die Layout-, Persistenz- und Zustandsinformationen für Grundleisten-Steuerelemente bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CReBar : public CControlBar  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CReBar::AddBar](#addbar)|Eine grundleiste hinzugefügt ein Band.|  
|[CReBar::Create](#create)|Erstellt das Grundleistensteuerelement, und fügt es der `CReBar` Objekt.|  
|[CReBar:: GetReBarCtrl](#getrebarctrl)|Ermöglicht den direkten Zugriff auf die zugrunde liegenden Standardsteuerelements.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Grundleisten-Objekt kann eine Vielzahl von untergeordnete Fenster, in der Regel andere Steuerelemente, einschließlich Bearbeitungsfelder, Symbolleisten und Listenfelder enthalten. Ein Grundleisten-Objekt kann über eine angegebene Bitmap zugehöriges untergeordnetes Fenster anzuzeigen. Ihre Anwendung kann automatisch die Größe grundleiste oder des Benutzers kann manuell grundleiste durch Klicken oder ziehen die Ziehpunktleiste.  
  
 ![Beispiel eines grundleistenmenüs](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Grundleisten-Steuerelement  
 Ein Grundleisten-Objekt verhält sich ähnlich wie ein Symbolleistenobjekt. Eine grundleiste mithilfe des Mechanismus klicken und ziehen die Bändern Größe. Einem Grundleisten-Steuerelement kann eine oder mehrere Bänder für jedes Band an, dass eine beliebige Kombination von ziehelements-Leiste, eine Bitmap, einer textbezeichnung und ein untergeordnetes Fenster enthalten. Allerdings darf keine Bänder mehr als ein untergeordnetes Fenster enthalten.  
  
 **CReBar** verwendet die [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Klasse, um seine Implementierung bereitstellen. Sie erreichen das Grundleistensteuerelement über [GetReBarCtrl](#getrebarctrl) Anpassungsoptionen für das Steuerelement nutzen. Weitere Informationen zu Rebar-Steuerelemente, finden Sie unter `CReBarCtrl`. Weitere Informationen zur Verwendung von Rebar-Steuerelemente finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  MFC-Steuerleiste Andocken unterstützt Grundleisten und Grundleisten-Steuerelement-Objekte nicht. Wenn **CRebar::EnableDocking** aufgerufen wird, wird die Anwendung implementiert.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="addbar"></a>  CReBar::AddBar  
 Rufen Sie diese Memberfunktion, um ein Band grundleiste hinzuzufügen.  
  
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
 Ein Zeiger auf ein `CWnd` Objekt, das das untergeordnete Fenster in grundleiste eingefügt werden soll. Das referenzierte Objekt benötigen eine **WS_CHILD**.  
  
 `lpszText`  
 Ein Zeiger auf eine Zeichenfolge, enthält des Texts auf der grundleiste angezeigt werden. **NULL** standardmäßig. Der Text in `lpszText` ist nicht Teil des untergeordneten Fensters; er befindet sich auf die Infoleiste selbst.  
  
 `pbmp`  
 Ein Zeiger auf eine `CBitmap` -Objekt, das Grundleisten-Hintergrund angezeigt werden. **NULL** standardmäßig.  
  
 `dwStyle`  
 Ein `DWORD` , enthält die Formatvorlage, die für die Infoleiste gelten. Finden Sie unter der **fStyle** funktionsbeschreibung in der Win32-Struktur [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) für eine vollständige Liste der Stile Band.  
  
 *clrFore*  
 Ein **COLORREF** Wert, der die Vordergrundfarbe der Infoleiste darstellt.  
  
 *clrBack*  
 Ein **COLORREF** Wert, der die Hintergrundfarbe der Infoleiste darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]  
  
##  <a name="create"></a>  CReBar::Create  
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
 Format des Grundleisten-Steuerelements. Standardmäßig **RBS_BANDBORDERS**, welche zeigt eingrenzen Zeilen ein, um benachbarte Bänder innerhalb der Grundleisten-Steuerelement zu trennen. Finden Sie unter [Grundleisten-Steuerelementtypen für die](http://msdn.microsoft.com/library/windows/desktop/bb774377) in das Windows SDK für eine Liste der Formate.  
  
 `dwStyle`  
 Das Grundleisten-Fensterstile.  
  
 `nID`  
 Die Infoleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CReBar::AddBar](#addbar).  
  
##  <a name="getrebarctrl"></a>  CReBar:: GetReBarCtrl  
 Diese Memberfunktion ermöglicht den direkten Zugriff auf die zugrunde liegenden Standardsteuerelements.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die Funktionalität von der allgemeinen Windows Grundleisten-Steuerelement an der Anpassung von Ihrem Grundleisten nutzen. Beim Aufruf `GetReBarCtrl`, wird ein Verweis-Objekt, das `CReBarCtrl` Objekt, damit die beiden Satz von Memberfunktionen verwendet werden kann.  
  
 Weitere Informationen zur Verwendung von `CReBarCtrl` zum Anpassen Ihrer Grundleisten finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel-MFCIE](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



