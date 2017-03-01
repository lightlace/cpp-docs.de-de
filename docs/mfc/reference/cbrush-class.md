---
title: CBrush-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBrush
dev_langs:
- C++
helpviewer_keywords:
- brushes, CBrush class
- CBrush class
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: efcbe2757de3a7e4621e2b20c88726ead111cf8c
ms.lasthandoff: 02/24/2017

---
# <a name="cbrush-class"></a>CBrush-Klasse
Kapselt einen Pinsel der Windows GDI (Graphics Device Interface).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|Erstellt ein `CBrush`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Initialisiert einen Pinsel mit der Formatvorlage, Farbe und Muster im angegebenen ein [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur.|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Initialisiert einen Pinsel mit einem Muster, die durch eine geräteunabhängige Bitmap (DIB) angegeben.|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|Initialisiert einen Pinsel mit der angegebenen Schraffur und Farbe.|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|Initialisiert einen Pinsel mit einem Muster, die durch eine Bitmap angegeben.|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|Initialisiert einen Pinsel mit der angegebenen Volltonfarbe aus.|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Erstellt einen Pinsel, der die Standardsystemfarbe ist.|  
|[CBrush::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CBrush` Objekt, wenn ein Handle zu einem Windows angegebenen `HBRUSH` Objekt.|  
|[CBrush::GetLogBrush](#getlogbrush)|Ruft eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](#operator_hbrush)|Gibt das Windows-Handle an der der `CBrush` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CBrush` Objekt, das Erstellen einer `CBrush` -Objekt und übergeben es an `CDC` Memberfunktion, die einen Pinsel erfordert.  
  
 Pinsel können durchgezogen, ausgebrütet oder strukturiert sein.  
  
 Weitere Informationen zu `CBrush`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecbrusha--cbrushcbrush"></a><a name="cbrush"></a>CBrush::CBrush  
 Erstellt ein `CBrush`-Objekt.  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die Vordergrundfarbe des Pinsels als eine RGB-Farbe. Wenn der Pinsel eingestellt ist, gibt dieser Parameter die Farbe der Schraffur.  
  
 `nIndex`  
 Gibt die Schraffurart des Pinsels. Einer der folgenden Werte sind möglich:  
  
- `HS_BDIAGONAL`Nach unten Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_CROSS`Horizontale und vertikale Schraffur  
  
- `HS_DIAGCROSS`Kreuzschraffur auf 45 Grad  
  
- `HS_FDIAGONAL`Nach oben Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_HORIZONTAL`Horizontale Schraffur  
  
- `HS_VERTICAL`Vertikale schraffierte  
  
 `pBitmap`  
 Verweist auf ein `CBitmap` Objekt, das eine Bitmap angibt, mit der der Pinsel zeichnet.  
  
### <a name="remarks"></a>Hinweise  
 `CBrush`verfügt über vier Konstruktoren überladen. Der Konstruktor ohne Argumente erstellt ein nicht initialisiertes `CBrush` -Objekt, das initialisiert werden muss, bevor es verwendet werden kann.  
  
 Wenn Sie den Konstruktor ohne Argumente verwenden, müssen Sie das resultierende initialisieren `CBrush` -Objekt mit [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), oder [CreateDIBPatternBrush](#createdibpatternbrush). Wenn Sie einen der Konstruktoren, die Argumente verwenden, ist keine weitere Initialisierung erforderlich. Die Konstruktoren mit Argumenten können eine Ausnahme auslösen, wenn Fehler aufgetreten sind, während der Konstruktor ohne Argumente immer erfolgreich verläuft.  
  
 Der Konstruktor mit einem einzigen [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Parameter erstellt einen Pinsel mit Volltonfarbe mit der angegebenen Farbe. Die Farbe Gibt einen RGB-Wert und kann erstellt werden, mit der `RGB` Makro in WINDOWS. H.  
  
 Der Konstruktor mit zwei Parametern konstruiert ein Schraffurpinsel. Die `nIndex` Parameter gibt den Index einer Schraffur. Die `crColor` Parameter gibt die Farbe an.  
  
 Der Konstruktor mit einem `CBitmap` Parameter einen Pinsel erstellt. Eine Bitmap identifiziert. Wird angenommen, dass die Bitmap erstellt wurden, indem Sie mithilfe von [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), oder [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). Die minimale Größe für eine Bitmap in einem Füllmuster verwendet werden, ist 8 x 8 Pixel.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&21;](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="a-namecreatebrushindirecta--cbrushcreatebrushindirect"></a><a name="createbrushindirect"></a>CBrush::CreateBrushIndirect  
 Initialisiert einen Pinsel mit einer Formatvorlage, Farbe und Muster im angegebenen ein [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur.  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>Parameter  
 *lpLogBrush*  
 Verweist auf eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) -Struktur, die Informationen zu den Pinsel enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend als den aktuellen Pinsel für alle Gerätekontext ausgewählt werden.  
  
 Ein Pinsel mit einer Bitmap Monochrom (1-Ebene, 1 Bit pro Pixel) erstellt wird unter Verwendung der aktuellen Text- und Hintergrundfarben gezeichnet. Pixel dargestellt, indem ein Bit auf 0 festgelegt werden mit der aktuellen Farbe gezeichnet werden. Pixel dargestellt, indem ein Bit auf 1 festgelegt, werden mit der aktuellen Hintergrundfarbe gezeichnet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#22;](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="a-namecreatedibpatternbrusha--cbrushcreatedibpatternbrush"></a><a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush  
 Initialisiert einen Pinsel mit dem Muster durch eine geräteunabhängige Bitmap (DIB) angegeben.  
  
```  
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,  
    UINT nUsage);

 
BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,  
    UINT nUsage);
```  
  
### <a name="parameters"></a>Parameter  
 *hPackedDIB*  
 Identifiziert einen globalen Arbeitsspeicher-Objekt enthält eine gepackte geräteunabhängige Bitmap (DIB).  
  
 *nUsage*  
 Gibt an, ob die **BmiColors []** Felder von der [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) explizite RGB-Werte oder Indizes Datenstruktur (ein Teil von "verpackt die DIB") enthalten, in der derzeit realisierten logische Palette. Der Parameter muss einen der folgenden Werte sein:  
  
- **DIB_PAL_COLORS** die Farbtabelle besteht aus einem Array von 16-Bit-Indizes.  
  
- **DIB_RGB_COLORS** die Farbtabelle Literale RGB-Werte enthält.  
  
 *lpPackedDIB*  
 Verweist auf eine gepackte DIB bestehend aus einem `BITMAPINFO` Struktur unmittelbar gefolgt von einem Array von Bytes, die die Pixel der Bitmap definieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend für alle Gerätekontext ausgewählt werden, die Raster-Vorgänge unterstützt.  
  
 Die beiden Versionen unterscheiden sich in der, wie Sie die DIB behandelt:  
  
-   In der ersten Version, um ein Handle für die DIB-Datei erhalten Sie Windows aufrufen **GlobalAlloc** Funktion zum Reservieren eines globalen Arbeitsspeicher, und geben Sie den Speicher mit der gepackten DIB.  
  
-   In der zweiten Version, ist es nicht notwendig, rufen Sie **GlobalAlloc** gepackte DIB Arbeitsspeicher zugeordnet werden.  
  
 Eine gepackte DIB besteht aus einem `BITMAPINFO` -Datenstruktur, die unmittelbar nach der das Bytearray, das die Pixel der Bitmap definiert. Bitmaps, die als Füllung Muster sollte 8 x 8 Pixel. Wenn die Bitmap größer ist, erstellt Windows eine Füllmusters verwenden nur die Bits, die für die ersten 8 Zeilen und Spalten 8 Pixel in der oberen linken Ecke der Bitmap.  
  
 Wenn eine Anwendung einen Pinsel mit zwei Farben DIB Muster eine monochrome Gerätekontext auswählt, wird Windows in DIB angegebenen Farben ignoriert und stattdessen zeigt den Musterpinsel mit der aktuellen Text- und Hintergrundfarben des Gerätekontexts. Pixel, die der ersten Farbe (beim Offset 0 in der Farbtabelle der DIB) der DIB-Datei zugeordnet werden mithilfe von die Farbe des Texts angezeigt. Pixeln der zweiten Farbe (beim Offset 1 in der Tabelle) zugeordnet werden, mit der Hintergrundfarbe angezeigt.  
  
 Informationen zum Verwenden der folgenden Windows-Funktionen finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:  
  
- [CreateDIBPatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183492) (diese Funktion wird bereitgestellt, um Kompatibilität mit Anwendungen für Windows-Versionen vor 3.0; verwenden Sie die **CreateDIBPatternBrushPt** Funktion.)  
  
- [CreateDIBPatternBrushPt](http://msdn.microsoft.com/library/windows/desktop/dd183493) (diese Funktion sollte für Win32-basierte Anwendung verwendet werden.)  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&23;](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="a-namecreatehatchbrusha--cbrushcreatehatchbrush"></a><a name="createhatchbrush"></a>CBrush::CreateHatchBrush  
 Initialisiert einen Pinsel mit der angegebenen Schraffur und Farbe.  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt die Schraffurart des Pinsels. Einer der folgenden Werte sind möglich:  
  
- `HS_BDIAGONAL`Nach unten Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_CROSS`Horizontale und vertikale Schraffur  
  
- `HS_DIAGCROSS`Kreuzschraffur auf 45 Grad  
  
- `HS_FDIAGONAL`Nach oben Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_HORIZONTAL`Horizontale Schraffur  
  
- `HS_VERTICAL`Vertikale schraffierte  
  
 `crColor`  
 Gibt die Vordergrundfarbe des Pinsels als eine RGB-Farbe (die Farbe der Schraffuren). Finden Sie unter [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend als den aktuellen Pinsel für alle Gerätekontext ausgewählt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#24;](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="a-namecreatepatternbrusha--cbrushcreatepatternbrush"></a><a name="createpatternbrush"></a>CBrush::CreatePatternBrush  
 Initialisiert einen Pinsel mit einem Muster, die durch eine Bitmap angegeben.  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmap`  
 Identifiziert eine Bitmap.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend für alle Gerätekontext ausgewählt werden, die Raster-Vorgänge unterstützt. Die Bitmap identifizierten `pBitmap` wird in der Regel mit initialisiert die [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), oder [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) Funktion.  
  
 Bitmaps, die als Füllung Muster sollte 8 x 8 Pixel. Wenn die Bitmap größer ist, verwendet Windows nur die Bits für die ersten 8 Zeilen und Spalten der Pixel in der oberen linken Ecke der Bitmap.  
  
 Ein Musterpinsel kann ohne Auswirkung auf die verknüpfte Bitmap gelöscht werden. Dies bedeutet, dass die Bitmap verwendet werden kann, um eine beliebige Anzahl von Musterpinsel zu erstellen.  
  
 Ein Pinsel mit eine monochrome Bitmap (Ebene 1 Farbe und 1 Bit pro Pixel) erstellt wird unter Verwendung der aktuellen Text- und Hintergrundfarben gezeichnet. Pixel dargestellt, indem ein Bit auf 0 festgelegt, werden mit der aktuellen Farbe gezeichnet. Pixel dargestellt, indem ein Bit auf 1 festgelegt, die mit der aktuellen Hintergrundfarbe gezeichnet werden.  
  
 Informationen zur Verwendung [CreatePatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183508), einer Windows-Funktion finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#25;](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="a-namecreatesolidbrusha--cbrushcreatesolidbrush"></a><a name="createsolidbrush"></a>CBrush::CreateSolidBrush  
 Initialisiert einen Pinsel mit Volltonfarbe angegebenen.  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Struktur, die Farbe des Pinsels angibt. Die Farbe Gibt einen RGB-Wert und kann erstellt werden, mit der `RGB` Makro in WINDOWS. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend als den aktuellen Pinsel für alle Gerätekontext ausgewählt werden.  
  
 Wenn eine Anwendung hat mit dem Pinsel erstellt, indem `CreateSolidBrush`, sollten sie den Pinsel aus den Gerätekontext auszuwählen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CBrush::CBrush](#cbrush).  
  
##  <a name="a-namecreatesyscolorbrusha--cbrushcreatesyscolorbrush"></a><a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush  
 Initialisiert eine Pinselfarbe.  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den Index einer Farbe. Dieser Wert entspricht der Farbe verwendet, um eines der Fensterelemente 21 zeichnen. Finden Sie unter [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend als den aktuellen Pinsel für alle Gerätekontext ausgewählt werden.  
  
 Wenn eine Anwendung hat mit dem Pinsel erstellt, indem `CreateSysColorBrush`, sollten sie den Pinsel aus den Gerätekontext auszuwählen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#26;](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="a-namefromhandlea--cbrushfromhandle"></a><a name="fromhandle"></a>CBrush::FromHandle  
 Gibt einen Zeiger auf eine `CBrush` Objekt, wenn ein Handle zu einem Windows angegebenen [HBRUSH](#operator_hbrush) Objekt.  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `hBrush`  
 `HANDLE`Um ein Windows-GDI-Pinsel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CBrush` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CBrush` Objekt noch nicht angefügt, das Handle zu einem temporären `CBrush` Objekt erstellt und angefügt wird. Dieser temporäre `CBrush` Objekt ist gültig, bis das nächste Mal die Anwendung hat die Leerlaufzeit in seiner Ereignisschleife. Zu diesem Zeitpunkt werden alle temporären Grafikobjekte gelöscht. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht ein Fenster gültig.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CBrush::CBrush](#cbrush).  
  
##  <a name="a-namegetlogbrusha--cbrushgetlogbrush"></a><a name="getlogbrush"></a>CBrush::GetLogBrush  
 Rufen Sie diese Memberfunktion zum Abrufen der `LOGBRUSH` Struktur.  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `pLogBrush`  
 Verweist auf eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) -Struktur, die Informationen zu den Pinsel enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, und `pLogBrush` gültiger Zeiger ist, ist der Rückgabewert ist die Anzahl der Bytes im Puffer gespeichert.  
  
 Wenn die Funktion erfolgreich ausgeführt wird, und `pLogBrush` ist **NULL**, der Rückgabewert ist die Anzahl der Bytes, die zum Speichern der Informationen der Funktion in den Puffer speichern.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `LOGBRUSH` Struktur definiert die Formatvorlage, Farbe und Muster eines Pinsels.  
  
 Rufen Sie z. B. `GetLogBrush` mit der bestimmte Farbe oder eine Bitmap-Muster übereinstimmen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#27;](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="a-nameoperatorhbrusha--cbrushoperator-hbrush"></a><a name="operator_hbrush"></a>CBrush::operator HBRUSH  
 Verwenden Sie diesen Operator zum Abrufen der angefügten Windows GDI-Handle für die `CBrush` Objekt.  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CBrush` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Typumwandlungsoperator verwendet, die direkte Verwendung von unterstützt ein `HBRUSH` Objekt.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#28;](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel PROPDLG](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBitmap-Klasse](../../mfc/reference/cbitmap-class.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)

