---
title: Klasse CStatic | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- enhanced metafiles
- cursors, displaying
- static controls
- controls [MFC], static
- icons, displaying
- CStatic class
- enhanced metafiles, displaying
- bitmaps, displaying
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0209fad1b84b782cdec7927cb5a04e9bb3083d64
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cstatic-class"></a>CStatic-Klasse
Stellt die Funktionalität eines statischen Windows-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStatic : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatic::CStatic](#cstatic)|Erstellt ein `CStatic`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatic::Create](#create)|Erstellt die statischen Windows-Steuerelements, und fügt es der `CStatic` Objekt.|  
|[CStatic::DrawItem](#drawitem)|Überschreiben Sie, um ein statisches Ownerdrawn-Schaltflächen-Steuerelement zu zeichnen.|  
|[CStatic::GetBitmap](#getbitmap)|Ruft das Handle der Bitmap für die zuvor festgelegten mit [SetBitmap](#setbitmap).|  
|[CStatic::GetCursor](#getcursor)|Ruft das Handle des Cursorbilds zuvor mit festgelegten [SetCursor](#setcursor).|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Ruft das Handle der zuvor festgelegten mit EMF [SetEnhMetaFile](#setenhmetafile).|  
|[CStatic::GetIcon](#geticon)|Ruft das Handle des zuvor mit dem Symbol [SetIcon](#seticon).|  
|[CStatic::SetBitmap](#setbitmap)|Gibt eine Bitmap in statischen Steuerelements angezeigt werden.|  
|[CStatic::SetCursor](#setcursor)|Gibt ein Cursorbild im statischen Steuerelements angezeigt werden.|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Gibt eine erweiterte Metadatei im statischen Steuerelements angezeigt werden.|  
|[CStatic::SetIcon](#seticon)|Gibt ein Symbol in der statischen Steuerelements angezeigt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein statisches Steuerelement zeigt eine Textzeichenfolge, Feld, Rechteck, Symbol, Cursor, Bitmap oder erweiterte Metadatei. Es kann verwendet werden, zu bezeichnen, Feld oder andere Steuerelemente zu trennen. Ein statisches Steuerelement ist normalerweise keine Eingabe erfordert und bietet keine Ausgabe; Allerdings kann es übergeordneten Mausklicks benachrichtigen, wenn die Erstellung mit **SS_NOTIFY** Stil.  
  
 Erstellen Sie ein statisches Steuerelement in zwei Schritten. Zunächst rufen Sie den Konstruktor zum Erstellen der `CStatic` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion statische Steuerelement erstellen und diese an die `CStatic` Objekt.  
  
 Bei der Erstellung einer `CStatic` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CStatic` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CStatic` -Objekt innerhalb eines Fensters müssen Sie möglicherweise auch zerstört. Ein `CStatic` -Objekt erstellt, auf dem Stapel in einem Fenster wird automatisch gelöscht. Bei der Erstellung der `CStatic` Objekt auf dem Heap mithilfe der **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn Sie damit fertig sind.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="create"></a>CStatic::Create  
 Erstellt die statischen Windows-Steuerelements, und fügt es der `CStatic` Objekt.  
  
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
 Gibt die statisches Steuerelement Fensterstil. Wenden Sie eine beliebige Kombination von [Steuerelementtypen für die statische](../../mfc/reference/static-styles.md) an das Steuerelement.  
  
 `rect`  
 Gibt die Position und Größe des statischen Steuerelements an. Es kann entweder eine `RECT` Struktur oder ein `CRect` Objekt.  
  
 `pParentWnd`  
 Gibt die `CStatic` übergeordneten Fensters, in der Regel ein `CDialog` Objekt. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt die statisches Steuerelement Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CStatic` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor `CStatic`, und rufen Sie dann **erstellen**, die der statischen Windows-Steuerelements erstellt und fügt es der `CStatic` Objekt.  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) auf ein statisches Steuerelement:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
 Wenn man eine Bitmap, Cursor, Symbol oder Metadatei in statischen Steuerelements anzuzeigen, müssen Sie eine der folgenden anwenden [statische Stile](../../mfc/reference/static-styles.md):  
  
- **SS_BITMAP** verwenden Sie diesen Stil für Bitmaps.  
  
- **SS_ICON** verwenden Sie diesen Stil für Cursor und Symbole.  
  
- **SS_ENHMETAFILE** verwenden Sie diesen Stil für Metadateien.  
  
 Für Cursor, Bitmaps und Symbole sollten Sie auch das folgende Format verwenden:  
  
- **SS_CENTERIMAGE** verwenden, um das Bild im Steuerelement statisch zu zentrieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&#1;](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>CStatic::CStatic  
 Erstellt ein `CStatic`-Objekt.  
  
```  
CStatic();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&#2;](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>CStatic::DrawItem  
 Aufgerufen, um ein statisches Ownerdrawn-Schaltflächen-Steuerelement zu zeichnen.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) Struktur. Die Struktur enthält Informationen über das Element gezeichnet werden und den Typ der Zeichnung, die erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Implementieren der Zeichnung für eine Ownerdrawn- **CStatic** Objekt (das Steuerelement hat das Format **SS_OWNERDRAW**).  
  
##  <a name="getbitmap"></a>CStatic::GetBitmap  
 Ruft das Handle der Bitmap mit zuvor festgelegten [SetBitmap](#setbitmap), d. h. zugeordnete `CStatic`.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die aktuelle Bitmap oder **NULL** , wenn keine Bitmap festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>CStatic::GetCursor  
 Ruft das Handle des Cursors mit zuvor festgelegten [SetCursor](#setcursor), d. h. zugeordnete `CStatic`.  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den aktuellen Cursor oder **NULL** , wenn kein Cursor festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>CStatic::GetEnhMetaFile  
 Ruft das Handle des EMF mit zuvor festgelegten [SetEnhMetafile](#setenhmetafile), d. h. zugeordnete `CStatic`.  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die aktuelle erweiterte Metadatei oder **NULL** , wenn keine EMF festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>CStatic::GetIcon  
 Ruft das Handle des Symbols, mit zuvor festgelegten [SetIcon](#seticon), d. h. zugeordnete `CStatic`.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol mit der aktuellen oder **NULL** , wenn kein Symbol festgelegt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>CStatic::SetBitmap  
 Ordnet eine neue Bitmap statisches Steuerelement.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `hBitmap`  
 Handle der Bitmap, die in statischen Steuerelements gezeichnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Bitmap, die zuvor mit der statischen Steuerelements verknüpft wurde oder `NULL` Wenn keine Bitmap statisches Steuerelement zugeordnet war.  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap wird automatisch in statischen Steuerelements gezeichnet werden soll. Standardmäßig in der oberen linken Ecke gezeichnet wird, und wird die Größe der statische Steuerelement geändert, um die Größe der Bitmap.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen einbeziehen dieser verwenden:  
  
-   SS_BITMAP verwenden Sie diesen Stil für Bitmaps für immer.  
  
-   SS_CENTERIMAGE verwenden das Bild im statischen Steuerelement zentriert. Wenn das Bild größer als das Steuerelement statisch ist, wird es abgeschnitten. Wenn er kleiner als statisches Steuerelement ist, wird der freie Speicherplatz, um das Bild durch die Farbe des Pixels in der oberen linken Ecke der Bitmap ausgefüllt werden.  
  
-   MFC stellt die Klasse `CBitmap`, die Sie verwenden können, wenn Sie mehr mit einer Bitmap als rufen Sie einfach die Win32 funktionieren `LoadBitmap`. `CBitmap`, eine Art von GDI-Objekt enthält wird häufig in Zusammenarbeit mit `CStatic`, also eine `CWnd` -Klasse, die für die Anzeige eines Grafikobjekts als ein statisches Steuerelement verwendet wird.  
  
 `CImage`ist eine ATL-/MFC-Klasse, die Sie leicht mit Device-independent Bitmaps (DIBs) arbeiten kann. Weitere Informationen finden Sie unter [CImage-Klasse](../../atl-mfc-shared/reference/cimage-class.md).  
  
-   Regel wird für ein `CStatic::SetBitmap` ein GDI-Objekt, das von der HBITMAP-Operator, der zurückgegeben wird ein `CBitmap` oder `CImage` Objekt. Der Code hierfür ähnelt die folgende Zeile.  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
Das folgende Beispiel erstellt zwei `CStatic` Objekte auf dem Heap. Daraufhin lädt er eine mithilfe einer Bitmap `CBitmap::LoadOEMBitmap` und andere aus einer Datei mit `CImage::Load`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>CStatic::SetCursor  
 Ordnet ein neues Abbild der Cursor des statischen Steuerelements.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Parameter  
 `hCursor`  
 Handle des Cursors im statischen Steuerelement gezeichnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Cursors, der zuvor die statisches Steuerelement zugeordnet oder **NULL** wurde kein Cursor statisches Steuerelement zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Der Cursor wird automatisch in statischen Steuerelements gezeichnet werden soll. Standardmäßig in der oberen linken Ecke gezeichnet wird, und des statischen Steuerelements wird auf die Größe des Cursors geändert werden.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen, einschließlich der folgenden verwenden:  
  
- **SS_ICON** verwenden Sie dieses Format immer für den Cursor und Symbole.  
  
- **SS_CENTERIMAGE** verwenden, um im statischen Steuerelements zu zentrieren. Wenn das Bild größer als das Steuerelement statisch ist, wird es abgeschnitten. Wenn er kleiner als statisches Steuerelement ist, wird der Leerraum um das Bild mit der Hintergrundfarbe des statischen Steuerelements ausgefüllt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>CStatic::SetEnhMetaFile  
 Ordnet ein neues EMF-Bild statisches Steuerelement.  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>Parameter  
 `hMetaFile`  
 Das Handle des EMF im statischen Steuerelement gezeichnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für die erweiterte Metadatei, die zuvor mit dem statischen-Steuerelement zugeordnet oder **NULL** Wenn keine EMF statisches Steuerelement zugeordnet war.  
  
### <a name="remarks"></a>Hinweise  
 Erweiterte Metadatei wird automatisch in statisches Steuerelement gezeichnet werden soll. Erweiterte Metadatei wird skaliert, um die Größe des statischen Steuerelements an.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen, einschließlich der folgenden verwenden:  
  
- **SS_ENHMETAFILE** verwenden Sie dieses Format immer für Metadateien.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>CStatic::SetIcon  
 Ordnet ein neues Symbolbild statisches Steuerelement.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Handle für das Symbol in der statisches Steuerelement gezeichnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das zuvor die statisches Steuerelement zugeordnete Symbol oder **NULL** Wenn kein Symbol statisches Steuerelement zugeordnet war.  
  
### <a name="remarks"></a>Hinweise  
 Das Symbol wird automatisch in statischen Steuerelements gezeichnet werden soll. Standardmäßig in der oberen linken Ecke gezeichnet wird, und wird die Größe der statische Steuerelement geändert, um die Größe des Symbols.  
  
 Sie können verschiedene Fenster und statische Steuerelementtypen, einschließlich der folgenden verwenden:  
  
- **SS_ICON** verwenden Sie dieses Format immer für den Cursor und Symbole.  
  
- **SS_CENTERIMAGE** verwenden, um im statischen Steuerelements zu zentrieren. Wenn das Bild größer als das Steuerelement statisch ist, wird es abgeschnitten. Wenn er kleiner als statisches Steuerelement ist, wird der Leerraum um das Bild mit der Hintergrundfarbe des statischen Steuerelements ausgefüllt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatic&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
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

