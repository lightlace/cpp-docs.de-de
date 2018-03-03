---
title: COleIPFrameWnd Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1833cbbbfb6706cffe73770bcd9b61ff755a645
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd-Klasse
Die Basis für der Fenster zur direkten Bearbeitung der Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Erstellt ein `COleIPFrameWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Vom Framework aufgerufen, wenn ein Element für die direkte Bearbeitung aktiviert ist.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Vom Framework aufgerufen, das Fenster zur direkten Bearbeitung neu zu positionieren.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erstellt und Positionen die Steuerleisten im Dokumentfenster der Steuerelementcontainer-Anwendung. Es behandelt auch Benachrichtigungen, die von einem eingebetteten generierten [COleResizeBar](../../mfc/reference/coleresizebar-class.md) Objekt, wenn der Benutzer die Größe der Fenster zur direkten Bearbeitung ändern.  
  
 Weitere Informationen zur Verwendung von `COleIPFrameWnd`, finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd  
 Erstellt eine `COleIPFrameWnd` -Objekt und initialisiert die direkte Zustandsinformationen, die in eine Struktur des Typs gespeichert wird **OLEINPLACEFRAMEINFO**.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) im Windows SDK.  
  
##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars  
 Das Framework Ruft die `OnCreateControlBars` -Funktion, wenn ein Element für die direkte Bearbeitung aktiviert wird.  
  
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
 Ein Zeiger auf die containeranwendung Rahmenfenster.  
  
 *pWndDoc*  
 Ein Zeiger auf den Container auf Dokumentebene Fenster. Kann **NULL** Wenn der Container eine SDI-Anwendung ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion zum Ausführen von jegliche speziellen Verarbeitung erforderlich, wenn Steuerleisten erstellt werden.  
  
##  <a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame  
 Das Framework Ruft die `RepositionFrame` Memberfunktion gestalten von Steuerleisten, und positionieren das Fenster zur direkten Bearbeitung, damit vollständig sichtbar ist.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPosRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das lokal enthält frame-Fensters aktuellen Positionskoordinaten, in Pixel relativ zum Clientbereich.  
  
 `lpClipRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das lokal enthält frame-Fensters aktuellen Clippingrechteck Koordinaten, in Pixel relativ zum Clientbereich.  
  
### <a name="remarks"></a>Hinweise  
 Layout der Steuerleisten im Containerfenster unterscheidet, die von einem nicht-OLE-Rahmenfenster ausgeführt. Das nicht-OLE-Rahmenfenster berechnet die Positionen von Steuerleisten und andere Objekte aus einem bestimmten Rahmenfenster Größe, wie in einem Aufruf von [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Der Clientbereich ist was bleibt, nachdem Speicherplatz für Schiebeleisten-Steuerelemente und andere Objekte subtrahiert wird. Ein `COleIPFrameWnd` Fenster, positioniert auf der anderen Seite Symbolleisten in Übereinstimmung mit einem bestimmten Client-Bereich. Das heißt, `CFrameWnd::RecalcLayout` "von außen" funktioniert, wohingegen `COleIPFrameWnd::RepositionFrame` funktioniert "von innen nach außen."  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)
