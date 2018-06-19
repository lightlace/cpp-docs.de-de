---
title: CBrush-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
dev_langs:
- C++
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39c5167c81d6c44fa62f9bff87c6c04f73f9f6d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355888"
---
# <a name="cbrush-class"></a>CBrush-Klasse
Kapselt einen Pinsel der Windows GDI (Graphics Device Interface).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|Erstellt ein `CBrush`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Initialisiert einen Pinsel mit der Formatvorlage, die Farbe und die Muster im angegebenen eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur.|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Initialisiert einen Pinsel mit einem Muster, die durch eine geräteunabhängige Bitmap (DIB) angegeben.|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|Initialisiert einen Pinsel mit dem angegebenen Schraffur und die Farbe an.|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|Initialisiert einen Pinsel mit einem Muster, die durch eine Bitmap angegeben.|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|Initialisiert einen Pinsel mit der angegebenen Volltonfarbe aus.|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Erstellt einen Pinsel, der die Standardsystemfarbe ist.|  
|[CBrush::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CBrush` Objekt, wenn ein Handle zu einem Windows vorhanden `HBRUSH` Objekt.|  
|[CBrush::GetLogBrush](#getlogbrush)|Ruft eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](#operator_hbrush)|Gibt die Windows-Handle an der die `CBrush` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CBrush` Objekt, das Erstellen einer `CBrush` -Objekt und übergibt ihn dann an alle `CDC` Memberfunktion, die einen Pinsel erfordert.  
  
 Pinsel können eingestellt oder gemusterten durchgezogen, sein.  
  
 Weitere Informationen zu `CBrush`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cbrush"></a>  CBrush::CBrush  
 Erstellt ein `CBrush`-Objekt.  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die Vordergrundfarbe des Pinsels als RGB-Farbe. Wenn der Pinsel eingestellt ist, gibt dieser Parameter die Farbe der Schraffur an.  
  
 `nIndex`  
 Gibt die Schraffurart des Pinsels. Eine der folgenden Werte sind möglich:  
  
- `HS_BDIAGONAL` Nach unten weisenden Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_CROSS` Horizontale und vertikale Schraffur  
  
- `HS_DIAGCROSS` Kreuzschraffur 45 Grad  
  
- `HS_FDIAGONAL` Nach oben Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_HORIZONTAL` Horizontale Schraffur  
  
- `HS_VERTICAL` Vertikale Schraffur  
  
 `pBitmap`  
 Verweist auf ein `CBitmap` Objekt, das eine Bitmap angibt, mit denen die Pinsel zeichnet.  
  
### <a name="remarks"></a>Hinweise  
 `CBrush` verfügt über vier Konstruktoren überladen. Der Konstruktor ohne Argumente erstellt eine nicht initialisierte `CBrush` -Objekt, das initialisiert werden muss, bevor er verwendet werden kann.  
  
 Wenn Sie den Konstruktor ohne Argumente verwenden, müssen Sie initialisieren, das resultierende `CBrush` -Objekt mit [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), oder [CreateDIBPatternBrush](#createdibpatternbrush). Bei Verwendung eines Konstruktors, die Argumente akzeptiert, ist keine weitere Initialisierung erforderlich. Die Konstruktoren mit Argumenten können Fehler auftreten, während der Konstruktor ohne Argumente immer erfolgreich sein wird, eine Ausnahme ausgelöst.  
  
 Der Konstruktor mit einem einzelnen [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Parameter erstellt ein Pinsels in Volltonfarbe mit der angegebenen Farbe. Die Farbe Gibt einen RGB-Wert und konstruiert werden kann, mit der `RGB` Makro in WINDOWS. H.  
  
 Der Konstruktor mit zwei Parametern erstellt ein Schraffurpinsel. Die `nIndex` Parameter gibt den Index einer Schraffur. Die `crColor` Parameter gibt die Farbe an.  
  
 Der Konstruktor mit einem `CBitmap` Parameter erstellt einen Pinsel. Der Parameter identifiziert eine Bitmap. Wird angenommen, dass die Bitmap mit erstellten [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap:: Createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), oder [ CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). Die minimale Größe für eine Bitmap in einem Füllmusters vorgesehen ist 8 x 8 Pixel.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="createbrushindirect"></a>  CBrush::CreateBrushIndirect  
 Initialisiert einen Pinsel mit einer Formatvorlage, die Farbe und die Muster im angegebenen eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur.  
  
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
  
 Ein Pinsel erstellt mithilfe einer Bitmap Monochrom (1-Ebene, 1 Bit pro Pixel) wird unter Verwendung der aktuellen Text- und Hintergrundfarben gezeichnet. Pixel, dargestellt durch ein Bit auf 0 festgelegt werden mit der aktuellen Farbe des Texts gezeichnet. Pixel, dargestellt durch ein Bit auf 1 festgelegt werden mit der aktuellen Hintergrundfarbe gezeichnet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="createdibpatternbrush"></a>  CBrush::CreateDIBPatternBrush  
 Initialisiert einen Pinsel mit dem Muster, die durch eine geräteunabhängige Bitmap (DIB) angegeben.  
  
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
 Identifiziert ein globaler Speicher-Objekt, das eine gepackte geräteunabhängige Bitmap (DIB) enthält.  
  
 *nUsage*  
 Gibt an, ob die **BmiColors []** Felder von der [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) explizite RGB-Werte oder Indizes Datenstruktur (ein Teil der "zurück, der die DIB") enthalten, in der aktuell realisierte logische Palette. Der Parameter muss einen der folgenden Werte sein:  
  
- **DIB_PAL_COLORS** die Farbtabelle besteht aus einem Array von 16-Bit-Indizes.  
  
- **DIB_RGB_COLORS** der Farbtabelle enthält Literale RGB-Werte.  
  
 *lpPackedDIB*  
 Verweist auf eine gepackte DIB bestehend aus einem `BITMAPINFO` Struktur folgt unmittelbar ein Array von Bytes, die die Pixel der Bitmap definieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend für jeden Gerätekontext ausgewählt werden, die auszuführenden Vorgängen unterstützen.  
  
 Die beiden Versionen unterscheiden sich in der, wie Sie die DIB behandelt:  
  
-   In der ersten Version ein Handle für die DIB abrufen rufen Sie auf der Windows **GlobalAlloc** Funktion, um einen globalen Speicherblock zuordnen und geben Sie dann den Speicher mit dem gepackten DIB.  
  
-   In der zweiten Version ist es nicht notwendig, **GlobalAlloc** für die gepackte DIB Arbeitsspeicher belegt werden.  
  
 Eine gepackte DIB besteht aus einem `BITMAPINFO` Datenstruktur, die unmittelbar nach der das Array von Bytes, die die Pixel der Bitmap definiert. Als Füllung Muster verwendet Bitmaps muss 8 x 8 Pixel. Wenn die Bitmap größer ist, erstellt Windows eine Füllmusters verwenden nur die Bits, die die ersten 8 Zeilen und 8 Spalten in der oberen linken Ecke der Bitmap Pixel entspricht.  
  
 Wenn eine Anwendung eine monochrome Gerätekontext Pinsel zwei Farben DIB Muster auswählt, wird Windows in DIB angegebenen Farben ignoriert und stattdessen zeigt den Musterpinsel mit der aktuellen Text- und Hintergrundfarben des Gerätekontexts. Der ersten Farbe (am Offset 0 in der Farbtabelle DIB) der DIB Pixel werden mit der Textfarbe angezeigt. Pixel, die der zweiten Farbe (Offset 1 in der Tabelle Farbe) werden mit der Hintergrundfarbe angezeigt.  
  
 Informationen zur Verwendung der folgenden Windows-Funktionen finden Sie im Windows-SDK:  
  
- [CreateDIBPatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183492) (diese Funktion wird nur für Kompatibilität mit Anwendungen für Windows-Versionen vor 3.0 bereitgestellt; verwenden Sie die **CreateDIBPatternBrushPt** Funktion.)  
  
- [CreateDIBPatternBrushPt](http://msdn.microsoft.com/library/windows/desktop/dd183493) (diese Funktion sollte für Win32-basierte Anwendungen verwendet werden.)  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="createhatchbrush"></a>  CBrush::CreateHatchBrush  
 Initialisiert einen Pinsel mit dem angegebenen Schraffur und die Farbe an.  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt die Schraffurart des Pinsels. Eine der folgenden Werte sind möglich:  
  
- `HS_BDIAGONAL` Nach unten weisenden Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_CROSS` Horizontale und vertikale Schraffur  
  
- `HS_DIAGCROSS` Kreuzschraffur 45 Grad  
  
- `HS_FDIAGONAL` Nach oben Schraffur (von links nach rechts) auf 45 Grad  
  
- `HS_HORIZONTAL` Horizontale Schraffur  
  
- `HS_VERTICAL` Vertikale Schraffur  
  
 `crColor`  
 Gibt die Vordergrundfarbe des Pinsels als eine RGB-Farbe (die Farbe der Schraffuren) an. Finden Sie unter [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) in das Windows SDK für Weitere Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend als den aktuellen Pinsel für alle Gerätekontext ausgewählt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="createpatternbrush"></a>  CBrush::CreatePatternBrush  
 Initialisiert einen Pinsel mit einem Muster, die durch eine Bitmap angegeben.  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmap`  
 Identifiziert eine Bitmap an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend für jeden Gerätekontext ausgewählt werden, die auszuführenden Vorgängen unterstützen. Die Bitmap identifizierte `pBitmap` ist in der Regel initialisiert, indem die [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap:: Createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), oder [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) Funktion.  
  
 Als Füllung Muster verwendet Bitmaps muss 8 x 8 Pixel. Wenn die Bitmap größer ist, verwendet Windows nur die Bits, die ersten 8 Zeilen und Spalten der Pixel in der oberen linken Ecke der Bitmap entsprechen.  
  
 Ein Musterpinsel kann ohne Auswirkungen auf die zugeordneten Bitmap gelöscht werden. Dies bedeutet, dass die Bitmap verwendet werden kann, um eine beliebige Anzahl von Musterpinsel zu erstellen.  
  
 Ein Pinsel mit eine monochrome Bitmap (Ebene 1 Farbe, 1 Bit pro Pixel) erstellt wird unter Verwendung der aktuellen Text- und Hintergrundfarben gezeichnet. Pixel, dargestellt durch ein Bit auf 0 festgelegt, werden mit der aktuellen Farbe des Texts gezeichnet. Pixel, dargestellt durch ein Bit auf 1 festgelegt, werden mit der aktuellen Hintergrundfarbe gezeichnet.  
  
 Informationen zur Verwendung [CreatePatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183508), ein Windows-Funktion, finden Sie im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="createsolidbrush"></a>  CBrush::CreateSolidBrush  
 Initialisiert einen Pinsel mit einer angegebenen Volltonfarbe aus.  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Struktur, die Farbe des Pinsels angibt. Die Farbe Gibt einen RGB-Wert und konstruiert werden kann, mit der `RGB` Makro in WINDOWS. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend als den aktuellen Pinsel für alle Gerätekontext ausgewählt werden.  
  
 Wenn eine Anwendung nicht mehr verwendet den Pinsel erstellt, indem `CreateSolidBrush`, sollten sie den Pinsel im Gerätekontext auswählen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CBrush::CBrush](#cbrush).  
  
##  <a name="createsyscolorbrush"></a>  CBrush::CreateSysColorBrush  
 Initialisiert eine Pinselfarbe.  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt einen Index für die Farbe an. Dieser Wert entspricht der Farbe verwendet, um eines der Fensterelemente 21 zeichnen. Finden Sie unter [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) in das Windows SDK für eine Liste von Werten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel kann anschließend als den aktuellen Pinsel für alle Gerätekontext ausgewählt werden.  
  
 Wenn eine Anwendung nicht mehr verwendet den Pinsel erstellt, indem `CreateSysColorBrush`, sollten sie den Pinsel im Gerätekontext auswählen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="fromhandle"></a>  CBrush::FromHandle  
 Gibt einen Zeiger auf eine `CBrush` Objekt, wenn ein Handle zu einem Windows vorhanden [HBRUSH](#operator_hbrush) Objekt.  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `hBrush`  
 `HANDLE` auf einem Windows-GDI-Pinsel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CBrush` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CBrush` Objekt ist nicht bereits angefügt an das Handle, das einen temporären `CBrush` Objekt erstellt und angefügt. Dieser temporäre `CBrush` -Objekt nur bis zur nächsten Ausführung, die die Anwendung Leerlaufzeit in die Ereignisschleife verfügt gültig ist. Zu diesem Zeitpunkt werden alle temporären Grafikobjekte gelöscht. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht von einem Fenster gültig.  
  
 Weitere Informationen zum Verwenden von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CBrush::CBrush](#cbrush).  
  
##  <a name="getlogbrush"></a>  CBrush::GetLogBrush  
 Rufen Sie diese Memberfunktion zum Abrufen der `LOGBRUSH` Struktur.  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `pLogBrush`  
 Verweist auf eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) -Struktur, die Informationen zu den Pinsel enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, und `pLogBrush` gültiger Zeiger ist, ist der Rückgabewert ist die Anzahl der Bytes im Puffer gespeichert.  
  
 Wenn die Funktion erfolgreich ausgeführt wird, und `pLogBrush` ist **NULL**, der Rückgabewert ist die Anzahl der Bytes, die erforderlich sind, für die Informationen der Funktion würde im Puffer gespeichert.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `LOGBRUSH` Struktur definiert die Formatvorlage, die Farbe und die Muster aus einem Pinsel.  
  
 Rufen Sie z. B. `GetLogBrush` mit der bestimmten Farbe oder eine Bitmap-Muster übereinstimmen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="operator_hbrush"></a>  CBrush::operator HBRUSH  
 Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle Abrufen der `CBrush` Objekt.  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CBrush` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator wird ein Typumwandlungsoperator, die direkte Verwendung von unterstützt ein `HBRUSH` Objekt.  
  
 Weitere Informationen zum Verwenden von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel PROPDLG](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBitmap-Klasse](../../mfc/reference/cbitmap-class.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)
