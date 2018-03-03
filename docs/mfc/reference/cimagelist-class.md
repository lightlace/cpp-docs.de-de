---
title: CImageList-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
dev_langs:
- C++
helpviewer_keywords:
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1dae44f60c61222659304bea4ee811999d50280b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cimagelist-class"></a>CImageList-Klasse
Stellt die Funktionalität des allgemeinen Windows-Bildlisten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CImageList : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::CImageList](#cimagelist)|Erstellt ein `CImageList`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::Add](#add)|Fügt ein Bild oder Bilder, die auf einer Bildliste.|  
|[CImageList::Attach](#attach)|Fügt eine Bildliste zu einem `CImageList` Objekt.|  
|[CImageList::BeginDrag](#begindrag)|Beginnt, ein Bild zu ziehen.|  
|[CImageList::Copy](#copy)|Kopiert ein Bild innerhalb einer `CImageList` Objekt.|  
|[CImageList:: Create](#create)|Initialisiert mit einer Bildliste und fügt es einer `CImageList` Objekt.|  
|[CImageList::DeleteImageList](#deleteimagelist)|Löscht eine Bildliste.|  
|[CImageList::DeleteTempMap](#deletetempmap)|Wird aufgerufen, indem Sie die [CWinApp](../../mfc/reference/cwinapp-class.md) -leerlaufzeithandler So löschen Sie temporäre `CImageList` mit erstellte Objekt `FromHandle`.|  
|[CImageList::Detach](#detach)|Trennt ein Listenobjekt Image aus einem `CImageList` -Objekt und gibt ein Handle auf eine Bildliste zurück.|  
|[CImageList::DragEnter](#dragenter)|Sperren von Updates während eines Ziehvorgangs, und zeigt das Ziehbild an einer angegebenen Position.|  
|[CImageList::DragLeave](#dragleave)|Entsperrt das Fenster, und blendet das Ziehbild, damit das Fenster aktualisiert werden kann.|  
|[CImageList::DragMove](#dragmove)|Verschiebt das Bild, das bei einem Drag & Drop-Vorgang gezogen wird.|  
|[CImageList::DragShowNolock](#dragshownolock)|Blendet das Bild ziehen Sie während eines Ziehvorgangs ohne Sperren des Fensters.|  
|[Memberfunktion CImageList:: Draw](#draw)|Zeichnet das Bild, das bei einem Drag & Drop-Vorgang gezogen wird.|  
|[CImageList::DrawEx](#drawex)|Zeichnet ein Bild Listenelement in den angegebenen Gerätekontext. Die Funktion verwendet die angegebene Zeichnungsart und mischt des Abbilds mit der angegebenen Farbe.|  
|[CImageList::DrawIndirect](#drawindirect)|Zeichnet ein Bild aus einer Bildliste.|  
|[CImageList::EndDrag](#enddrag)|Wird einen Ziehvorgang beendet.|  
|[CImageList::ExtractIcon](#extracticon)|Erstellt ein Symbol, das basierend auf dem Bild und die Maske in einer Bildliste.|  
|[CImageList::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste vorhanden. Wenn ein `CImageList`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CImageList`-Objekt erstellt und angefügt.|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste vorhanden. Wenn eine `CImageList` Objekt ist nicht an das Handle angefügt **NULL** zurückgegeben wird.|  
|[CImageList::GetBkColor](#getbkcolor)|Ruft die aktuelle Hintergrundfarbe für eine Bildliste ab.|  
|[CImageList::GetDragImage](#getdragimage)|Ruft die Liste von temporären Bilds, die für das Ziehen verwendet wird.|  
|[CImageList::GetImageCount](#getimagecount)|Ruft die Anzahl von Bildern in einer Bildliste ab.|  
|[CImageList::GetImageInfo](#getimageinfo)|Ruft Informationen zu einem Bild ab.|  
|[CImageList::GetSafeHandle](#getsafehandle)|Ruft ab **M_hImageList**.|  
|[CImageList::Read](#read)|Liest eine Bildliste aus einem Archiv.|  
|[CImageList::Remove](#remove)|Entfernt ein Bild aus einer Bildliste.|  
|[CImageList::Replace](#replace)|Ersetzt ein Bild in einer Bildliste mit einem neuen Image an.|  
|[CImageList::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe für eine Bildliste fest.|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Erstellt ein neues Image der ziehen.|  
|[CImageList::SetImageCount](#setimagecount)|Setzt die Anzahl der Bilder in einer Bildliste zurück.|  
|[CImageList:: SetOverlayImage](#setoverlayimage)|Fügt den nullbasierten Index eines Bilds zur Liste der Bilder als Overlaymasken verwendet werden soll.|  
|[CImageList::Write](#write)|Schreibt eine Bildliste in ein Archiv.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Gibt die `HIMAGELIST` angefügt, um die `CImageList`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|Ein Handle, enthält die Bildliste für dieses Objekt angefügt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Liste"Image" ist eine Auflistung von derselben Größe Bilder, von die jedes auf durch den nullbasierten Index verwiesen werden kann. Bilderliste für das werden verwendet, um große Mengen von Symbolen oder Bitmaps effizient zu verwalten. Alle Bilder in einer Bildliste sind in einer einzelnen, Breiten Bitmap im Gerät Bildschirmformat enthalten. Eine Bildliste kann auch eine monochrome Bitmap enthalten, die zum Zeichnen von Bildern transparent Masken (Symbolart) enthält. Die Microsoft Win32-Anwendung Programmierschnittstelle (API) bietet Liste Image-Funktionen, mit denen Sie zum Zeichnen von Bildern, erstellen und Zerstören von Bildlisten, hinzufügen und Entfernen von Bildern, Ersetzen von Bildern, merge Bilder und Bilder ziehen.  
  
 Dieses Steuerelement (und somit die `CImageList` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Weitere Informationen zur Verwendung von `CImageList`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CImageList](../../mfc/using-cimagelist.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="add"></a>CImageList::Add  
 Rufen Sie diese Funktion, um ein oder mehrere Abbilder oder ein Symbol einer Bildliste hinzuzufügen.  
  
```  
int Add(
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Add(
    CBitmap* pbmImage,  
    COLORREF crMask);  
  
int Add(HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `pbmImage`  
 Zeiger auf die Bitmap, die das Bild oder die Bilder enthält. Die Anzahl von Images wird von der Breite der Bitmap abgeleitet.  
  
 `pbmMask`  
 Zeiger auf die Bitmap, die mit der Maske. Wenn keine Maske mit der Bildliste verwendet wird, wird dieser Parameter ignoriert.  
  
 `crMask`  
 Farbe, die zum Generieren der Maske verwendet werden. Jedes dieser Farbe in der angegebenen Bitmap Pixel auf Schwarz geändert wird, und das entsprechende Bit in der Maske auf einen festgelegt.  
  
 `hIcon`  
 Handle des Symbols, das mithilfe einer Bitmap und eine Maske für das neue Abbild enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierten Index des ersten neuen Bilds, wenn erfolgreich; andernfalls - 1.  
  
### <a name="remarks"></a>Hinweise  
 Sie sind verantwortlich für das Symbol "-Handle freigeben, wenn Sie damit fertig sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>CImageList::Attach  
 Mit dieser Funktion können Sie eine Bildliste zum Anfügen einer `CImageList` Objekt.  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `hImageList`  
 Ein Handle für ein Bildlistenobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anlage erfolgreich war; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>CImageList::BeginDrag  
 Mit dieser Funktion können Sie beginnen, ziehen ein Bild.  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds zu ziehen.  
  
 `ptHotSpot`  
 Die Koordinaten der Drag & Startposition (in der Regel die Cursorposition). Die Koordinaten sind relativ zur oberen linken Ecke des Bilds.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt eine temporäre Bildliste, die für das Ziehen verwendet wird. Das Bild kombiniert das angegebene Bild und die Maske mit dem aktuellen Cursor. Als Antwort auf nachfolgende `WM_MOUSEMOVE` Nachrichten, Sie können das Bild bewegen, indem mithilfe der `DragMove` Memberfunktion. Zum Beenden des Ziehvorgangs wird, können Sie die `EndDrag` Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>CImageList::CImageList  
 Erstellt ein `CImageList`-Objekt.  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>CImageList::Copy  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL Copy(
    int iDst,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);

 
BOOL Copy(
    int iDst,  
    CImageList* pSrc,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);
```  
  
### <a name="parameters"></a>Parameter  
 *iDst*  
 Der nullbasierte Index des Bilds als Ziel des Kopiervorgangs verwendet werden soll.  
  
 `iSrc`  
 Der nullbasierte Index des Bilds als die Quelle des Kopiervorgangs verwendet werden soll.  
  
 `uFlags`  
 Die Bit-Flagwert, der angibt, den Typ des Kopiervorgangs vorgenommen werden. Dieser Parameter kann einen der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`ILCF_MOVE`|Das Bild wird in Abbildindex das Ziel kopiert. Dieser Vorgang führt zu mehreren Instanzen eines bestimmten Images. Standardmäßig ist `ILCF_MOVE` festgelegt.|  
|`ILCF_SWAP`|Die Quell- und Zielschemas Bilder tauschen Positionen in der Bildliste.|  
  
 `pSrc`  
 Ein Zeiger auf eine `CImageList` -Objekt, das das Ziel des Kopiervorgangs ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
##  <a name="create"></a>CImageList:: Create  
 Initialisiert mit einer Bildliste und fügt es einer [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.  
  
```  
BOOL Create(
    int cx,  
    int cy,  
    UINT nFlags,  
    int nInitial,  
    int nGrow);

 
BOOL Create(
    UINT nBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    LPCTSTR lpszBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    CImageList& imagelist1,  
    int nImage1,  
    CImageList& imagelist2,  
    int nImage2,  
    int dx,  
    int dy);  
  
BOOL Create(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Die Dimensionen der einzelnen Bilds in Pixel.  
  
 `cy`  
 Die Dimensionen der einzelnen Bilds in Pixel.  
  
 `nFlags`  
 Gibt den Typ der Bildliste zu erstellen. Dieser Parameter kann eine Kombination der folgenden Werte sein, aber er kann nur eine der enthalten die `ILC_COLOR` Werte.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`ILC_COLOR`|Verwenden Sie das Standardverhalten, wenn keine der anderen `ILC_COLOR`* Flags angegeben ist. In der Regel die Standardeinstellung ist `ILC_COLOR4`; aber für ältere Anzeigetreiber, der Standardwert ist `ILC_COLORDDB`.|  
|`ILC_COLOR4`|Verwenden Sie eine 4-Bit (16) geräteunabhängige Bitmap (DIB) farbabschnitts als Bitmap für die Bildliste.|  
|`ILC_COLOR8`|Verwenden Sie einen 8-Bit-DIB-Abschnitt. Die Farben für die Tabelle sind die gleichen Farben als die Halbtonpalette.|  
|`ILC_COLOR16`|Verwenden Sie eine 16-Bit (32 / 64k Farbe) DIB-Abschnitt.|  
|`ILC_COLOR24`|Verwenden Sie einen 24-Bit-DIB-Abschnitt.|  
|`ILC_COLOR32`|Verwenden Sie einen 32-Bit-DIB-Abschnitt.|  
|`ILC_COLORDDB`|Verwenden Sie eine geräteabhängige Bitmap.|  
|`ILC_MASK`|Verwendet eine Maske. Die Bildliste enthält zwei Bitmaps, von denen eine monochrome Bitmap, die als Maske verwendet wird. Wenn dieser Wert nicht enthalten ist, enthält die Bildliste nur einer einzigen Bitmap. Finden Sie unter [Zeichnen von Bildern aus einer Bildliste](../../mfc/drawing-images-from-an-image-list.md) zusätzliche Informationen zu maskierten Images.|  
  
 `nInitial`  
 Anzahl der Bilder, die zunächst die Bildliste enthält.  
  
 `nGrow`  
 Anzahl der Bilder, die mit denen die Bildliste vergrößert werden kann, wenn das System, um die Größe der Liste, um Platz für neue Images zu machen muss. Dieser Parameter entspricht der Anzahl von neuen Images, die die Größe Bildliste enthalten kann.  
  
 `nBitmapID`  
 Ressourcen-IDs der Bitmap die Bildliste zugeordnet werden soll.  
  
 `crMask`  
 Farbe, die zum Generieren einer Maske verwendet werden. Jedes dieser Farbe in der angegebenen Bitmap Pixel auf Schwarz geändert wird, und das entsprechende Bit in der Maske auf einen festgelegt.  
  
 `lpszBitmapID`  
 Eine Zeichenfolge, die die Ressourcen-IDs der Bilder enthält.  
  
 `imagelist1`  
 Ein Verweis auf ein `CImageList`-Objekt.  
  
 `nImage1`  
 Der Index des ersten vorhandenen Images.  
  
 `imagelist2`  
 Ein Verweis auf ein `CImageList`-Objekt.  
  
 `nImage2`  
 Der Index des zweiten vorhandenen Images.  
  
 `dx`  
 Der Offset der x-Achse des zweiten Bilds in Beziehung zu den ersten Bilds in Pixel.  
  
 `dy`  
 Der Offset der y-Achse des zweiten Bilds in Beziehung zu den ersten Bilds in Pixel.  
  
 `pImageList`  
 Ein Zeiger auf eine `CImageList` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CImageList` in zwei Schritten. Zunächst den Konstruktor aufrufen und dann `Create`, die die Bildliste erstellt, und fügt es der `CImageList` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>CImageList::DeleteImageList  
 Mit dieser Funktion wird zum Löschen einer Bildliste.  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>CImageList::DeleteTempMap  
 Wird aufgerufen, automatisch von der `CWinApp` -leerlaufzeithandler, `DeleteTempMap` löscht temporäre `CImageList` von erstellten Objekte [FromHandle](#fromhandle), jedoch zerstört keine Handles ( `hImageList`) vorübergehend verknüpft sind mit der **ImageList** Objekte.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>CImageList::Detach  
 Mit dieser Funktion können Sie ein Image Listenobjekt aus trennen eine `CImageList` Objekt.  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Bildlistenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt ein Handle für das Image-Liste-Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::Attach](#attach).  
  
##  <a name="dragenter"></a>CImageList::DragEnter  
 Sperren Sie während eines Ziehvorgangs Updates vom angegebenen Fensters `pWndLock` und zeigt das Bild an der Position angegeben `point`.  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndLock`  
 Ein Zeiger auf das Fenster, das Bild besitzt.  
  
 `point`  
 Position, an der zur Anzeige des Bilds ziehen. Koordinaten sind relativ zur oben links im Fenster (nicht den Clientbereich).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Koordinaten sind relativ zur oberen linken Ecke des Fensters, damit Sie beim Angeben der Koordinaten für die Breite der Elemente des Fensters, z. B. die Rahmen, die Titelleiste und die Menüleiste ausgleichen müssen.  
  
 Wenn `pWndLock` ist **NULL**, diese Funktion zeichnet das Bild in den Anzeigekontext Desktopfenster zugeordnet und Koordinaten sind relativ zu der oberen linken Ecke des Bildschirms.  
  
 Diese Funktion sperrt alle anderen Updates, die auf das angegebene Fenster, während des Ziehvorgangs. Wenn Sie während eines Ziehvorgangs, z. B. das Ziel eines Drag-and-Drop-Vorgangs, Hervorhebung Zeichnung durchführen müssen können Sie das gezogene Bild vorübergehend ausblenden, indem die [CImageList::DragLeave](#dragleave) Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::BeginDrag](#begindrag).  
  
##  <a name="dragleave"></a>CImageList::DragLeave  
 Vom angegebenen Fensters entsperrt `pWndLock` und blendet Sie aus der Drag &-Image, ermöglichen das Fenster aktualisiert werden.  
  
```  
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndLock`  
 Ein Zeiger auf das Fenster, das Bild besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::EndDrag](#enddrag).  
  
##  <a name="dragmove"></a>CImageList::DragMove  
 Mit dieser Funktion wird zum Verschieben des Bildes, das bei einem Drag & Drop-Vorgang gezogen wird.  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ziehen Sie neue Position.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, als Antwort auf eine `WM_MOUSEMOVE` Nachricht. Verwenden Sie zum Einleiten eines Ziehvorgangs die `BeginDrag` Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>CImageList::DragShowNolock  
 Blendet das Bild ziehen Sie während eines Ziehvorgangs ohne Sperren des Fensters.  
  
```  
static BOOL PASCAL DragShowNolock(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob der Drag-Bild angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die [CImageList::DragEnter](#dragenter) Funktion sperrt alle Updates für das Fenster während eines Ziehvorgangs ein. Diese Funktion des Fensters allerdings nicht gesperrt.  
  
##  <a name="draw"></a>Memberfunktion CImageList:: Draw  
 Mit dieser Funktion wird zum Zeichnen des Bilds, das bei einem Drag & Drop-Vorgang gezogen wird.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Ziel-Gerätekontext.  
  
 `nImage`  
 Nullbasierte Index des zu zeichnenden Bilds.  
  
 `pt`  
 Ort, an dem in den angegebenen Gerätekontext gezeichnet werden soll.  
  
 `nStyle`  
 Kennzeichen, das die Zeichnungsart angibt. Eine oder mehrere der folgenden Werte sind möglich:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`ILD_BLEND25`, **ILD_FOCUS**|Zeichnet das Bild, das Mischen von 25 Prozent mit der Hervorhebungsfarbe des Systems. Dieser Wert hat keine Auswirkung, wenn die Bildliste eine Maske keinen enthält.|  
|`ILD_BLEND50`, **ILD_SELECTED**, **ILD_BLEND**|Zeichnet das Bild, das Mischen von 50 Prozent mit der Hervorhebungsfarbe des Systems. Dieser Wert hat keine Auswirkung, wenn die Bildliste eine Maske keinen enthält.|  
|**ILD_MASK**|Zeichnet die Maske.|  
|`ILD_NORMAL`|Zeichnet das Bild, das die Hintergrundfarbe für die Bildliste verwenden. Ist die Hintergrundfarbe der `CLR_NONE` Wert, der das Bild gezeichnet wird, transparent mit der Maske.|  
|`ILD_TRANSPARENT`|Zeichnet das Bild transparent die Maske, unabhängig von der die Farbe des Hintergrunds.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList:: SetOverlayImage](#setoverlayimage).  
  
##  <a name="drawex"></a>CImageList::DrawEx  
 Zeichnet ein Bild Listenelement in den angegebenen Gerätekontext.  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    COLORREF clrBk,  
    COLORREF clrFg,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Ziel-Gerätekontext.  
  
 `nImage`  
 Nullbasierte Index des zu zeichnenden Bilds.  
  
 `pt`  
 Ort, an dem in den angegebenen Gerätekontext gezeichnet werden soll.  
  
 `sz`  
 Die Größe des Anteils des Bilds relativ zur linken oberen Ecke des Bilds gezeichnet werden soll. Finden Sie unter `dx` und *dy* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
 *clrBk*  
 Die Hintergrundfarbe des Bilds. Finden Sie unter *RgbBk* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
 *clrFg*  
 Die Vordergrundfarbe des Bilds. Finden Sie unter *RgbFg* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
 `nStyle`  
 Kennzeichen, das die Zeichnungsart angibt. Finden Sie unter *fStyle* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion verwendet die angegebene Zeichnungsart und mischt des Abbilds mit der angegebenen Farbe.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>CImageList::DrawIndirect  
 Rufen Sie diese Memberfunktion, um ein Bild aus einer Bildliste gezeichnet werden soll.  
  
```  
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

 
BOOL DrawIndirect(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    POINT ptOrigin,  
    UINT fStyle = ILD_NORMAL,  
    DWORD dwRop = SRCCOPY,  
    COLORREF rgbBack = CLR_DEFAULT,  
    COLORREF rgbFore = CLR_DEFAULT,  
    DWORD fState = ILS_NORMAL,  
    DWORD Frame = 0,  
    COLORREF crEffect = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>Parameter  
 *pimldp*  
 Ein Zeiger auf ein [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) -Struktur, die Informationen zu den Ziehvorgang enthält.  
  
 `pDC`  
 Ein Zeiger auf den Ziel-Gerätekontext. Sie müssen dies löschen [CDC](../../mfc/reference/cdc-class.md) Objekt, wenn Sie damit fertig sind.  
  
 `nImage`  
 Der nullbasierte Index des Bilds gezeichnet werden.  
  
 `pt`  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, enthält die x- und y-Koordinaten, in dem das Bild gezeichnet wird.  
  
 `sz`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur, der angibt, der Größe des Bilds gezeichnet werden.  
  
 *ptOrigin*  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, enthält die x- und y-Koordinaten der oberen linken Ecke des zeichnen-Vorgangs in Bezug auf das eigentliche Bild angeben. Pixel des Bilds, die auf der linken Seite der X-Koordinate und höher die y-Koordinate sind werden nicht gezeichnet.  
  
 `fStyle`  
 Kennzeichen, das angibt, die Zeichnungsart und optional das Overlaybild. Finden Sie im Abschnitt "Hinweise" Informationen auf dem Bild überlagert. Die MFC-Standardimplementierung `ILD_NORMAL`, zeichnet das Bild, das die Hintergrundfarbe für die Bildliste verwenden. Ist die Hintergrundfarbe der `CLR_NONE` Wert, der das Bild gezeichnet wird, transparent mithilfe einer Maske.  
  
 Andere mögliche Formate sind unter beschrieben die **fStyle** Mitglied der [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) Struktur.  
  
 *dwRop*  
 Wert, der ein Raster Vorgangscode angibt. Diese Codes definieren, wie die Farbdaten für das Quellrechteck mit der Farbdaten für Zielrechtecks Erreichen des endgültige Farbe kombiniert werden. MFC Standardimplementierung **SRCCOPY**, Quellrechtecks direkt an das Zielrechteck kopiert. Dieser Parameter wird ignoriert, wenn die `fStyle` Parameter enthält keinen der **ILD_ROP** Flag.  
  
 Weitere mögliche Werte sind unter beschrieben die **DwRop** Mitglied der [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) Struktur.  
  
 *rgbBack*  
 Die Hintergrundfarbe Bild standardmäßig `CLR_DEFAULT`. Dieser Parameter kann eine anwendungsdefinierte RGB-Wert oder einen der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`CLR_DEFAULT`|Standard-Hintergrundfarbe. Das Bild gezeichnet wird, verwenden die Hintergrundfarbe des Image-Liste.|  
|`CLR_NONE`|Keine Hintergrundfarbe. Das Bild wird transparent gezeichnet.|  
  
 *rgbFore*  
 Bild der Vordergrundfarbe, standardmäßig `CLR_DEFAULT`. Dieser Parameter kann eine anwendungsdefinierte RGB-Wert oder einen der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`CLR_DEFAULT`|Die Standardvordergrundfarbe. Mit der Hervorhebungsfarbe des Systems als die Vordergrundfarbe für das Bild gezeichnet.|  
|`CLR_NONE`|Keine Blend-Farbe. Das Bild wird mit der Farbe des Zielgerätekontexts gemischt.|  
  
 Dieser Parameter wird nur verwendet, wenn `fStyle` enthält die `ILD_BLEND25` oder `ILD_BLEND50` Flag.  
  
 *fState*  
 Kennzeichen, das die Zeichnung Status angibt. Dieser Member kann ein oder mehrere Status-Flags für Image-Liste enthalten.  
  
 *Frame*  
 Wirkt sich auf das Verhalten des saturate und Alphablending Auswirkungen.  
  
 Bei Verwendung mit **ILS_SATURATE**, dieses Element enthält den Wert, der für jede Komponente Farbe die RGB-Dreiergruppe für jedes Pixels in das Symbol "hinzugefügt wird.  
  
 Bei Verwendung mit **ILS_APLHA**, dieses Element enthält den Wert für den alpha-Kanal. Dieser Wert kann zwischen 0 und 255, wobei 0 vollständig transparent, und 255 wird vollständig deckend liegen.  
  
 *crEffect*  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Leuchten und Schattenkopien Auswirkungen verwendete Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn das Abbild erfolgreich gezeichneten andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Win32-Struktur selbst eingeben möchten, verwenden Sie die erste Version. Verwenden Sie die zweite Version, wenn Sie eine oder mehrere der MFC Standardargumente nutzen oder zu vermeiden, verwalten Sie die Struktur von möchten.  
  
 Ein Overlay-Image ist ein Bild, das auf das primäre Bild, das in diese Memberfunktion von angegeben gezeichnet wird die `nImage` Parameter. Zeichnen eine Overlaymaske mithilfe der [zeichnen](#draw) Memberfunktion mit dem einsbasierten Index für die Überlagerung-Maske, die mithilfe von angegeben die [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>CImageList::EndDrag  
 Mit dieser Funktion wird zum Beenden eines Ziehvorgangs ein.  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Einleiten eines Ziehvorgangs die `BeginDrag` Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>CImageList::ExtractIcon  
 Mit dieser Funktion wird zum Erstellen eines Symbols basierend auf ein Abbild und dessen zugehörige Maske in einer Bildliste.  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds.  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für das Symbol "bei Erfolg; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode stützt sich auf das Verhalten der [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) Makro auf das Symbol "erstellen. Finden Sie in der [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) Makro für Weitere Informationen zu Symbol erstellen und bereinigen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>CImageList::FromHandle  
 Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste vorhanden.  
  
```  
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `hImageList`  
 Gibt die Bildliste an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CImageList` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CImageList` ist nicht mit dem Handle und ein temporäres Kennwort bereits verbunden `CImageList` Objekt erstellt und angefügt. Dieser temporäre `CImageList` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner-Ereignisschleife aufweist, zu diesem Zeitpunkt alle temporären Objekte gelöscht werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>CImageList::FromHandlePermanent  
 Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste vorhanden.  
  
```  
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `hImageList`  
 Gibt die Bildliste an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CImageList` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CImageList` Objekt ist nicht an das Handle angefügt **NULL** zurückgegeben wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>CImageList::GetBkColor  
 Mit dieser Funktion wird zum Abrufen der aktuellen Hintergrundfarbe für eine Bildliste.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der RGB-Farbwert des der `CImageList` Hintergrundfarbe-Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::SetBkColor](#setbkcolor).  
  
##  <a name="getdragimage"></a>CImageList::GetDragImage  
 Ruft die Liste von temporären Bilds, die für das Ziehen verwendet wird.  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoint`  
 Adresse der einen [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die das aktuelle empfängt ziehen Position.  
  
 *lpPointHotSpot*  
 Adresse der einen **Punkt** Struktur, den Offset des Bilds ziehen Sie relativ zur Ziehposition empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf den temporären Bilds, die Liste wird verwendet, für das Ziehen; andernfalls **NULL**.  
  
##  <a name="getimagecount"></a>CImageList::GetImageCount  
 Mit dieser Funktion wird zum Abrufen der Anzahl von Bildern in einer Bildliste.  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Images.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::ExtractIcon](#extracticon).  
  
##  <a name="getimageinfo"></a>CImageList::GetImageInfo  
 Mit dieser Funktion wird zum Abrufen von Informationen zu einem Bild.  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds.  
  
 *pImageInfo*  
 Zeiger auf eine [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393) -Struktur, die Informationen zu dem Bild empfängt. Die Informationen in dieser Struktur kann verwendet werden, um die Bitmaps für das Bild direkt zu bearbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `IMAGEINFO` Struktur enthält Informationen über ein Bild in einer Bildliste.  
  
##  <a name="getsafehandle"></a>CImageList::GetSafeHandle  
 Mit dieser Funktion wird zum Abrufen der **M_hImageList** -Datenmember.  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf die angefügten Bildliste; andernfalls **NULL** , wenn kein Objekt zugeordnet ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>CImageList::m_hImageList  
 Ein Handle, der die Bildliste für dieses Objekt angefügt werden soll.  
  
 **HIMAGELIST M_hImageList;**  
  
### <a name="remarks"></a>Hinweise  
 Die **M_hImageList** -Datenmember ist eine öffentliche Variable des Typs `HIMAGELIST`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>CImageList::operator HIMAGELIST  
 Verwenden Sie diesen Operator das angefügte Handle des abzurufenden der `CImageList` Objekt.  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für die Bildliste szenariobeschreibungen der `CImageList` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator wird ein Typumwandlungsoperator, die direkte Verwendung von unterstützt ein `HIMAGELIST` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>CImageList::Read  
 Mit dieser Funktion wird zum Lesen von einer Bildliste aus einem Archiv.  
  
```  
BOOL Read(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parameter  
 `pArchive`  
 Ein Zeiger auf ein `CArchive` Objekt, von dem die Bildliste gelesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>CImageList::Remove  
 Rufen Sie diese Funktion, um ein Bild aus einem Image Listenobjekt entfernen.  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente, die nach `nImage` nun eine Position nach unten verschieben. Z. B. wenn eine Bildliste zwei Elemente enthält, verursacht löschen das erste Element der verbleibenden Element jetzt in der ersten Position. `nImage`= 0 für das Element in der ersten Position.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>CImageList::Replace  
 Rufen Sie diese Funktion, um ein Bild in einer Bildliste mit einem neuen Image zu ersetzen.  
  
```  
BOOL Replace(
    int nImage,  
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Replace(
    int nImage,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds zu ersetzen.  
  
 `pbmImage`  
 Ein Zeiger auf die Bitmap, die das Bild enthält.  
  
 `pbmMask`  
 Ein Zeiger auf die Bitmap, die mit der Maske. Wenn keine Maske mit der Bildliste verwendet wird, wird dieser Parameter ignoriert.  
  
 `hIcon`  
 Ein Handle für das Symbol, das mithilfe einer Bitmap und eine Maske für das neue Abbild enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version zurückgeben **BOOL** ungleich NULL zurückgibt, wenn erfolgreich, andernfalls 0.  
  
 Die Version zurückgeben `int` gibt den nullbasierten Index des Bilds zurück, wenn erfolgreich, andernfalls - 1.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, nach dem Aufruf [SetImageCount](#setimagecount) zum Zuweisen von den neuen gültigen Bilder auf den Platzhalter Indexnummern image.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::SetImageCount](#setimagecount).  
  
##  <a name="setbkcolor"></a>CImageList::SetBkColor  
 Mit dieser Funktion wird zum Festlegen der Hintergrundfarbe für eine Bildliste.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Parameter  
 `cr`  
 Hintergrundfarbe festlegen. Es kann sein `CLR_NONE`. In diesem Fall werden Bilder transparent mit der Maske gezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Hintergrundfarbe, wenn erfolgreich; andernfalls `CLR_NONE`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>CImageList::SetDragCursorImage  
 Erstellt ein neues Image der Drag & durch Kombinieren von der angegebenen Bilds (in der Regel ein Bild eines Mauscursors) mit dem aktuellen Drag-Image an.  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 *nDrag*  
 Der Index des neuen Images mit dem Image ziehen Sie kombiniert werden.  
  
 `ptHotSpot`  
 Die Position des Hotspots in das neue Image.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Da die Funktionen zum Ziehen das neue Image während eines Ziehvorgangs verwenden, sollten Sie verwenden Windows [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) Funktion, um den tatsächlichen Cursor nach dem Aufruf ausblenden `CImageList::SetDragCursorImage`. Andernfalls kann das System angezeigt, haben Sie zwei Mauscursor für die Dauer des Ziehvorgangs.  
  
##  <a name="setimagecount"></a>CImageList::SetImageCount  
 Rufen Sie diese Memberfunktion zum Zurücksetzen der Anzahl von Bildern in einem `CImageList` Objekt.  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>Parameter  
 *uNewCount*  
 Der Wert, der die neue Gesamtzahl von Bildern in der Bildliste angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Memberfunktion zum Erhöhen der Anzahl von Bildern in der Bildliste aufrufen, rufen Sie [ersetzen](#replace) für jede zusätzliche Image gültiger Images den neuen Indizes zuweisen. Bei einem gültigen Bilder Indizes zuweisen werden unvorhersehbare Draw-Vorgänge, die die neuen Images zu erstellen.  
  
 Wenn Sie die Größe einer Bildliste verringern, indem Sie diese Funktion verwenden, werden die abgeschnittene Bilder freigegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>CImageList:: SetOverlayImage  
 Mit dieser Funktion wird zum Hinzufügen von des nullbasierten Indexes eines Bilds zur Liste der Bilder als Overlaymasken verwendet werden soll.  
  
```  
BOOL SetOverlayImage(
    int nImage,  
    int nOverlay);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds, das als eine Overlaymaske verwendet.  
  
 *nOverlay*  
 1 basierende Index der Overlaymaske.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Liste können bis zu vier Indizes hinzugefügt werden.  
  
 Eine Overlaymaske ist ein Bild transparent über ein anderes Bild gezeichnet. Zeichnen eine Overlaymaske auf ein Bild mithilfe der [Memberfunktion CImageList:: Draw](#draw) Memberfunktion mit dem einsbasierten Index für die Überlagerung-Maske, die mithilfe von angegeben die **INDEXTOOVERLAYMASK** Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>CImageList::Write  
 Mit dieser Funktion können Sie ein Bildlistenobjekt in ein Archiv zu schreiben.  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parameter  
 `pArchive`  
 Ein Zeiger auf ein `CArchive` Objekt, in dem die Bildliste gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl-Klasse](../../mfc/reference/ctabctrl-class.md)
