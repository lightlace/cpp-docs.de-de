---
title: CDialogEx-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs: C++
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c22e258c8306eab1f55fa94f875dde5b68256c71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdialogex-class"></a>CDialogEx-Klasse
Die `CDialogEx`-Klasse gibt die Hintergrundfarbe und das Hintergrundbild eines Dialogfelds an.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDialogEx : public CDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialogEx::CDialogEx](#cdialogex)|Erstellt ein `CDialogEx`-Objekt.|  
|`CDialogEx::~CDialogEx`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|Legt die Hintergrundfarbe des Dialogfelds fest.|  
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|Legt das Hintergrundbild des Dialogfelds fest.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Verwenden der `CDialogEx`-Klasse müssen Sie Ihre Dialogfeldklasse von der `CDialogEx`-Klasse statt der `CDialog`-Klasse ableiten.  
  
 Dialogfeldbilder werden in einer Ressourcendatei gespeichert. Das Framework löscht automatisch jedes Bild, das aus der Ressourcendatei geladen wird. Um das aktuelle Hintergrundbild programmgesteuert zu löschen, rufen die [CDialogEx::SetBackgroundImage](#setbackgroundimage) -Methode auf, oder Implementieren einer `OnDestroy` -Ereignishandler. Beim Aufrufen der [CDialogEx::SetBackgroundImage](#setbackgroundimage) -Methode übergeben Sie ein `HBITMAP` Parameter als Bild-Handle. Das `CDialogEx`-Objekt übernimmt den Besitz des Bilds und löscht es, wenn das `m_bAutoDestroyBmp` -Flag `TRUE` ist.  
  
 Ein `CDialogEx` Objekt kann es sich um ein übergeordnetes Element einer [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt. Die [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt ruft die `CDialogEx::SetActiveMenu` Methode bei der [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt wird geöffnet. Danach die `CDialogEx` Objekt behandelt alle Menüereignisse, bis die [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt ist geschlossen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdialogex.h  
  
##  <a name="cdialogex"></a>CDialogEx::CDialogEx  
 Erstellt ein `CDialogEx`-Objekt.  
  
```  
CDialogEx(
    UINT nIDTemplate,  
    CWnd* pParent=NULL);

 
CDialogEx(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIDTemplate`  
 Die Ressourcen-ID von einer Dialogfeldvorlage.  
  
 [in] `lpszTemplateName`  
 Der Ressourcenname von einer Dialogfeldvorlage.  
  
 [in] `pParent`  
 Ein Zeiger auf das übergeordnete Fenster. Der Standardwert ist `NULL`.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster. Der Standardwert ist `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setbackgroundcolor"></a>CDialogEx::SetBackgroundColor  
 Legt die Hintergrundfarbe des Dialogfelds fest.  
  
```  
void SetBackgroundColor(
    COLORREF color,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein Wert für den RGB-Farbe.  
  
 [in] `bRepaint`  
 `TRUE`um den Bildschirm sofort zu aktualisieren; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setbackgroundimage"></a>CDialogEx::SetBackgroundImage  
 Legt das Hintergrundbild des Dialogfelds fest.  
  
```  
void SetBackgroundImage(
    HBITMAP hBitmap,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bAutoDestroy=TRUE,  
    BOOL bRepaint=TRUE);

 
BOOL SetBackgroundImage(
    UINT uiBmpResId,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hBitmap`  
 Ein Handle für das Hintergrundbild.  
  
 [in] `uiBmpResId`  
 Die Ressourcen-ID des Hintergrundbilds.  
  
 [in] `location`  
 Eines der `CDialogEx::BackgroundLocation` Werte, die den Speicherort des Bilds angeben. Gültige Werte sind BACKGR_TILE, BACKGR_TOPLEFT BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT und BACKGR_BOTTOMRIGHT. Der Standardwert ist BACKGR_TILE.  
  
 [in] `bAutoDestroy`  
 `TRUE`das Hintergrundbild automatisch zerstört; andernfalls `FALSE`.  
  
 [in] `bRepaint`  
 `TRUE`Das Dialogfeld sofort neu zeichnet; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei der zweiten Methode überladen Syntax `TRUE` , wenn die Methode erfolgreich ausgeführt, andernfalls wird `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Bild, das Sie angeben, ist nicht gestreckt den Innenbereich des Dialogfelds.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager-Klasse](../../mfc/reference/ccontextmenumanager-class.md)
