---
title: CImageList-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- Windows common controls [C++], CImageList
- image lists [C++], CImageList class
- CImageList class
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
caps.latest.revision: 19
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
ms.openlocfilehash: e61d99d6d68b1c68cd5e306dd0fcd10d6fe4324d
ms.lasthandoff: 02/24/2017

---
# <a name="cimagelist-class"></a>CImageList-Klasse
Stellt die Funktionalität des allgemeinen Windows-Bildlisten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CImageList : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::CImageList](#cimagelist)|Erstellt ein `CImageList`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::Add](#add)|Fügt ein Bild oder Bilder auf einer Bildliste.|  
|[CImageList::Attach](#attach)|Fügt eine Bildliste zu einem `CImageList` Objekt.|  
|[CImageList::BeginDrag](#begindrag)|Beginnt, ziehen ein Bild.|  
|[CImageList::Copy](#copy)|Kopiert ein Abbild innerhalb einer `CImageList` Objekt.|  
|[CImageList:: Create](#create)|Initialisiert mit einer Bildliste und fügt es ein `CImageList` Objekt.|  
|[CImageList::DeleteImageList](#deleteimagelist)|Löscht eine Bildliste.|  
|[CImageList::DeleteTempMap](#deletetempmap)|Aufgerufen, indem die [CWinApp](../../mfc/reference/cwinapp-class.md) Zeit im Leerlauf Handler So löschen Sie alle temporären `CImageList` von erstellte Objekt `FromHandle`.|  
|[CImageList::Detach](#detach)|Trennt eine Image-List-Objekt aus einer `CImageList` -Objekt und gibt ein Handle für eine Bildliste.|  
|[CImageList::DragEnter](#dragenter)|Sperren während eines Ziehvorgangs Updates und zeigt das Bild an der angegebenen Position.|  
|[CImageList::DragLeave](#dragleave)|Das Fenster entsperrt, und blendet das Ziehbild, damit das Fenster aktualisiert werden kann.|  
|[CImageList::DragMove](#dragmove)|Verschiebt das Bild, das während eines Drag & Drop-Vorgangs gezogen wird.|  
|[CImageList::DragShowNolock](#dragshownolock)|Blendet das Bild während eines Ziehvorgangs ohne Sperren des Fensters.|  
|[Memberfunktion CImageList:: Draw](#draw)|Zeichnet das Bild, das während eines Drag & Drop-Vorgangs gezogen wird.|  
|[CImageList::DrawEx](#drawex)|Zeichnet ein Bild Listenelement in den angegebenen Gerätekontext. Die Funktion verwendet die angegebene Zeichnungsart und das Bild mit der angegebenen Farbe gemischt.|  
|[CImageList::DrawIndirect](#drawindirect)|Zeichnet ein Bild aus einer Bildliste.|  
|[CImageList::EndDrag](#enddrag)|Beendet einen Ziehvorgang.|  
|[CImageList::ExtractIcon](#extracticon)|Erstellt ein Symbol basierend auf einem Bild und die Maske in einer Bildliste.|  
|[CImageList::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste angegeben. Wenn ein `CImageList`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CImageList`-Objekt erstellt und angefügt.|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste angegeben. Wenn ein `CImageList` Objekt ist nicht angefügt, um das Handle **NULL** zurückgegeben wird.|  
|[CImageList::GetBkColor](#getbkcolor)|Ruft die aktuelle Hintergrundfarbe einer Bildliste ab.|  
|[CImageList::GetDragImage](#getdragimage)|Ruft die temporären Bilds ab, die zum Ziehen von verwendet wird.|  
|[CImageList::GetImageCount](#getimagecount)|Ruft die Anzahl der Bilder in einer Bildliste ab.|  
|[CImageList::GetImageInfo](#getimageinfo)|Ruft Informationen zu einem Bild ab.|  
|[CImageList::GetSafeHandle](#getsafehandle)|Ruft **M_hImageList**.|  
|[CImageList::Read](#read)|Liest eine Liste der Images aus dem Archiv.|  
|[CImageList::Remove](#remove)|Entfernt ein Bild aus einer Bildliste.|  
|[CImageList::Replace](#replace)|Ersetzt ein Bild in einer Bildliste mit einem neuen Abbild.|  
|[CImageList::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe einer Bildliste.|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Erstellt ein neues Drag-Image.|  
|[CImageList::SetImageCount](#setimagecount)|Setzt die Anzahl der Bilder in einer Bildliste zurück.|  
|[CImageList:: SetOverlayImage](#setoverlayimage)|Die Liste der Bilder als Overlaymasken verwendet hinzugefügt den nullbasierten Index eines Bilds.|  
|[CImageList::Write](#write)|Schreibt eine Bildliste in ein Archiv.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Gibt die `HIMAGELIST` angefügt werden, um die `CImageList`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|Ein Handle, die diesem Objekt zugeordneten Bildliste enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Liste"Image" ist eine Sammlung von gleich großer Bilder, von die jede auf durch den nullbasierten Index verwiesen werden kann. Bildlisten werden verwendet, um große Mengen von Symbolen oder Bitmaps effizient zu verwalten. Alle Bilder in einer Bildliste sind in einer einzelnen, Breiten Bitmap im Bildschirmformat Gerät enthalten. Eine Bildliste kann auch eine monochrome Bitmap enthalten, die Masken zum Zeichnen transparenter Bilder (Symbolformat) enthält. Die Anwendungsprogrammierschnittstelle (API) Microsoft Win32-Anwendung bietet Image List-Funktionen, mit denen Sie zum Zeichnen von Bildern, erstellen und Zerstören von Bildlisten, hinzufügen und Entfernen von Bildern, ersetzen, Zusammenfügen von Bildern und Bilder ziehen.  
  
 Dieses Steuerelement (und somit die `CImageList` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen zur Verwendung von `CImageList`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CImageList](../../mfc/using-cimagelist.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="add"></a>CImageList::Add  
 Rufen Sie diese Funktion, um ein oder mehrere Bilder oder ein Symbol mit einer Bildliste hinzuzufügen.  
  
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
 Ein Zeiger auf die Bitmap, die das Bild oder die Bilder enthält. Die Breite der Bitmap ist die Anzahl der Abbilder abgeleitet.  
  
 `pbmMask`  
 Ein Zeiger auf die Bitmap mit der Maske. Wenn keine Maske mit Liste der Images verwendet wird, wird dieser Parameter ignoriert.  
  
 `crMask`  
 Zum Generieren der Maske verwendete Farbe. Diese Farbe in der angegebenen Bitmap jedes Pixel auf Schwarz geändert wird, und das entsprechende Bit in der Maske auf einen festgelegt ist.  
  
 `hIcon`  
 Handle für das Symbol, das die Bitmap und die Maske für das neue Abbild enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des ersten neuen Bilds, wenn erfolgreich; andernfalls – 1.  
  
### <a name="remarks"></a>Hinweise  
 Sie sind verantwortlich für das Symbolhandle freigeben, wenn Sie damit fertig sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#1;](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>CImageList::Attach  
 Rufen Sie diese Funktion zum Anfügen einer Bildliste zu einem `CImageList` Objekt.  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `hImageList`  
 Ein Handle für ein Image List-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Anlage erfolgreich war; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#2;](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>CImageList::BeginDrag  
 Rufen Sie diese Funktion, um zu beginnen, ziehen ein Bild.  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds zu ziehen.  
  
 `ptHotSpot`  
 Die Koordinaten der ziehen Startposition (in der Regel die Cursorposition). Die Koordinaten sind der oberen linken Ecke des Bildes.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt eine temporäre Bildliste, die zum Ziehen von verwendet wird. Das Abbild kombiniert das angegebene Bild und die Maske mit den aktuellen Cursor. Als Antwort auf nachfolgende `WM_MOUSEMOVE` Nachrichten, Sie können das Bild bewegen, indem Sie mit der `DragMove` Member-Funktion. Um den Ziehvorgang zu beenden, können Sie die `EndDrag` -Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&3;](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>CImageList::CImageList  
 Erstellt ein `CImageList`-Objekt.  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>CImageList::Copy  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
 `iSrc`  
 Der nullbasierte Index des Bildes, das als Quelle für den Kopiervorgang verwendet werden.  
  
 `uFlags`  
 Die Bit-Flag-Wert, der angibt, den Typ des Kopiervorgangs vorgenommen werden. Dieser Parameter kann einen der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`ILCF_MOVE`|Das Zielbild Index wird das Quellbild kopiert. Dieser Vorgang führt mehrere Instanzen eines angegebenen Bilds. Standardmäßig ist `ILCF_MOVE` festgelegt.|  
|`ILCF_SWAP`|Die Quell- und Ziel-Bilder austauschen, Positionen innerhalb der Bildliste.|  
  
 `pSrc`  
 Ein Zeiger auf ein `CImageList` -Objekt, das das Ziel des Kopiervorgangs ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&6;](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
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
 Dimensionen der einzelnen Bilds in Pixel.  
  
 `cy`  
 Dimensionen der einzelnen Bilds in Pixel.  
  
 `nFlags`  
 Gibt den Typ der Bildliste zu erstellen. Dieser Parameter kann eine Kombination der folgenden Werte sein, es kann jedoch nur eines der `ILC_COLOR` Werte.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`ILC_COLOR`|Verwenden Sie das Standardverhalten, wenn keine der anderen `ILC_COLOR`*-Flag angegeben werden. In der Regel die Standardeinstellung ist `ILC_COLOR4`; aber für ältere Anzeigetreiber, die Standardeinstellung ist `ILC_COLORDDB`.|  
|`ILC_COLOR4`|Verwenden Sie einen 4-Bit (16 Farben) geräteunabhängige Bitmap (DIB) Abschnitt als Bitmap für die Bildliste.|  
|`ILC_COLOR8`|Verwenden Sie einen 8-Bit-DIB-Abschnitt. Die Farben für die Tabelle sind die Farben die Halbtonpalette.|  
|`ILC_COLOR16`|Verwenden Sie eine 16-Bit (32 / 64k Farbe) DIB-Abschnitt.|  
|`ILC_COLOR24`|Verwenden Sie einen 24-Bit-DIB-Abschnitt.|  
|`ILC_COLOR32`|Verwenden Sie einen 32-Bit-DIB-Abschnitt.|  
|`ILC_COLORDDB`|Verwenden Sie eine geräteabhängige Bitmap.|  
|`ILC_MASK`|Verwendet eine Maske. Die Bildliste enthält zwei Bitmaps, von denen eine monochrome Bitmap als Maske verwendet wird. Wenn dieser Wert nicht angegeben wird, enthält die Bildliste nur eine Bitmap. Finden Sie unter [Zeichnen von Bildern aus einer Bildliste](../../mfc/drawing-images-from-an-image-list.md) Weitere Informationen zu Maskierte Bilder.|  
  
 `nInitial`  
 Anzahl der Bilder, die zunächst die Bildliste enthält.  
  
 `nGrow`  
 Anzahl der Bilder, um die Liste der Images wachsen kann, wenn das System die Liste, um Platz für neue Abbilder der Größe anpassen muss. Dieser Parameter gibt die Anzahl neuer Abbilder, die angepasste Bildliste enthalten kann.  
  
 `nBitmapID`  
 Ressourcen-IDs der Bitmap die Bildliste zugeordnet werden soll.  
  
 `crMask`  
 Zum Generieren einer Maske verwendete Farbe. Jedes Pixel dieser Farbe in der angegebenen Bitmap in Schwarz geändert wird, und das entsprechende Bit in der Maske auf einen festgelegt ist.  
  
 `lpszBitmapID`  
 Eine Zeichenfolge, die die Ressourcen-IDs der Bilder enthält.  
  
 `imagelist1`  
 Ein Verweis auf ein `CImageList`-Objekt.  
  
 `nImage1`  
 Der Index des ersten vorhandenen Bildes.  
  
 `imagelist2`  
 Ein Verweis auf ein `CImageList`-Objekt.  
  
 `nImage2`  
 Der Index des zweiten vorhandenen Images.  
  
 `dx`  
 Der Offset der x-Achse für das zweite Bild im Verhältnis zum ersten Bilds in Pixel.  
  
 `dy`  
 Der Offset der y-Achse für das zweite Bild im Verhältnis zum ersten Bilds in Pixel.  
  
 `pImageList`  
 Ein Zeiger auf ein `CImageList` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie eine `CImageList` in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann `Create`, die Liste der Images erstellt und fügt es der `CImageList`Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#7;](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>CImageList::DeleteImageList  
 Rufen Sie diese Funktion zum Löschen einer Bildliste.  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#8;](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>CImageList::DeleteTempMap  
 Automatisch aufgerufen, die `CWinApp` Zeit im Leerlauf-Handler `DeleteTempMap` löscht alle temporären `CImageList` von erstellten Objekte [FromHandle](#fromhandle), aber zerstört keine Handles ( `hImageList`) vorübergehend zugeordnet der **ImageList** Objekte.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#9;](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>CImageList::Detach  
 Mit dieser Funktion können Sie trennen eine Liste Bildobjekt aus einem `CImageList` Objekt.  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Image List-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt ein Handle für das Image List-Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::Attach](#attach).  
  
##  <a name="dragenter"></a>CImageList::DragEnter  
 Sperren Sie während eines Ziehvorgangs Updates vom angegebenen `pWndLock` und zeigt das Bild an der angegebenen Position `point`.  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndLock`  
 Ein Zeiger auf das Fenster, das Bild besitzt.  
  
 `point`  
 Die Position, an der das Bild angezeigt. Koordinaten werden der oberen linken Ecke des Fensters (nicht die Clientbereich).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Koordinaten sind relativ zur oberen linken Ecke des Fensters, damit die Breite von Fensterelementen, z. B. die Rahmen, die Titelleiste und die Menüleiste kompensieren muss, wenn die Koordinaten festgelegt.  
  
 Wenn `pWndLock` ist **NULL**, diese Funktion zeichnet das Bild in der Anzeigekontext mit dem Desktopfenster und Koordinaten der oberen linken Ecke des Bildschirms werden.  
  
 Diese Funktion sperrt alle anderen Updates des angegebenen Fensters während des Ziehvorgangs. Wenn Sie eine Zeichnung während eines Ziehvorgangs, z. B. markieren das Ziel eines Drag & Drop-Vorgangs müssen können Sie das gezogene Bild vorübergehend ausblenden, indem die [CImageList::DragLeave](#dragleave) Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::BeginDrag](#begindrag).  
  
##  <a name="dragleave"></a>CImageList::DragLeave  
 Hebt die Sperre von angegebenen `pWndLock` und blendet das Bild ziehen Sie das Fenster aktualisiert werden, sodass.  
  
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
 Rufen Sie diese Funktion zum Verschieben des Bildes, das während eines Drag & Drop-Vorgangs gezogen wird.  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ziehen Sie neue Position.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist in der Regel als Reaktion auf eine `WM_MOUSEMOVE` Nachricht. Zum Starten eines Ziehvorgangs verwenden die `BeginDrag` -Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&4;](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>CImageList::DragShowNolock  
 Blendet das Bild während eines Ziehvorgangs ohne Sperren des Fensters.  
  
```  
static BOOL PASCAL DragShowNolock(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob das Bild angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die [CImageList::DragEnter](#dragenter) Funktion sperrt alle Updates für das Fenster während eines Ziehvorgangs ein. Diese Funktion wird das Fenster jedoch nicht gesperrt.  
  
##  <a name="draw"></a>Memberfunktion CImageList:: Draw  
 Rufen Sie diese Funktion zum Zeichnen des Bilds, das während eines Drag & Drop-Vorgangs gezogen wird.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Zielgerätekontext.  
  
 `nImage`  
 Nullbasierte Index des zu zeichnenden Bilds.  
  
 `pt`  
 Ort, an dem in den angegebenen Gerätekontext gezeichnet werden soll.  
  
 `nStyle`  
 Flag, das das Zeichnungsformat angibt. Es kann eine oder mehrere der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`ILD_BLEND25`, **ILD_FOCUS**|Zeichnet das Bild, das Mischen von 25 Prozent mit der Hervorhebungsfarbe des Systems. Dieser Wert hat keine Auswirkung, wenn die Bildliste eine Maske nicht enthält.|  
|`ILD_BLEND50`, **ILD_SELECTED**, **ILD_BLEND**|Zeichnet das Bild, das Mischen von 50 Prozent mit der Hervorhebungsfarbe des Systems. Dieser Wert hat keine Auswirkung, wenn die Bildliste eine Maske nicht enthält.|  
|**ILD_MASK**|Zeichnet die Maske.|  
|`ILD_NORMAL`|Zeichnet das Bild mit der Hintergrundfarbe für die Bildliste. Wenn die Hintergrundfarbe der `CLR_NONE` Wert, der das Bild gezeichnet wird, transparent mit der Maske.|  
|`ILD_TRANSPARENT`|Zeichnet das Bild transparent die Maske, unabhängig von der Hintergrundfarbe.|  
  
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
 Ein Zeiger auf den Zielgerätekontext.  
  
 `nImage`  
 Nullbasierte Index des zu zeichnenden Bilds.  
  
 `pt`  
 Ort, an dem in den angegebenen Gerätekontext gezeichnet werden soll.  
  
 `sz`  
 Die Größe des Teils des Bilds relativ zu der oberen linken Ecke des Bildes gezeichnet. Finden Sie unter `dx` und *dy* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 *clrBk*  
 Die Hintergrundfarbe des Bilds. Finden Sie unter *RgbBk* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 *clrFg*  
 Die Vordergrundfarbe des Bilds. Finden Sie unter *RgbFg* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 `nStyle`  
 Flag, das das Zeichnungsformat angibt. Finden Sie unter *fStyle* in [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion verwendet die angegebene Zeichnungsart und das Bild mit der angegebenen Farbe gemischt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#10;](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>CImageList::DrawIndirect  
 Rufen Sie diese Memberfunktion zum Zeichnen eines Bildes aus einer Bildliste.  
  
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
 Ein Zeiger auf eine [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) -Struktur, die Informationen zu den Ziehvorgang enthält.  
  
 `pDC`  
 Ein Zeiger auf den Zielgerätekontext. Sie müssen diese löschen [CDC](../../mfc/reference/cdc-class.md) Objekt, wenn Sie damit fertig sind.  
  
 `nImage`  
 Der nullbasierte Index des Bilds, gezeichnet werden soll.  
  
 `pt`  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, enthält die X- und y-Koordinaten, in dem das Bild gezeichnet werden.  
  
 `sz`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur, der die Größe des Bilds, gezeichnet werden soll.  
  
 *ptOrigin*  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die die X- und y-Koordinaten angeben der oberen linken Ecke des Vorgangs in Bezug auf das Bild selbst zeichnen enthält. Pixel des Bilds, die auf der linken Seite der X-Koordinate und über die y-Koordinate sind, werden nicht gezeichnet.  
  
 `fStyle`  
 Flag, das angibt, das Zeichnungsformat und optional das Bild überlagert. Finden Sie im Abschnitt "Hinweise" Informationen auf das Bild überlagert. Die MFC-Standard-Implementierung `ILD_NORMAL`, zeichnet das Bild mit der Hintergrundfarbe für die Bildliste. Wenn die Hintergrundfarbe der `CLR_NONE` Wert, der das Bild gezeichnet wird, transparent mit einer Maske.  
  
 Andere mögliche Formate sind beschrieben unter der **fStyle** Mitglied der [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) Struktur.  
  
 *dwRop*  
 Wert, der ein Raster Vorgangscode angibt. Diese Codes definieren, wie die Farbdaten für das Quellrechteck mit Farbe Daten für das Zielrechteck erreichen die endgültige Farbe kombiniert werden. MFC Standardimplementierung **SRCCOPY**, das Quellrechteck direkt in das Zielrechteck kopiert. Dieser Parameter wird ignoriert, wenn die `fStyle` Parameter enthält keinen der **ILD_ROP** Flag.  
  
 Andere mögliche Werte sind beschrieben unter der **DwRop** Mitglied der [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) Struktur.  
  
 *rgbBack*  
 Die Hintergrundfarbe Bild standardmäßig `CLR_DEFAULT`. Dieser Parameter kann eine Anwendung definierte RGB-Wert oder einen der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`CLR_DEFAULT`|Standard-Hintergrundfarbe. Mit der Hintergrundfarbe der Image-Liste das Bild gezeichnet.|  
|`CLR_NONE`|Keine Hintergrundfarbe. Das Bild transparent dargestellt.|  
  
 *rgbFore*  
 Bild-Vordergrundfarbe standardmäßig `CLR_DEFAULT`. Dieser Parameter kann eine Anwendung definierte RGB-Wert oder einen der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`CLR_DEFAULT`|Standard-Vordergrundfarbe. Das Bild wird unter Verwendung der Hervorhebungsfarbe des Systems als Vordergrundfarbe gezeichnet.|  
|`CLR_NONE`|Keine Füllfarbe. Das Bild wird mit der Farbe des Zielgerätekontexts gemischt.|  
  
 Dieser Parameter wird nur verwendet, wenn `fStyle` enthält die `ILD_BLEND25` oder `ILD_BLEND50` Flag.  
  
 *fState*  
 Flag, das die Zeichnung Status angibt. Dieser Member kann ein oder mehrere Status-Flags der Image-Liste enthalten.  
  
 *Frame*  
 Wirkt sich auf das Verhalten von saturate und Alpha-Blending überlagern.  
  
 Bei Verwendung mit **ILS_SATURATE**, dieser Member enthält den Wert, der die RGB-Dreiergruppe für jedes Pixel in der jede Komponente Farbe hinzugefügt wird.  
  
 Bei Verwendung mit **ILS_APLHA**, dieses Element enthält den Wert für den Alphakanal. Dieser Wert kann zwischen 0 und 255 liegen, wobei 0 vollständig transparent, und 255 wird transparent sein.  
  
 *crEffect*  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) für Leuchten und Schatten Effekte verwendete Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist das Bild erfolgreich gezeichnet, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Version, wenn Sie die Win32-Struktur selbst füllen möchten. Verwenden Sie die zweite Version, wenn eine oder mehrere der Argumente von MFC nutzen, oder verwalten die Struktur erstellt werden soll.  
  
 Ein Overlaybild ist ein Bild, das über das primäre Bild, das gemäß der von dieser Memberfunktion gezeichnet der `nImage` Parameter. Zeichnen Sie eine Überlagerung Maske mithilfe der [zeichnen](#draw) Memberfunktion mit dem Index eins der Überlagerung Maske mit angegeben der [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#11;](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>CImageList::EndDrag  
 Rufen Sie diese Funktion, um einen Ziehvorgang beendet.  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>Hinweise  
 Zum Starten eines Ziehvorgangs verwenden die `BeginDrag` -Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&5;](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>CImageList::ExtractIcon  
 Rufen Sie diese Funktion zum Erstellen eines Symbols basierend auf einem Bild und deren zugehörige Maske in einer Bildliste.  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds.  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für das Symbol, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode stützt sich auf das Verhalten der [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) Makro auf das Symbol erstellen. Finden Sie in der [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) Makro für Weitere Informationen zum Symbol für Erstellung und Bereinigung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#12;](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>CImageList::FromHandle  
 Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste angegeben.  
  
```  
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `hImageList`  
 Gibt die Liste der Images.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CImageList` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CImageList` ist noch nicht auf das Handle zu einem temporären angefügt `CImageList` Objekt erstellt und angefügt wird. Dieser temporäre `CImageList` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner Ereignisschleife aufweist, zu diesem Zeitpunkt alle temporären Objekte gelöscht werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#13;](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>CImageList::FromHandlePermanent  
 Gibt einen Zeiger auf ein `CImageList` Objekt, wenn ein Handle zu einer Bildliste angegeben.  
  
```  
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `hImageList`  
 Gibt die Liste der Images.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CImageList` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CImageList` Objekt ist nicht angefügt, um das Handle **NULL** zurückgegeben wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&14;](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>CImageList::GetBkColor  
 Rufen Sie diese Funktion, um die aktuelle Hintergrundfarbe einer Bildliste abzurufen.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der RGB-Farbwert der `CImageList` -Objekt Hintergrundfarbe.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::SetBkColor](#setbkcolor).  
  
##  <a name="getdragimage"></a>CImageList::GetDragImage  
 Ruft die temporären Bilds ab, die zum Ziehen von verwendet wird.  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoint`  
 Adresse einer [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, empfängt den aktuellen, Position ziehen.  
  
 *lpPointHotSpot*  
 Adresse einer **Punkt** Struktur, den Offset des Bildes ziehen Sie relativ zu der Ziehposition empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf den temporären Bilds, das die Liste der dient zum Ziehen; andernfalls **NULL**.  
  
##  <a name="getimagecount"></a>CImageList::GetImageCount  
 Rufen Sie diese Funktion, um die Anzahl der Bilder in einer Bildliste ab.  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bilder.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::ExtractIcon](#extracticon).  
  
##  <a name="getimageinfo"></a>CImageList::GetImageInfo  
 Rufen Sie diese Funktion zum Abrufen von Informationen zu einem Bild.  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds.  
  
 *pImageInfo*  
 Zeiger auf eine [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393) -Struktur, die Informationen zu dem Bild empfängt. Die Informationen in dieser Struktur kann verwendet werden, können Sie die Bitmaps für das Bild direkt zu bearbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `IMAGEINFO` Struktur enthält Informationen über ein Bild in einer Bildliste.  
  
##  <a name="getsafehandle"></a>CImageList::GetSafeHandle  
 Rufen Sie diese Funktion zum Abrufen der **M_hImageList** -Datenmember.  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle mit dem angefügten; andernfalls **NULL** , wenn kein Objekt zugeordnet ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#15;](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>CImageList::m_hImageList  
 Ein Handle, der diesem Objekt zugeordneten Bildliste.  
  
 **HIMAGELIST M_hImageList;**  
  
### <a name="remarks"></a>Hinweise  
 Die **M_hImageList** -Datenmember ist eine öffentliche Variable des Typs `HIMAGELIST`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&23;](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>CImageList::operator HIMAGELIST  
 Verwenden Sie diesen Operator das angefügte Handle der Abrufen der `CImageList` Objekt.  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für die Bildliste durch dargestellt die `CImageList` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Typumwandlungsoperator verwendet, die direkte Verwendung von unterstützt ein `HIMAGELIST` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList Nr.&16;](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>CImageList::Read  
 Rufen Sie diese Funktion zum Lesen einer Bildliste aus einem Archiv.  
  
```  
BOOL Read(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parameter  
 `pArchive`  
 Ein Zeiger auf ein `CArchive` -Objekt aus der Liste der Images gelesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&18;](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>CImageList::Remove  
 Rufen Sie diese Funktion, um ein Bild aus einem Image List-Objekt zu entfernen.  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des zu entfernenden Bildes.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente, die nach `nImage` jetzt eine Position nach unten zu verschieben. Z. B. wenn eine Bildliste zwei Elemente enthält, bewirkt löschen das erste Element den verbleibenden Artikel jetzt in der ersten Position sein. `nImage`=&0; für das Element in der ersten Position.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList Nr.&19;](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>CImageList::Replace  
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
 `nImage`  
 Nullbasierte Index des Bilds zu ersetzen.  
  
 `pbmImage`  
 Ein Zeiger auf die Bitmap, die das Bild enthält.  
  
 `pbmMask`  
 Ein Zeiger auf die Bitmap mit der Maske. Wenn keine Maske mit Liste der Images verwendet wird, wird dieser Parameter ignoriert.  
  
 `hIcon`  
 Ein Handle für das Symbol, das die Bitmap und die Maske für das neue Abbild enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version zurückgeben **BOOL** gibt einen Wert ungleich NULL zurück, wenn erfolgreich, andernfalls 0.  
  
 Die Version zurückgeben `int` gibt den nullbasierten Index des Bilds zurück, wenn erfolgreich, andernfalls – 1.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion nach dem Aufruf von [SetImageCount](#setimagecount) zum Zuweisen der neuen gültigen Bilder auf den Platzhalter Indexnummern Bild.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CImageList::SetImageCount](#setimagecount).  
  
##  <a name="setbkcolor"></a>CImageList::SetBkColor  
 Rufen Sie diese Funktion, um die Hintergrundfarbe einer Bildliste festgelegt.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Parameter  
 `cr`  
 Hintergrundfarbe festlegen. Es kann sein `CLR_NONE`. In diesem Fall werden die Bilder transparent mit der Maske gezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Hintergrundfarbe, wenn erfolgreich; andernfalls `CLR_NONE`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&20;](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>CImageList::SetDragCursorImage  
 Erstellt ein neues Bild mit Drag & durch Kombinieren des angegebenen Bilds (in der Regel ein Bild eines Mauscursors) mit dem aktuellen Drag-Image.  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parameter  
 *nDrag*  
 Index, der das neue Bild mit dem Bild kombiniert werden.  
  
 `ptHotSpot`  
 Die Position des Hotspots in das neue Bild.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Da die Funktionen zum Ziehen das neue Bild während eines Ziehvorgangs verwenden, sollten Sie verwenden Windows [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) Funktion, um den tatsächlichen Mauscursor nach dem Aufruf von ausblenden `CImageList::SetDragCursorImage`. Andernfalls kann das System angezeigt, für die Dauer des Ziehvorgangs zwei Mauscursor haben.  
  
##  <a name="setimagecount"></a>CImageList::SetImageCount  
 Rufen Sie diese Memberfunktion zum Zurücksetzen der Anzahl von Bildern in ein `CImageList` Objekt.  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>Parameter  
 *uNewCount*  
 Der Wert für die neue Gesamtzahl der Bilder in der Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Memberfunktion zum Erhöhen der Anzahl der Bilder in der Bildliste aufrufen, rufen Sie [ersetzen](#replace) für jedes weitere Bild gültigen Bilder die neuen Indizes zuweisen. Wenn Sie keine gültigen Bilder zuzuordnen, werden Draw-Vorgänge, die die neuen Bilder erstellen vorhersehbar.  
  
 Wenn Sie die Größe einer Bildliste verringern, indem Sie diese Funktion verwenden, werden die abgeschnittenen Bilder freigegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&21;](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>CImageList:: SetOverlayImage  
 Rufen Sie diese Funktion, um die Liste der Bilder als Overlaymasken verwendet den nullbasierten Index eines Bilds hinzugefügt.  
  
```  
BOOL SetOverlayImage(
    int nImage,  
    int nOverlay);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bildes, das als eine Überlagerung Maske verwenden.  
  
 *nOverlay*  
 1 basierende Index der Überlagerung Maske.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Liste können bis zu vier Indizes hinzugefügt werden.  
  
 Eine Overlaymaske ist ein Bild transparent über ein anderes Bild gezeichnet. Zeichnen Sie eine Überlagerung Maske über ein Bild mithilfe der [Memberfunktion CImageList:: Draw](#draw) Memberfunktion mit dem Index&1;-basierte der Überlagerung Maske mit angegeben der **INDEXTOOVERLAYMASK** Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&#22;](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>CImageList::Write  
 Rufen Sie diese Funktion, um ein Image List-Objekt in ein Archiv zu schreiben.  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parameter  
 `pArchive`  
 Ein Zeiger auf ein `CArchive` -Objekt in der Liste der Images gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CImageList&17;](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl-Klasse](../../mfc/reference/ctabctrl-class.md)

