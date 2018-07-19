---
title: CImageList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63e6a7a45fc119309ce99640ab74006ae44a05bf
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339132"
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
|[CImageList::Add](#add)|Fügt ein Bild oder Bilder für eine Bildliste an.|  
|[CImageList::Attach](#attach)|Fügt eine Bildliste für eine `CImageList` Objekt.|  
|[CImageList::BeginDrag](#begindrag)|Beginnt, ein Bild zu ziehen.|  
|[CImageList::Copy](#copy)|Kopiert ein Bild innerhalb einer `CImageList` Objekt.|  
|[CImageList:: Create](#create)|Initialisiert eine Bildliste an, und fügt sie an einer `CImageList` Objekt.|  
|[CImageList::DeleteImageList](#deleteimagelist)|Löscht eine Bildliste.|  
|[CImageList::DeleteTempMap](#deletetempmap)|Wird aufgerufen, indem die [CWinApp](../../mfc/reference/cwinapp-class.md) -leerlaufzeithandler So löschen Sie temporäre `CImageList` von erstelltes Objekt `FromHandle`.|  
|[CImageList::Detach](#detach)|Trennt ein Image List-Objekt aus einem `CImageList` Objekt und gibt ein Handle einer Bildliste zurück.|  
|[CImageList::DragEnter](#dragenter)|Sperren von Updates während eines Ziehvorgangs, und zeigt das Ziehbild an einer angegebenen Position.|  
|[CImageList::DragLeave](#dragleave)|Entsperrt das Fenster, und blendet Sie aus dem Ziehbild, damit das Fenster aktualisiert werden kann.|  
|[CImageList::DragMove](#dragmove)|Verschiebt das Bild, das bei einem Drag & Drop-Vorgang gezogen wird.|  
|[CImageList::DragShowNolock](#dragshownolock)|Anzeigen oder Ausblenden der bilddarstellung während eines Ziehvorgangs, ohne Sperren das Fenster.|  
|[Memberfunktion CImageList:: Draw](#draw)|Zeichnet das Bild, das bei einem Drag & Drop-Vorgang gezogen wird.|  
|[CImageList::DrawEx](#drawex)|Zeichnet ein Bild Listenelement in den angegebenen Gerätekontext. Die Funktion verwendet die angegebene Zeichnungsart und wie das Image mit der angegebenen Farbe.|  
|[CImageList::DrawIndirect](#drawindirect)|Zeichnet ein Bild aus einer Bildliste.|  
|[CImageList::EndDrag](#enddrag)|Beendet einen Ziehvorgang.|  
|[CImageList::ExtractIcon](#extracticon)|Erstellt ein Symbol, das basierend auf einem Bild und der Maske in einer Bildliste.|  
|[CImageList::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CImageList` Objekt, wenn ein Handle einer Bildliste angegeben. Wenn ein `CImageList`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CImageList`-Objekt erstellt und angefügt.|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Gibt einen Zeiger auf eine `CImageList` Objekt, wenn ein Handle einer Bildliste angegeben. Wenn eine `CImageList` Objekt nicht an das Handle angefügt ist, wird NULL zurückgegeben.|  
|[CImageList::GetBkColor](#getbkcolor)|Ruft die aktuelle Hintergrundfarbe für eine Bildliste ab.|  
|[CImageList::GetDragImage](#getdragimage)|Ruft die temporären Bilds ab, der für das Ziehen von verwendet wird.|  
|[CImageList::GetImageCount](#getimagecount)|Ruft die Anzahl der Bilder in einer Bildliste ab.|  
|[CImageList::GetImageInfo](#getimageinfo)|Ruft Informationen zu einem Bild ab.|  
|[CImageList::GetSafeHandle](#getsafehandle)|Ruft ab, `m_hImageList`.|  
|[CImageList::Read](#read)|Liest eine Bildliste aus einem Archiv an.|  
|[CImageList::Remove](#remove)|Entfernt ein Bild aus einer Bildliste.|  
|[CImageList::Replace](#replace)|Ersetzt ein Bild in einer Bildliste mit einem neuen Abbild.|  
|[CImageList::SetBkColor](#setbkcolor)|Legt fest, der die Hintergrundfarbe für eine Bildliste.|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Erstellt ein neues Drag-Image an.|  
|[CImageList::SetImageCount](#setimagecount)|Setzt die Anzahl der Bilder in einer Bildliste zurück.|  
|[CImageList:: SetOverlayImage](#setoverlayimage)|Fügt den nullbasierten Index eines Bildes zur Liste der Images als Overlaymasken verwendet werden soll.|  
|[CImageList::Write](#write)|Schreibt eine Bildliste in ein Archiv an.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Gibt das HIMAGELIST angefügt, um die `CImageList`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|Ein Handle, mit der Image-Liste, die auf dieses Objekt angefügt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine "Bildliste" ist eine Auflistung von gleichen Bilder, von die jeder durch den nullbasierten Index verwiesen werden kann. Bilderliste für das werden verwendet, um große Mengen von Symbolen oder Bitmaps effizient zu verwalten. Alle Abbilder in einer Bildliste sind in eine einzelne, große Bitmap im Bildschirm-Gerät-Format enthalten. Eine Bildliste kann auch eine monochrome Bitmap enthalten, die zum Zeichnen von Bildern transparent Masken (Symbolart) enthält. Die Microsoft Win32-Anwendung, die Anwendungsprogrammierschnittstelle (API) bietet Image List-Funktionen, mit denen Sie zum Zeichnen von Bildern, erstellen und Zerstören von Bildlisten, hinzufügen und Entfernen von Bildern, Ersetzen von Bildern, Zusammenfügen von Bildern, und ziehen Images an.  
  
 Dieses Steuerelement (und somit die `CImageList` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen zur Verwendung von `CImageList`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CImageList](../../mfc/using-cimagelist.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="add"></a>  CImageList::Add  
 Rufen Sie diese Funktion zum Hinzufügen von ein oder mehrere Abbilder oder ein Symbol für eine Bildliste.  
  
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
 *pbmImage*  
 Zeiger auf die Bitmap, die das bzw. die Bilder enthält. Die Anzahl der Abbilder wird von der Breite der Bitmap abgeleitet.  
  
 *pbmMask*  
 Zeiger auf die Bitmap, die mit der Maske. Wenn keine Maske für die Bildliste verwendet wird, wird dieser Parameter ignoriert.  
  
 *crMask*  
 Farbe, die zum Generieren der Maske verwendet werden. Jedes Pixel dieser Farbe in der angegebenen Bitmap ist in Schwarz geändert, und das entsprechende Bit in der Maske einer festgelegt ist.  
  
 *hIcon*  
 Handle des Symbols, die dem Bitmap und der Maske für das neue Abbild enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des ersten neuen Images im Erfolgsfall, andernfalls andernfalls - 1.  
  
### <a name="remarks"></a>Hinweise  
 Sie sind verantwortlich für das Symbol "-Handle freigegeben, wenn Sie mehr benötigt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>  CImageList::Attach  
 Rufen Sie diese Funktion zum Anfügen einer Bildliste für eine `CImageList` Objekt.  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 *hImageList*  
 Ein Handle für ein Image List-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Anlage erfolgreich war; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>  CImageList::BeginDrag  
 Mit dieser Funktion können Sie beginnen, ziehen ein Bild.  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 *Nbild*  
 Nullbasierte Index des Bildes, das ziehen.  
  
 *ptHotSpot*  
 Die Koordinaten der Drag & Startposition (in der Regel die Cursorposition). Die Koordinaten sind relativ zur oben links des Bilds.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt eine temporäre Bildliste an, die für das Ziehen von verwendet wird. Das Bild kombiniert das angegebene Bild und die Maske, mit den aktuellen Cursor. Als Reaktion auf zukünftige WM_MOUSEMOVE-Nachrichten, können Sie das Ziehbild verschieben, indem Sie mit der `DragMove` Member-Funktion. Um den Ziehvorgang zu beenden, können Sie die `EndDrag` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>  CImageList::CImageList  
 Erstellt ein `CImageList`-Objekt.  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>  CImageList::Copy  
 Diese Memberfunktion auf, die das Verhalten der Win32-Funktion [ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520), wie im Windows SDK beschrieben.  
  
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
 Der nullbasierte Index des Bildes, das als Ziel des Kopiervorgangs verwendet werden.  
  
 *iSrc*  
 Der nullbasierte Index des Bildes, das als Quelle des Kopiervorgangs verwendet werden.  
  
 *uFlags*  
 Der Bit-Flag-Wert, der angibt, den Typ des Kopiervorgangs auf vorgenommen werden. Dieser Parameter kann einen der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|ILCF_MOVE|Das Quellbild wird in der Ziel-Image-Index kopiert. Dieser Vorgang führt mehrere Instanzen eines angegebenen Bilds. ILCF_MOVE ist die Standardeinstellung.|  
|ILCF_SWAP|Die Images für Quelle und Ziel austauschen Positionen in der Bildliste.|  
  
 *pSrc*  
 Ein Zeiger auf eine `CImageList` -Objekt, das das Ziel des Kopiervorgangs ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
##  <a name="create"></a>  CImageList:: Create  
 Initialisiert eine Bildliste an, und fügt sie an einer [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.  
  
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
 *CX*  
 Dimensionen des jedes Bilds in Pixel.  
  
 *CY*  
 Dimensionen des jedes Bilds in Pixel.  
  
 *nFlags*  
 Gibt den Typ der Liste der Bilder zu erstellen. Dieser Parameter kann eine Kombination der folgenden Werte sein, aber er kann nur eine der enthalten die `ILC_COLOR` Werte.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|ILC_COLOR|Verwenden Sie das Standardverhalten, wenn keine der anderen ILC_COLOR * Flags angegeben ist. In der Regel ist die Standardeinstellung ILC_COLOR4; aber für ältere Anzeigetreiber, ist die Standardeinstellung ILC_COLORDDB.|  
|ILC_COLOR4|Verwenden Sie einen 4-Bit (16 Farben) geräteunabhängige Bitmap (DIB) Abschnitt als Bitmap für die Bildliste.|  
|ILC_COLOR8|Verwenden Sie einen 8-Bit-DIB-Abschnitt. Die Farben für die Farbtabelle sind die gleichen Farben als die Halbtonpalette ab.|  
|ILC_COLOR16|Verwenden Sie eine 16-Bit (32 / 64k Farbe) DIB-Abschnitt.|  
|ILC_COLOR24|Verwenden Sie einen 24-Bit-DIB-Abschnitt.|  
|ILC_COLOR32|Verwenden Sie einen 32-Bit-DIB-Abschnitt.|  
|ILC_COLORDDB|Verwenden Sie eine geräteabhängige Bitmap.|  
|ILC_MASK|Verwendet eine Maske. Liste der Bilder enthält zwei Bitmaps, von denen eine monochrome Bitmap als Maske verwendet wird. Wenn dieser Wert nicht enthalten ist, enthält die Bildliste nur ein Bitmap an. Finden Sie unter [Zeichnen von Bildern aus einer Bildliste](../../mfc/drawing-images-from-an-image-list.md) zusätzliche Informationen zu maskierten Images.|  
  
 *nInitial*  
 Die Anzahl der Bilder, die die Bildliste zunächst enthält.  
  
 *nGrow*  
 Die Anzahl von Bildern, um die Liste der Bilder wachsen kann, wenn das System zum Ändern der Größe der Liste aus, um Platz für neue Images zu schaffen muss. Dieser Parameter stellt die Anzahl neuer Images, die Liste der Größe geänderte Bilder enthalten kann.  
  
 *nBitmapID*  
 Ressourcen-IDs der Bitmap, die Bildliste zugeordnet werden soll.  
  
 *crMask*  
 Farbe, die zum Generieren einer Maske verwendet werden. Jedes Pixel dieser Farbe in die angegebene Bitmap in Schwarz geändert wird, und das entsprechende Bit in der Maske einer festgelegt ist.  
  
 *lpszBitmapID*  
 Eine Zeichenfolge, die die Ressourcen-IDs der Bilder enthält.  
  
 *imageList1*  
 Ein Verweis auf ein `CImageList`-Objekt.  
  
 *nImage1*  
 Der Index des ersten vorhandenen Bilds.  
  
 *ImageList2*  
 Ein Verweis auf ein `CImageList`-Objekt.  
  
 *nImage2*  
 Der Index des zweiten vorhandenen Bilds.  
  
 *DX*  
 Offset der x-Achse des das zweite Bild in Beziehung mit der ersten Abbildung in Pixel.  
  
 *dy*  
 Offset für die y-Achse, der das zweite Bild in Beziehung mit der ersten Abbildung in Pixel.  
  
 *pImageList*  
 Ein Zeiger auf eine `CImageList` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CImageList` in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen dann `Create`, die Liste der Bilder erstellt, und fügt es der `CImageList` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>  CImageList::DeleteImageList  
 Rufen Sie diese Funktion zum Löschen einer Bildliste.  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>  CImageList::DeleteTempMap  
 Wird automatisch aufgerufen, die `CWinApp` -leerlaufzeithandler, `DeleteTempMap` löscht temporäre `CImageList` Objekten von erstellt [FromHandle](#fromhandle), aber zerstört keine Handles ( `hImageList`) vorübergehend verknüpft ist mit der `ImageList` Objekte.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>  CImageList::Detach  
 Mit dieser Funktion wird zum Trennen von einem Image List-Objekt aus einem `CImageList` Objekt.  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Image List-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt ein Handle für das Image List-Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::Attach](#attach).  
  
##  <a name="dragenter"></a>  CImageList::DragEnter  
 Sperren Sie während eines Ziehvorgangs, Updates für das Fenster gemäß *pWndLock* und zeigt das Drag-Bild an der Position gemäß *zeigen*.  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndLock*  
 Zeiger auf das Fenster, das Ziehbild besitzt.  
  
 *Zeigen Sie*  
 Position, an der zur Anzeige des Bilds ziehen. Koordinaten sind relativ zur oben links im Fenster (nicht der Clientbereich).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Koordinaten sind relativ zur oberen linken Ecke des Fensters, damit Sie die Breite des Fensterelemente, z. B. die Rahmen, Titelleiste und Menüleiste kompensieren müssen, wenn Sie die Koordinaten angeben.  
  
 Wenn *pWndLock* NULL ist, die diese Funktion zeichnet das Bild in den Anzeigekontext, dem Desktopfenster zugeordnet und die Koordinaten sind relativ zu der oberen linken Ecke des Bildschirms.  
  
 Diese Funktion sperrt alle anderen Updates des angegebenen Fensters während des Ziehvorgangs an. Wenn Sie alle Zeichnungen während eines Ziehvorgangs, z. B. markieren das Ziel eines Drag & Drop-Vorgangs müssen, können Sie das gezogene Bild vorübergehend ausblenden, mit der [CImageList::DragLeave](#dragleave) Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::BeginDrag](#begindrag).  
  
##  <a name="dragleave"></a>  CImageList::DragLeave  
 Entsperrt die angegebenen Fensters von *pWndLock* und blendet das Ziehbild, können das Fenster aktualisiert werden.  
  
```  
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndLock*  
 Zeiger auf das Fenster, das Ziehbild besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::EndDrag](#enddrag).  
  
##  <a name="dragmove"></a>  CImageList::DragMove  
 Rufen Sie diese Funktion zum Verschieben des Bildes, das bei einem Drag & Drop-Vorgang gezogen wird.  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 *pt*  
 Ziehen Sie neue Position.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird als Reaktion auf eine WM_MOUSEMOVE-Meldung in der Regel aufgerufen werden. Verwenden Sie zum Einleiten eines Ziehvorgangs, die `BeginDrag` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>  CImageList::DragShowNolock  
 Anzeigen oder Ausblenden der bilddarstellung während eines Ziehvorgangs, ohne Sperren das Fenster.  
  
```  
static BOOL PASCAL DragShowNolock(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 *bShow*  
 Gibt an, ob die bilddarstellung angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die [CImageList::DragEnter](#dragenter) Funktion sperrt alle Updates für das Fenster während eines Ziehvorgangs. Diese Funktion sperrt das Fenster jedoch nicht.  
  
##  <a name="draw"></a>  Memberfunktion CImageList:: Draw  
 Rufen Sie diese Funktion zum Zeichnen des Bilds, das bei einem Drag & Drop-Vorgang gezogen wird.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Zeiger auf den Ziel-Gerätekontext.  
  
 *Nbild*  
 Nullbasierte Index des Bildes, das gezeichnet werden soll.  
  
 *pt*  
 Position, an dem in den angegebenen Gerätekontext gezeichnet werden soll.  
  
 *nStyle*  
 Flag, das die Zeichnungsart angibt. Sie können eine oder mehrere der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|ILD_BLEND25, ILD_FOCUS|Zeichnet das Bild, das blending 25 Prozent mit der Hervorhebungsfarbe des Systems. Dieser Wert hat keine Auswirkungen, wenn keine Liste der Bilder eine Maske enthält.|  
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|Zeichnet das Bild, die Kombination von 50 Prozent mit der Hervorhebungsfarbe des Systems. Dieser Wert hat keine Auswirkungen, wenn keine Liste der Bilder eine Maske enthält.|  
|ILD_MASK|Zeichnet die Maske.|  
|ILD_NORMAL|Zeichnet das Bild, das mit der Hintergrundfarbe für die Bildliste. Ist die Farbe des Hintergrunds des Werts CLR_NONE führt dazu, wird das Bild gezeichnet transparent mit der Maske.|  
|ILD_TRANSPARENT|Zeichnet das Bild transparent mit der Maske, unabhängig von die Farbe des Hintergrunds.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList:: SetOverlayImage](#setoverlayimage).  
  
##  <a name="drawex"></a>  CImageList::DrawEx  
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
 *pDC*  
 Zeiger auf den Ziel-Gerätekontext.  
  
 *Nbild*  
 Nullbasierte Index des Bildes, das gezeichnet werden soll.  
  
 *pt*  
 Position, an dem in den angegebenen Gerätekontext gezeichnet werden soll.  
  
 *sz*  
 Die Größe des Teils des Bildes, das relativ zu der oberen linken Ecke des Bilds gezeichnet werden soll. Finden Sie unter *Dx* und *dy* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
 *clrBk*  
 Hintergrundfarbe des Bilds. Finden Sie unter *RgbBk* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
 *clrFg*  
 Die Vordergrundfarbe des Bilds. Finden Sie unter *RgbFg* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
 *nStyle*  
 Flag, das die Zeichnungsart angibt. Finden Sie unter *fStyle* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion verwendet die angegebene Zeichnungsart und wie das Image mit der angegebenen Farbe.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>  CImageList::DrawIndirect  
 Rufen Sie diese Memberfunktion, um ein Bild aus einer Bildliste zu zeichnen.  
  
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
  
 *pDC*  
 Ein Zeiger auf den Ziel-Gerätekontext. Sie müssen dies löschen [CDC](../../mfc/reference/cdc-class.md) Objekt, wenn Sie damit fertig sind.  
  
 *Nbild*  
 Der nullbasierte Index des Bilds gezeichnet werden soll.  
  
 *pt*  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, enthält der x- und y-Koordinaten, in dem das Bild gezeichnet werden.  
  
 *sz*  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur, der angibt, der Größe des Bilds gezeichnet werden soll.  
  
 *ptOrigin*  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die die X - und y-Koordinaten angeben von oben links von den Zeichenvorgang in Bezug auf das Bild selbst enthält. Pixel des Bilds, die auf der linken Seite die X-Koordinate und höher die y-Koordinate sind, werden nicht gezeichnet.  
  
 *fStyle*  
 Flag, das angibt, die Zeichnungsart und optional das Überlagerungsbild. Finden Sie im Abschnitt "Hinweise" Informationen auf dem Überlagerungsbild. Die MFC-Standardimplementierung ILD_NORMAL, zeichnet das Bild, das mit der Hintergrundfarbe für die Bildliste. Wenn die Farbe des Hintergrunds der CLR_NONE führt dazu-Wert ist, wird das Bild gezeichnet transparent mit einer Maske.  
  
 Andere mögliche Formate sind unter beschrieben die *fStyle* Mitglied der [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) Struktur.  
  
 *dwRop*  
 Wert, der einen rastervorgang Code angibt. Diese Codes definieren, wie die Farbdaten für das Quellrechteck mit die Farbdaten für das Zielrechteck, um die endgültige Farbe zu erreichen kombiniert werden. MFC Standardimplementierung SRCCOPY, kopiert das Quellrechteck direkt in das Zielrechteck. Dieser Parameter wird ignoriert, wenn die *fStyle* Parameter enthält keinen das ILD_ROP-Flag.  
  
 Weitere mögliche Werte sind unter beschrieben die *DwRop* Mitglied der [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) Struktur.  
  
 *rgbBack*  
 Die Hintergrundfarbe Image standardmäßig CLR_DEFAULT. Dieser Parameter kann eine Anwendung definierte RGB-Wert oder eine der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|CLR_DEFAULT|Standard-Hintergrundfarbe. Das Bild gezeichnet wird, mit der Hintergrundfarbe der Image-Liste.|  
|CLR_NONE FÜHRT DAZU|Keine Hintergrundfarbe. Das Bild wird transparent gezeichnet.|  
  
 *rgbFore*  
 Image-Vordergrundfarbe, standardmäßig CLR_DEFAULT. Dieser Parameter kann eine Anwendung definierte RGB-Wert oder eine der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|CLR_DEFAULT|Die Standardvordergrundfarbe. Das Bild gezeichnet wird, mit der Hervorhebungsfarbe des Systems als Vordergrundfarbe.|  
|CLR_NONE FÜHRT DAZU|Keine Blend-Farbe. Das Bild wird durch die Farbe des Zielgerätekontexts gemischt.|  
  
 Dieser Parameter wird verwendet, nur dann, wenn *fStyle* dem ILD_BLEND25 oder ILD_BLEND50-Flag enthält.  
  
 *fState*  
 Flag zum Angeben des zeichnen-Zustands. Dieser Member kann ein oder mehrere Status-Flags für Image-Liste enthalten.  
  
 *Frame*  
 Wirkt sich auf das Verhalten von saturate und Alpha-Blending überlagern.  
  
 Bei Verwendung mit ILS_SATURATE enthält dieser Member den Wert, der jede Farbkomponente des RGB-Triplets für jedes Pixel im Symbol hinzugefügt wird.  
  
 Bei Verwendung mit ILS_APLHA enthält dieser Member den Wert für den alpha-Kanal. Dieser Wert kann zwischen 0 und 255 liegen, wobei 0 vollständig transparent, und 255 wird vollständig deckend sein.  
  
 *crEffect*  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Lichteffekts und Schatten Effekte verwendete Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Bild erfolgreich gezeichnet wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Version, wenn Sie die Win32-Struktur selbst eingeben möchten. Verwenden Sie die zweite Version aus, wenn Sie verwenden möchten, nutzen Sie eine oder mehrere der MFC Standardargumente oder zu vermeiden, Verwalten der Struktur.  
  
 Ein Overlay-Image ist ein Bild, das auf das primäre Bild, das in diese Memberfunktion von angegeben gezeichnet wird die *Nbild* Parameter. Zeichnen Sie eine Overlaymaske mithilfe der [zeichnen](#draw) Member-Funktion mit den einsbasierten Index die Overlay-Maske, die mithilfe von angegeben die [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>  CImageList::EndDrag  
 Rufen Sie diese Funktion zum Beenden eines Ziehvorgangs ein.  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Einleiten eines Ziehvorgangs, die `BeginDrag` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>  CImageList::ExtractIcon  
 Rufen Sie diese Funktion zum Erstellen eines Symbols basierend auf einem Bild und der entsprechenden Maske in einer Bildliste.  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 *Nbild*  
 Nullbasierte Index des Bilds.  
  
### <a name="return-value"></a>Rückgabewert  
 Handle des Symbols, das bei erfolgreicher Ausführung; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode beruht auf das Verhalten der [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) Makro auf das Symbol zu erstellen. Finden Sie in der [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) Makro für Weitere Informationen zum Symbol für Erstellung und Bereinigung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>  CImageList::FromHandle  
 Gibt einen Zeiger auf eine `CImageList` Objekt, wenn ein Handle einer Bildliste angegeben.  
  
```  
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 *hImageList*  
 Gibt die Bildliste an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CImageList` -Objekt, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CImageList` ist noch nicht auf das Handle, eine temporäre angefügt `CImageList` Objekt erstellt und angefügt. Diese temporären `CImageList` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Zeit im Leerlauf in seiner Ereignisschleife verfügt, zu diesem Zeitpunkt alle temporären Objekte gelöscht werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>  CImageList::FromHandlePermanent  
 Gibt einen Zeiger auf eine `CImageList` Objekt, wenn ein Handle einer Bildliste angegeben.  
  
```  
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 *hImageList*  
 Gibt die Bildliste an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CImageList` -Objekt, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CImageList` Objekt nicht an das Handle angefügt ist, wird NULL zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>  CImageList::GetBkColor  
 Rufen Sie diese Funktion, um die aktuelle Hintergrundfarbe für eine Bildliste abgerufen werden soll.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die RGB-Farbwert, der die `CImageList` Objekt Background-Farbe.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::SetBkColor](#setbkcolor).  
  
##  <a name="getdragimage"></a>  CImageList::GetDragImage  
 Ruft die temporären Bilds ab, der für das Ziehen von verwendet wird.  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 *lpPoint*  
 Adresse von einem [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die die aktuelle empfängt ziehen Sie die Position.  
  
 *lpPointHotSpot*  
 Adresse von einem `POINT` -Struktur, den Offset des Bilds ziehen Sie relativ zur Ziehposition empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf den temporären Bilds, die Liste wird verwendet, für das Ziehen; andernfalls NULL.  
  
##  <a name="getimagecount"></a>  CImageList::GetImageCount  
 Rufen Sie diese Funktion zum Abrufen der Anzahl von Bildern in einer Bildliste.  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bilder.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::ExtractIcon](#extracticon).  
  
##  <a name="getimageinfo"></a>  CImageList::GetImageInfo  
 Rufen Sie diese Funktion zum Abrufen von Informationen zu einem Bild.  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *Nbild*  
 Nullbasierte Index des Bilds.  
  
 *pImageInfo*  
 Zeiger auf ein [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393) -Struktur, die Informationen zu dem Bild empfängt. Die Informationen in dieser Struktur kann verwendet werden, um die Bitmaps für das Image direkt zu bearbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `IMAGEINFO` Struktur enthält Informationen zu einem Bild in einer Bildliste.  
  
##  <a name="getsafehandle"></a>  CImageList::GetSafeHandle  
 Mit dieser Funktion wird zum Abrufen der `m_hImageList` -Datenmember.  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf die Liste der angefügten Bilds Wenn kein Objekt verbunden ist, andernfalls NULL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>  CImageList::m_hImageList  
 Ein Handle der Bildliste an dieses Objekt angefügt werden soll.  
  
 `HIMAGELIST m_hImageList;`  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hImageList` -Datenmember ist eine öffentliche Variable des Typs HIMAGELIST.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>  CImageList::operator HIMAGELIST  
 Verwenden Sie diesen Operator, um das angefügte Handle zu erhalten die `CImageList` Objekt.  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle der Bildliste durch dargestellt die `CImageList` Objekt; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Umwandlungsoperator, die direkte Verwendung von ein HIMAGELIST-Objekt unterstützt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>  CImageList::Read  
 Rufen Sie diese Funktion, um eine Bildliste aus einem Archiv zu lesen.  
  
```  
BOOL Read(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parameter  
 *pArchive*  
 Ein Zeiger auf eine `CArchive` Objekt aus der Liste der Bilder, die gelesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>  CImageList::Remove  
 Rufen Sie diese Funktion, um ein Bild aus einem Image List-Objekt zu entfernen.  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 *Nbild*  
 Nullbasierte Index des zu entfernenden Bildes.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente, die nach *Nbild* jetzt eine Position nach unten zu verschieben. Z. B. wenn eine Bildliste zwei Elemente enthält, bewirkt löschen das erste Element den verbleibenden Artikel jetzt in der ersten Position sein. *Nbild*= 0 für das Element in der ersten Position.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>  CImageList::Replace  
 Rufen Sie diese Funktion, um ein Bild in einer Bildliste mit einem neuen Abbild ersetzen.  
  
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
 *Nbild*  
 Nullbasierte Index des Bildes, das ersetzen.  
  
 *pbmImage*  
 Ein Zeiger auf die Bitmap, die das Bild enthält.  
  
 *pbmMask*  
 Ein Zeiger auf die Bitmap, die mit der Maske. Wenn keine Maske für die Bildliste verwendet wird, wird dieser Parameter ignoriert.  
  
 *hIcon*  
 Ein Handle für das Symbol, das die Bitmap und eine Maske für das neue Abbild enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version, die Rückgabe von "bool" zurückgibt ungleich NULL, wenn erfolgreich; andernfalls 0.  
  
 Die Version, die Rückgabe **Int** gibt den nullbasierten Index des Bilds zurück, wenn erfolgreich, andernfalls - 1.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nach dem Aufruf dieser Memberfunktion [SetImageCount](#setimagecount) So weisen Sie das neue image gültigen Bilder auf den Platzhalter Indexnummern.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::SetImageCount](#setimagecount).  
  
##  <a name="setbkcolor"></a>  CImageList::SetBkColor  
 Rufen Sie diese Funktion zum Festlegen der Hintergrundfarbe für eine Bildliste.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Parameter  
 *CR*  
 Die Hintergrundfarbe festlegen. Es kann CLR_NONE führt dazu, sein. In diesem Fall werden die Bilder gezeichnet transparent mit der Maske.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Hintergrundfarbe, wenn erfolgreich; andernfalls CLR_NONE führt dazu.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>  CImageList::SetDragCursorImage  
 Erstellt ein neues Bild mit Drag & durch die Kombination der angegebenen Bilds (in der Regel eine Maus Cursorbild) mit dem aktuellen Drag-Image an.  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 *Nziehen*  
 Der Index des neuen Images mit dem Ziehbild kombiniert werden.  
  
 *ptHotSpot*  
 Die Position des Hotspots in das neue Image.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Da die Funktionen zum Ziehen das neue Image während eines Ziehvorgangs verwenden, befolgen Sie die Windows [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) Funktion, um den tatsächlichen Cursor nach dem Aufruf ausblenden `CImageList::SetDragCursorImage`. Andernfalls kann das System angezeigt, damit zwei Mauscursor für die Dauer des Ziehvorgangs.  
  
##  <a name="setimagecount"></a>  CImageList::SetImageCount  
 Rufen Sie diese Memberfunktion zum Zurücksetzen der Anzahl der Bilder in einem `CImageList` Objekt.  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>Parameter  
 *uNewCount*  
 Der Wert, der die neue Gesamtzahl der Bilder in der Bildliste angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Memberfunktion zum Erhöhen der Anzahl von Bildern in der Bildliste aufrufen, rufen Sie [ersetzen](#replace) für jedes zusätzliche Image gültigen Images die neuen Indizes zuweisen. Wenn Sie nicht im gültigen Images die Indizes zuweisen, werden Draw-Vorgänge, die die neuen Images erstellen nicht vorhersehbar sein.  
  
 Wenn Sie die Größe des einer Bildliste mit dieser Funktion verringern, werden die abgeschnittene Images freigegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>  CImageList:: SetOverlayImage  
 Rufen Sie diese Funktion zum Hinzufügen des nullbasierten Indexes eines Bildes zur Liste der Images als Overlaymasken verwendet werden soll.  
  
```  
BOOL SetOverlayImage(
    int nImage,  
    int nOverlay);
```  
  
### <a name="parameters"></a>Parameter  
 *Nbild*  
 Nullbasierte Index des Bildes, das als eine Overlaymaske verwendet werden.  
  
 *nOverlay*  
 1 basierende Index der Überlagerung Maske.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Liste können bis zu vier Indizes hinzugefügt werden.  
  
 Eine Overlaymaske ist ein Bild transparent über ein anderes Bild gezeichnet. Zeichnen Sie eine Overlaymaske über ein Image mithilfe der [Memberfunktion CImageList:: Draw](#draw) Member-Funktion mit den einsbasierten Index die Overlay-Maske, die mithilfe des Makros INDEXTOOVERLAYMASK angegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>  CImageList::Write  
 Rufen Sie diese Funktion, um ein Image List-Objekt in ein Archiv zu schreiben.  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parameter  
 *pArchive*  
 Ein Zeiger auf eine `CArchive` Objekt, in der Liste der Bilder gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl-Klasse](../../mfc/reference/ctabctrl-class.md)
