---
title: Klasse von COleIPFrameWnd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd class
- OLE, editing
- OLE, in-place activation
- in-place editing
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 85ce028bb5d72c06a0e228abba1bd08a7f6526cb
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd-Klasse
Die Basis für der Fenster zur direkten Bearbeitung der Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Erstellt ein `COleIPFrameWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Wird vom Framework aufgerufen, wenn ein Element für die direkte Bearbeitung aktiviert wird.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Vom Framework aufgerufen wird, im in-Place-Fenster neu zu positionieren.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erstellt und Positionen Steuerleisten im Dokumentfenster der Container-Anwendung. Es behandelt auch von einem eingebetteten generierte Benachrichtigungen [COleResizeBar](../../mfc/reference/coleresizebar-class.md) Objekt, wenn der Benutzer im in-Place-Fenster ändert.  
  
 Weitere Informationen zur Verwendung von `COleIPFrameWnd`, finden Sie im Artikel [Activation](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd  
 Erstellt eine `COleIPFrameWnd` -Objekt und initialisiert seine direkten Zustandsinformationen, die in einer Struktur des Typs gespeichert wird **OLEINPLACEFRAMEINFO**.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars  
 Das Framework Ruft die `OnCreateControlBars` funktionieren, wenn Sie ein Element für die direkte Bearbeitung aktiviert wird.  
  
```  
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,  
    CWnd* pWndDoc);

 
virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,  
    CFrameWnd* pWndDoc);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndFrame*  
 Ein Zeiger auf den Steuerelementcontainer-Anwendung Rahmenfenster.  
  
 *pWndDoc*  
 Zeiger auf den Container auf Dokumentebene Fenster. Kann **NULL** Wenn der Container eine SDI-Anwendung ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg einen Wert ungleich null; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion zum Ausführen einer besondere Verarbeitung erforderlich, wenn Steuerleisten erstellt werden.  
  
##  <a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame  
 Das Framework Ruft die `RepositionFrame` Memberfunktion Steuerleisten Layout und im in-Place-Fenster neu anordnen, damit alle sichtbar ist.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPosRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das direkt enthält frame-Fensters aktuelle Positionskoordinaten, in Pixel relativ zum Clientbereich.  
  
 `lpClipRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das direkt enthält frame-Fensters aktuelle Auswahlrechteck Koordinaten in Pixel relativ zum Clientbereich.  
  
### <a name="remarks"></a>Hinweise  
 Layout der Steuerleisten im Containerfenster unterscheidet, die von einem nicht-OLE-Rahmenfenster ausgeführt. Das nicht-OLE-Rahmenfenster berechnet die Positionen der Steuerleisten und andere Objekte von einer bestimmten Rahmenfenster, wie bei einem Aufruf von [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Der Clientbereich ist was bleibt, nachdem Speicherplatz für Schiebeleisten-Steuerelemente und andere Objekte subtrahiert wird. Ein `COleIPFrameWnd` , auf der anderen Seite Fensterposition Symbolleisten in Übereinstimmung mit einem bestimmten Client-Bereich. Das heißt, `CFrameWnd::RecalcLayout` "von außen" arbeitet, während die `COleIPFrameWnd::RepositionFrame` funktioniert "von innen nach außen."  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)

