---
title: CStatic Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
dev_langs: C++
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3319535bdcf3693fcf9427572e3902f96261d33e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cstatic-class"></a>CStatic-Klasse
Stellt die Funktionalität eines statischen Windows-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStatic : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatic::CStatic](#cstatic)|Erstellt ein `CStatic`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatic::Create](#create)|Die statischen Windows-Steuerelements erstellt und fügt es der `CStatic` Objekt.|  
|[CStatic::DrawItem](#drawitem)|Überschreiben Sie, um ein vom Besitzer gezeichnetes statisches Steuerelement gezeichnet werden soll.|  
|[CStatic::GetBitmap](#getbitmap)|Ruft das Handle der Bitmap für die zuvor festgelegten mit [SetBitmap](#setbitmap).|  
|[CStatic::GetCursor](#getcursor)|Ruft das Handle des Cursorbilds zuvor festgelegt wird, mit [SetCursor](#setcursor).|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Ruft das Handle der zuvor festgelegten mit EMF [SetEnhMetaFile](#setenhmetafile).|  
|[CStatic::GetIcon](#geticon)|Ruft das Handle des zuvor mit dem Symbol [SetIcon](#seticon).|  
|[CStatic::SetBitmap](#setbitmap)|Gibt eine Bitmap, die im statischen Steuerelement angezeigt werden.|  
|[CStatic::SetCursor](#setcursor)|Gibt einen Cursorbild statisches Steuerelement angezeigt werden.|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Gibt eine erweiterte Metadatei statisches Steuerelement angezeigt werden.|  
|[CStatic::SetIcon](#seticon)|Gibt ein Symbol, um in den statischen Steuerelement angezeigt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein statisches Steuerelement zeigt eine Textzeichenfolge, Feld, Rechteck, Symbol, Cursor, Bitmap oder erweiterte Metadatei. Es kann zu bezeichnen, Feld oder separat von anderen Steuerelementen verwendet werden. Ein statisches Steuerelement normalerweise akzeptiert keine Eingaben und stellt keine Ausgabe. Allerdings kann es übergeordneten Mausklicks benachrichtigen, wenn er mit erstellt wird **SS_NOTIFY** Stil.  
  
 Erstellen Sie ein statisches Steuerelement in zwei Schritten. Rufen Sie zunächst den Konstruktor zum Erstellen der `CStatic` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion statische Steuerelement erstellen, und fügen Sie es auf die `CStatic` Objekt.  
  
 Bei Erstellung einer `CStatic` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CStatic` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CStatic` Objekt innerhalb eines Fensters müssen Sie möglicherweise auch sie zerstört werden. Ein `CStatic` Objekt erstellt, auf dem Stapel in einem Fenster wird automatisch zerstört. Bei Erstellung der `CStatic` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das sie zerstört werden, wenn Sie damit fertig sind.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="create"></a>CStatic::Create  
 Die statischen Windows-Steuerelements erstellt und fügt es der `CStatic` Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszText,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID = 0xffff);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Gibt den Text im Steuerelement platziert. Wenn **NULL**, wird kein Text angezeigt werden.  
  
 `dwStyle`  
 Gibt die statisches Steuerelement Fensterstil. Wenden Sie eine beliebige Kombination von [Steuerelementtypen für die statische](../../mfc/reference/styles-used-by-mfc.md#static-styles) an das Steuerelement.  
  
 `rect`  
 Gibt die Position und Größe des statischen Steuerelements an. Es kann es sich um eine `RECT` Struktur oder ein `CRect` Objekt.  
  
 `pParentWnd`  
 Gibt an, die `CStatic` übergeordnetes Fenster, in der Regel eine `CDialog` Objekt. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt an, die statisches Steuerelement Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CStatic` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor `CStatic`, und rufen Sie anschließend **erstellen**, der den statischen Windows-Steuerelements erstellt und fügt es der `CStatic` Objekt.  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) zu einem statischen Steuerelement:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
 Wenn Sie eine Bitmap, Cursor, Symbol oder Metadatei im statischen Steuerelement anzeigen möchten, müssen Sie eine der folgenden Bedingungen erfüllt sein [statische Stile](../../mfc/reference/styles-used-by-mfc.md#static-styles):  
  
- **SS_BITMAP** verwenden Sie dieses Format für Bitmaps.  
  
- **SS_ICON** verwenden Sie dieses Format für Cursor und Symbole.  
  
- **SS_ENHMETAFILE** verwenden Sie dieses Format für Metadateien.  
  
 Für Cursor, Bitmaps oder Symbole sollten Sie auch das folgende Format verwenden:  
  
- **SS_CENTERIMAGE** verwenden, um das Bild im statischen Steuerelement zu zentrieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>CStatic::CStatic  
 Erstellt ein `CStatic`-Objekt.  
  
```  
CStatic();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>CStatic::DrawItem  
 Wird aufgerufen, durch das Framework ein vom Besitzer gezeichnetes statisches Steuerelement gezeichnet werden soll.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) Struktur. Die Struktur enthält Informationen über das Element gezeichnet werden und den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Implementieren der Zeichnung für ein vom Besitzer gezeichnetes **CStatic** Objekt (das Steuerelement hat das Format **SS_OWNERDRAW**).  
  
##  <a name="getbitmap"></a>CStatic::GetBitmap  
 Ruft das Handle für die Bitmap, die zuvor festgelegten mit [SetBitmap](#setbitmap), d. h. zugeordneten `CStatic`.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die aktuelle Bitmap oder **NULL** , wenn keine Bitmap festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>CStatic::GetCursor  
 Ruft das Handle des Cursors, der zuvor festgelegten mit [SetCursor](#setcursor), d. h. zugeordneten `CStatic`.  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den aktuellen Cursor oder **NULL** Wenn kein Cursor festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>CStatic::GetEnhMetaFile  
 Ruft das Handle der zuvor festgelegten mit EMF [SetEnhMetafile](#setenhmetafile), d. h. zugeordneten `CStatic`.  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die aktuelle erweiterte Metadatei oder **NULL** , wenn keine EMF festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>CStatic::GetIcon  
 Ruft das Handle des Symbols, mit bereits festgelegten [SetIcon](#seticon), d. h. zugeordneten `CStatic`.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das aktuelle Symbol oder **NULL** Wenn Symbol "keine" festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>CStatic::SetBitmap  
 Ordnet die statisches Steuerelement eine neue Bitmapdatei hinzu.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `hBitmap`  
 Handle der Bitmap, in der statisches Steuerelement gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Bitmap, die zuvor mit dem statischen Steuerelement verknüpft wurde oder `NULL` war keine Bitmap statisches Steuerelement zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap wird automatisch in die statisches Steuerelement gezeichnet werden soll. Standardmäßig wird Sie in der oberen linken Ecke gezeichnet werden und statische Steuerelement wird auf die Größe der Bitmap für die Größe geändert werden.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen, einschließlich:  
  
-   SS_BITMAP verwenden Sie dieses Format immer für Bitmaps.  
  
-   SS_CENTERIMAGE verwenden, um das Bild im statischen Steuerelement zu zentrieren. Wenn das Bild größer als statisches Steuerelement ist, wird er abgeschnitten. Wenn er kleiner als statisches Steuerelement ist, wird der freie Speicherplatz, um das Bild durch die Farbe des Pixels in der oberen linken Ecke der Bitmap ausgefüllt.  
  
-   MFC stellt die Klasse `CBitmap`, die Sie verwenden können, wenn Sie mehr mit einem Bitmapbild als rufen einfach die Win32-Funktion keine `LoadBitmap`. `CBitmap`, der einen Art von GDI-Objekt enthält wird häufig in Zusammenarbeit mit `CStatic`, also eine `CWnd` -Klasse, die für das Anzeigen eines Grafikobjekts als ein statisches Steuerelement verwendet wird.  
  
 `CImage`ist eine ATL/MFC-Klasse, die Sie leicht mit dem Gerät unabhängig Bitmaps (DIB) arbeiten kann. Weitere Informationen finden Sie unter [CImage-Klasse](../../atl-mfc-shared/reference/cimage-class.md).  
  
-   Typische Verwendung ist, geben Sie `CStatic::SetBitmap` ein GDI-Objekt, das durch den HBITMAP-Operator, der zurückgegeben wird ein `CBitmap` oder `CImage` Objekt. Der Code dazu ähnelt die folgende Zeile.  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
Das folgende Beispiel erstellt zwei `CStatic` Objekte im Heap. Daraufhin lädt er eine mithilfe einer Bitmap `CBitmap::LoadOEMBitmap` und die andere aus einer Datei mit `CImage::Load`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>CStatic::SetCursor  
 Ordnet ein neues Image der Cursor mit dem statischen Steuerelement.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Parameter  
 `hCursor`  
 Handle des Cursors im statischen Steuerelement gezeichnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Cursors, der zuvor mit dem statischen Steuerelement zugeordnet oder **NULL** war kein Cursor statisches Steuerelement zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Der Cursor wird automatisch in die statisches Steuerelement gezeichnet werden soll. Standardmäßig in der oberen linken Ecke gezeichnet wird, und die statische Steuerelement wird auf die Größe des Cursors geändert werden.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen, u. a. folgende:  
  
- **SS_ICON** verwenden Sie dieses Format immer für Cursor und Symbole.  
  
- **SS_CENTERIMAGE** verwenden, um im statischen Steuerelement zu zentrieren. Wenn das Bild größer als statisches Steuerelement ist, wird er abgeschnitten. Wenn er kleiner als statisches Steuerelement ist, wird der freie Speicherplatz, um das Bild mit die Hintergrundfarbe des Steuerelements statische ausgefüllt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>CStatic::SetEnhMetaFile  
 Ordnet dem statischen Steuerelement ein neues EMF-Bild zu.  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>Parameter  
 `hMetaFile`  
 Das Handle des EMF im statischen Steuerelement gezeichnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für die erweiterte Metadatei, die zuvor mit dem statischen Steuerelement zugeordnet oder **NULL** war keine EMF statisches Steuerelement zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Erweiterte Metadatei wird automatisch in statisches Steuerelement gezeichnet werden soll. Erweiterte Metadatei wird skaliert, die Größe des statischen Steuerelements an.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen, u. a. folgende:  
  
- **SS_ENHMETAFILE** verwenden Sie dieses Format immer für Metadateien.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>CStatic::SetIcon  
 Ordnet ein neuen Symbolbild statisches Steuerelement.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Handle des Symbols im statischen Steuerelement gezeichnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das zuvor statisches Steuerelement zugeordnete Symbol oder **NULL** war kein Symbol statisches Steuerelement zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Das Symbol wird automatisch in die statisches Steuerelement gezeichnet werden soll. Standardmäßig in der oberen linken Ecke gezeichnet wird, und wird die Größe der statische Steuerelement geändert, auf die Größe des Symbols.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen, u. a. folgende:  
  
- **SS_ICON** verwenden Sie dieses Format immer für Cursor und Symbole.  
  
- **SS_CENTERIMAGE** verwenden, um im statischen Steuerelement zu zentrieren. Wenn das Bild größer als statisches Steuerelement ist, wird er abgeschnitten. Wenn er kleiner als statisches Steuerelement ist, wird der freie Speicherplatz, um das Bild mit die Hintergrundfarbe des Steuerelements statische ausgefüllt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)
