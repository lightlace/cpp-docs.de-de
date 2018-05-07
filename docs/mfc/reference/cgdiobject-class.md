---
title: CGdiObject Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba88269cf37f41cf8a594745eb2e98a57ccf64ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cgdiobject-class"></a>CGdiObject-Klasse
Stellt eine Basisklasse für verschiedene Arten von Objekten der Windows GDI (Graphics Device Interface) wie Bitmaps, Bereiche, Pinsel, Stifte, Paletten und Schriftwarten bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|Erstellt ein `CGdiObject`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Fügt ein Windows-GDI-Objekt, das eine `CGdiObject` Objekt.|  
|[CGdiObject::CreateStockObject](#createstockobject)|Ruft ein Handle für das Windows vordefinierten stock Stifte, Pinsel, oder Schriftarten ab.|  
|[CGdiObject::DeleteObject](#deleteobject)|Löscht die Windows-GDI-Objekt, um angefügt die `CGdiObject` Objekt aus dem Arbeitsspeicher freigegeben werden und alle Dateisystem-Speicherkapazität, die dem Objekt zugeordnet.|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|Löscht temporäre `CGdiObject` von erstellten Objekte `FromHandle`.|  
|[CGdiObject::Detach](#detach)|Trennt ein Windows-GDI-Objekt aus einem `CGdiObject` -Objekt und gibt ein Handle für das Windows-GDI-Objekt.|  
|[CGdiObject::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CGdiObject` Objekt ein Handle zu einem Windows-GDI-Objekt.|  
|[CGdiObject::GetObject](#getobject)|Füllt ein Puffer mit Daten, die die Windows-GDI-Objekt beschreibt angefügt, um die `CGdiObject` Objekt.|  
|[CGdiObject::GetObjectType](#getobjecttype)|Ruft den Typ des GDI-Objekts ab.|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|Gibt `m_hObject` , wenn `this` ist `NULL`, in diesem Fall `NULL` zurückgegeben wird.|  
|[CGdiObject:: UnrealizeObject](#unrealizeobject)|Setzt den Ursprung eines Pinsels oder setzt eine logische Palette.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.|  
|[CGdiObject::operator ==](#operator_eq_eq)|Bestimmt, ob zwei GDI-Objekte logisch gleich sind.|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Ruft eine `HANDLE` auf das angefügte Windows-GDI-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|Ein `HANDLE` , enthält die `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, oder `HFONT` auf dieses Objekt angefügt.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGdiObject` direkt. Vielmehr, Sie erstellen ein Objekt aus einer ihrer abgeleiteten Klassen wie z. B. `CPen` oder `CBrush`.  
  
 Weitere Informationen zu `CGdiObject`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="attach"></a>  CGdiObject::Attach  
 Fügt ein Windows-GDI-Objekt, das eine `CGdiObject` Objekt.  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Ein `HANDLE` mit einem Windows-GDI-Objekt (z. B. `HPEN` oder `HBRUSH`).  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anlage erfolgreich ist; andernfalls 0.  
  
##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject  
 Erstellt ein `CGdiObject`-Objekt.  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGdiObject` direkt. Vielmehr, Sie erstellen ein Objekt aus einer ihrer abgeleiteten Klassen wie z. B. `CPen` oder **Cbrush**.  
  
##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject  
 Ruft ein Handle auf eine der vordefinierten vordefinierten Windows-GDI-Stifte, Pinsel oder Schriftarten ab und fügt das GDI-Objekt, das die `CGdiObject` Objekt.  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine Konstante, die Angabe des Typs der vordefinierten gewünschte Objekt. Der Parameter *FnObject* für [GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925) in das Windows SDK für eine Beschreibung der entsprechenden Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Funktion mit einer der abgeleiteten Klassen, entspricht der Windows-GDI-Objekttyp, wie z. B. `CPen` für eine vordefinierte Stift.  
  
##  <a name="deleteobject"></a>  CGdiObject::DeleteObject  
 Löscht das angefügte Windows-GDI-Objekt aus dem Arbeitsspeicher freigegeben werden und alle mit dem Windows-GDI-Objekt zugeordneten Systemspeicher.  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das GDI-Objekt wurde erfolgreich gelöscht wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Über den zugeordneten Speicher der `CGdiObject` Objekt wird durch diesen Aufruf nicht beeinflusst. Eine Anwendung sollte nicht aufrufen `DeleteObject` auf eine `CGdiObject` -Objekt, das einen Gerätekontext derzeit ausgewählt ist.  
  
 Wenn ein Musterpinsel gelöscht wird, wird die dem Pinsel zugeordnete Bitmap nicht gelöscht werden. Die Bitmap muss separat gelöscht werden.  
  
##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap  
 Wird aufgerufen, automatisch von der `CWinApp` -leerlaufzeithandler, `DeleteTempMap` löscht temporäre `CGdiObject` von erstellten Objekte `FromHandle`.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Hinweise  
 `DeleteTempMap` trennt das Windows-GDI-Objekt, das an einen temporären angefügt `CGdiObject` Objekt vor dem Löschen der `CGdiObject` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>  CGdiObject::Detach  
 Trennt ein Windows-GDI-Objekt aus einem `CGdiObject` -Objekt und gibt ein Handle für das Windows-GDI-Objekt.  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HANDLE` in der Windows-GDI-Objekt getrennt ist, andernfalls **NULL** Wenn kein GDI-Objekt zugeordnet ist.  
  
##  <a name="fromhandle"></a>  CGdiObject::FromHandle  
 Gibt einen Zeiger auf eine `CGdiObject` Objekt ein Handle zu einem Windows-GDI-Objekt.  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Ein `HANDLE` mit einem Windows-GDI-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CGdiObject` , die möglicherweise vorübergehend oder dauerhaft.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CGdiObject` Objekt noch nicht mit dem Windows-GDI-Objekt, eine temporäre angefügt `CGdiObject` Objekt erstellt und angefügt.  
  
 Dieser temporäre `CGdiObject` Objekt ist nur gültig, bis das nächste Mal die Anwendung im Leerlauf Zeit hat, im zugehörigen Ereignisschleife zu diesem Zeitpunkt werden alle temporären Grafikobjekte gelöscht. Anders ausgedrückt: Dies ist, dass der Zugriff auf das temporäre Objekt während der Verarbeitung der Nachricht von einem Fenster nur gültig ist.  
  
##  <a name="getobject"></a>  CGdiObject::GetObject  
 Füllt einen Puffer mit Daten, die ein angegebenes Objekt definiert.  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nCount`  
 Gibt die Anzahl von Bytes zum Kopieren in die `lpObject` Puffer.  
  
 `lpObject`  
 Verweist auf einen Benutzer bereitgestellte Puffer, der die Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes abgerufen. Tritt auf, andernfalls 0, wenn ein Fehler an.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ruft eine Datenstruktur, dessen Typ hängt vom Typ des Grafik-Objekts, ab, wie in der folgenden Liste gezeigt:  
  
|Object|Puffertyp|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[MITHILFE EINER BITMAP](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|Nicht unterstützt|  
  
 Wenn das Objekt eine `CBitmap` Objekt `GetObject` gibt nur die Breite, Höhe und Formatierungsinformationen der Bitmap für die Farbe. Die tatsächliche Bits können abgerufen werden, mithilfe von [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).  
  
 Wenn das Objekt eine `CPalette` -Objekt, `GetObject` Ruft eine **WORD** , die die Anzahl von Einträgen in der Palette angibt. Ruft die Funktion nicht die [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) Struktur, die die Palette definiert. Eine Anwendung kann Abrufen von Informationen auf der Paletteneinträge durch Aufrufen von [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).  
  
##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType  
 Ruft den Typ des GDI-Objekts ab.  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ des Objekts, wenn erfolgreich; andernfalls 0. Der Wert kann in folgenden Formen vorliegen:  
  
- **OBJ_BITMAP** mithilfe einer Bitmap  
  
- **OBJ_BRUSH** Pinsel  
  
- **OBJ_FONT** Schriftart  
  
- **OBJ_PAL** Palette  
  
- **OBJ_PEN** Stift  
  
- **OBJ_EXTPEN** erweiterte Stift  
  
- **OBJ_REGION** Region  
  
- **OBJ_DC** Gerätekontext  
  
- **OBJ_MEMDC** Speichergerätekontext  
  
- **OBJ_METAFILE** Metadatei  
  
- **OBJ_METADC** Metadatei Gerätekontext  
  
- **OBJ_ENHMETAFILE** Erweiterte Metadatei  
  
- **OBJ_ENHMETADC** Enhanced Metafile-Gerätekontext  
  
##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle  
 Gibt `m_hObject` , wenn **dies** ist **NULL**, in diesem Fall **NULL** zurückgegeben wird.  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HANDLE` auf das angefügte Windows-GDI-Objekt; andernfalls **NULL** , wenn kein Objekt zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist Teil der allgemeinen Handle Schnittstelle Paradigma und ist hilfreich, wenn **NULL** ist ein gültiger oder spezieller Wert für ein Handle.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).  
  
##  <a name="m_hobject"></a>  CGdiObject::m_hObject  
 Ein `HANDLE` , enthält die `HBITMAP`, **HRGN**, `HBRUSH`, `HPEN`, `HPALETTE`, oder **HFONT** auf dieses Objekt angefügt.  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>  CGdiObject::operator! =  
 Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `obj`  
 Ein Zeiger auf ein vorhandenes `CGdiObject`.  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt, ob ein GDI-Objekt auf der linken Seite nicht gleich einem GDI-Objekt auf der rechten Seite ist.  
  
##  <a name="operator_eq_eq"></a>  CGdiObject::operator ==  
 Bestimmt, ob zwei GDI-Objekte logisch gleich sind.  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `obj`  
 Ein Verweis auf ein vorhandenes `CGdiObject`.  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt, ob ein GDI-Objekt auf der linken Seite eine GDI-Objekt rechts vom gleich ist.  
  
##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ  
 Ruft eine `HANDLE` auf das angefügte Windows-GDI-Objekt; andernfalls **NULL** , wenn kein Objekt zugeordnet ist.  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>  CGdiObject:: UnrealizeObject  
 Setzt den Ursprung eines Pinsels oder setzt eine logische Palette.  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Während `UnrealizeObject` ist eine Memberfunktion der `CGdiObject` -Klasse, es sollte aufgerufen werden nur auf `CBrush` oder `CPalette` Objekte.  
  
 Für `CBrush` Objekte `UnrealizeObject` weist das System den Ursprung der angegebenen Pinsel das nächste Mal zurücksetzen es einen Gerätekontext ausgewählt ist. Wenn das Objekt eine `CPalette` Objekt `UnrealizeObject` weist das System die Palette realisiert, als wäre er nicht zuvor realisiert wurden. Das nächste Mal die Anwendung aufruft, die [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) -Funktion für die angegebene Palette, das System vollständig ordnet die logische Palette der Systempalette.  
  
 Die `UnrealizeObject` Funktion sollte nicht mit vordefinierten Objekten verwendet werden. Die `UnrealizeObject` -Funktion muss aufgerufen werden, ein neuen Pinsel Ursprung festgelegt ist (mithilfe von der [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) Funktion). Die `UnrealizeObject` Funktion darf nicht für die aktuell ausgewählte Pinsel oder der aktuell ausgewählten Palette alle Anzeigekontext aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBitmap-Klasse](../../mfc/reference/cbitmap-class.md)   
 [CBrush-Klasse](../../mfc/reference/cbrush-class.md)   
 [CFont-Klasse](../../mfc/reference/cfont-class.md)   
 [CPalette-Klasse](../../mfc/reference/cpalette-class.md)   
 [CPen-Klasse](../../mfc/reference/cpen-class.md)   
 [CRgn-Klasse](../../mfc/reference/crgn-class.md)
