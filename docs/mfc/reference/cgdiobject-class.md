---
title: CGdiObject Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- brushes, base class for
- fonts, base class for
- regions, base class for
- pens, base class for
- palettes, base class for
- CGdiObject class
- GDI objects, base class for
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
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
ms.openlocfilehash: 7fb0cd49c6a20263a5cae305b7f08f2733033ff2
ms.lasthandoff: 02/24/2017

---
# <a name="cgdiobject-class"></a>CGdiObject-Klasse
Stellt eine Basisklasse für verschiedene Arten von Objekten der Windows GDI (Graphics Device Interface) wie Bitmaps, Bereiche, Pinsel, Stifte, Paletten und Schriftwarten bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|Erstellt ein `CGdiObject`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Fügt ein Windows-GDI-Objekt, das ein `CGdiObject` Objekt.|  
|[CGdiObject::CreateStockObject](#createstockobject)|Ruft ein Handle für die Windows vordefinierte stock Stifte, Pinsel oder Schriftarten ab.|  
|[CGdiObject::DeleteObject](#deleteobject)|Löscht die Windows-GDI-Objekt an die `CGdiObject` Objekt aus dem Speicher durch Freigabe alle Systemspeicher, die dem Objekt zugeordnet.|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|Löscht alle temporären `CGdiObject` von erstellten Objekte `FromHandle`.|  
|[CGdiObject::Detach](#detach)|Trennt eine Windows-GDI-Objekt aus einem `CGdiObject` -Objekt und gibt ein Handle für das Windows-GDI-Objekt.|  
|[CGdiObject::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CGdiObject` Objekt ein Handle mit einem Windows-GDI-Objekt.|  
|[CGdiObject::GetObject](#getobject)|Füllt ein Puffer mit Daten, die die Windows-GDI-Objekt beschreibt angefügt, um die `CGdiObject` Objekt.|  
|[CGdiObject::GetObjectType](#getobjecttype)|Ruft den Typ des GDI-Objekts ab.|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|Gibt `m_hObject` , wenn `this` ist `NULL`, in diesem Fall `NULL` zurückgegeben wird.|  
|[CGdiObject:: UnrealizeObject](#unrealizeobject)|Setzt den Ursprung eines Pinsels oder setzt eine logische Palette.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.|  
|[CGdiObject::operator ==](#operator_eq_eq)|Bestimmt, ob zwei GDI-Objekte logisch gleich sind.|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Ruft eine `HANDLE` der angefügten Windows GDI-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|Ein `HANDLE` , enthält die `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, oder `HFONT` für dieses Objekt angefügt.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGdiObject` direkt. Stattdessen erstellen ein Objekts aus einer der davon abgeleiteten Klassen, z. B. `CPen` oder `CBrush`.  
  
 Weitere Informationen zu `CGdiObject`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="attach"></a>CGdiObject::Attach  
 Fügt ein Windows-GDI-Objekt, das ein `CGdiObject` Objekt.  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Ein `HANDLE` mit einem Windows-GDI-Objekt (z. B. `HPEN` oder `HBRUSH`).  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anlage erfolgreich ist; andernfalls 0.  
  
##  <a name="cgdiobject"></a>CGdiObject::CGdiObject  
 Erstellt ein `CGdiObject`-Objekt.  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGdiObject` direkt. Stattdessen erstellen ein Objekts aus einer der davon abgeleiteten Klassen, z. B. `CPen` oder **Cbrush**.  
  
##  <a name="createstockobject"></a>CGdiObject::CreateStockObject  
 Ruft ein Handle auf eine der vordefinierten vordefinierten Windows-GDI-Stifte, Pinsel oder Schriftarten und fügt das GDI-Objekt, das die `CGdiObject` Objekt.  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine Konstante, die den Typ des vordefinierten gewünschte Objekt angibt. Der Parameter *FnObject* für [GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Beschreibung der entsprechenden Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Funktion mit einer der abgeleiteten Klassen, entspricht der Windows GDI-Objekttyp, wie z. B. `CPen` für eine vordefinierte Stift.  
  
##  <a name="deleteobject"></a>CGdiObject::DeleteObject  
 Das angefügte Windows GDI-Objekt aus dem Speicher gelöscht, durch die Freigabe alle Systemspeicher, die die Windows-GDI-Objekt zugeordnet.  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das GDI-Objekt gelöscht wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der zugeordnete Speicher der `CGdiObject` Objekt wird von diesem Aufruf nicht beeinflusst. Eine Anwendung sollte nicht aufrufen, `DeleteObject` auf einem `CGdiObject` -Objekt, das einen Gerätekontext derzeit ausgewählt ist.  
  
 Wenn ein Musterpinsel gelöscht wird, wird die mit dem Pinsel verknüpfte Bitmap nicht gelöscht. Die Bitmap muss separat gelöscht werden.  
  
##  <a name="deletetempmap"></a>CGdiObject::DeleteTempMap  
 Namens automatisch von der `CWinApp` Zeit im Leerlauf Ereignishandler `DeleteTempMap` löscht alle temporären `CGdiObject` von erstellten Objekte `FromHandle`.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Hinweise  
 `DeleteTempMap`trennt das Windows-GDI-Objekt angefügt an einen temporären `CGdiObject` Objekt vor dem Löschen der `CGdiObject` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#175;](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>CGdiObject::Detach  
 Trennt eine Windows-GDI-Objekt aus einem `CGdiObject` -Objekt und gibt ein Handle für das Windows-GDI-Objekt.  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HANDLE` in die Windows-GDI-Objekt getrennt; andernfalls **NULL** Wenn keine GDI-Objekt verknüpft ist.  
  
##  <a name="fromhandle"></a>CGdiObject::FromHandle  
 Gibt einen Zeiger auf ein `CGdiObject` Objekt ein Handle mit einem Windows-GDI-Objekt.  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Ein `HANDLE` mit einem Windows-GDI-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CGdiObject` temporär oder permanent sein können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CGdiObject` Objekt noch nicht angefügt an das Windows-GDI-Objekt, ein temporäres `CGdiObject` Objekt erstellt und angefügt wird.  
  
 Dieser temporäre `CGdiObject` Objekt ist nur gültig, bis das nächste Mal die Anwendung Leerlaufzeit im zugehörigen Ereignisschleife zu diesem Zeitpunkt werden alle temporären Grafikobjekte gelöscht wurde. Anders ausgedrückt: Dies ist, dass das temporäre Objekt nur während der Verarbeitung der Nachricht ein Fenster gültig ist.  
  
##  <a name="getobject"></a>CGdiObject::GetObject  
 Füllt einen Puffer mit Daten, die ein angegebenen Objekt zu definieren.  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nCount`  
 Gibt die Anzahl der Bytes, die zum Kopieren in die `lpObject` Puffer.  
  
 `lpObject`  
 Verweist auf einen Benutzer bereitgestellte Puffer, der die Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes abgerufen. Andernfalls wird 0, wenn ein Fehler ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ruft eine Datenstruktur, deren Typ hängt vom Typ der Grafikobjekt, ab, wie in der folgenden Liste dargestellt:  
  
|Objekt|Puffertyp|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|["LOGFONT"](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[BITMAP](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|Nicht unterstützt|  
  
 Wenn das Objekt eine `CBitmap` Objekt `GetObject` gibt nur die Breite, Höhe und Farbe Formatierungsinformationen der Bitmap. Die eigentlichen Bits können abgerufen werden, mithilfe von [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).  
  
 Wenn das Objekt eine `CPalette` -Objekt, `GetObject` Ruft eine **WORD** , der die Anzahl der Einträge in der Palette angibt. Ruft die Funktion nicht die [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) -Struktur, die die Palette definiert. Eine Anwendung kann durch Aufrufen von Informationen über Paletteneinträge abrufen [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).  
  
##  <a name="getobjecttype"></a>CGdiObject::GetObjectType  
 Ruft den Typ des GDI-Objekts ab.  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ des Objekts, wenn erfolgreich; andernfalls 0. Die folgenden Werte sind möglich:  
  
- **OBJ_BITMAP** Bitmap  
  
- **OBJ_BRUSH** Pinsel  
  
- **OBJ_FONT** Schriftart  
  
- **OBJ_PAL** Palette  
  
- **OBJ_PEN** Stift  
  
- **OBJ_EXTPEN** erweiterte Stift  
  
- **OBJ_REGION** Region  
  
- **OBJ_DC** Gerätekontext  
  
- **OBJ_MEMDC** Speicher-Gerätekontext  
  
- **OBJ_METAFILE** Metadatei  
  
- **OBJ_METADC** Metadatei-Gerätekontext  
  
- **OBJ_ENHMETAFILE** Erweiterte Metadatei  
  
- **OBJ_ENHMETADC** Enhanced Metafile Gerätekontext  
  
##  <a name="getsafehandle"></a>CGdiObject::GetSafeHandle  
 Gibt `m_hObject` , wenn **dies** ist **NULL**, **NULL** zurückgegeben wird.  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HANDLE` der angefügten Windows GDI-Objekt; andernfalls **NULL** , wenn kein Objekt zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist Teil der allgemeinen Handle Schnittstelle Paradigma und ist hilfreich, wenn **NULL** ist ein gültiger oder spezieller Wert für ein Handle.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).  
  
##  <a name="m_hobject"></a>CGdiObject::m_hObject  
 Ein `HANDLE` , enthält die `HBITMAP`, **HRGN**, `HBRUSH`, `HPEN`, `HPALETTE`, oder **HFONT** für dieses Objekt angefügt.  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>CGdiObject::operator! =  
 Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `obj`  
 Ein Zeiger auf einen vorhandenen `CGdiObject`.  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt, ob ein GDI-Objekt auf der linken Seite ungleich ein GDI-Objekt auf der rechten Seite ist.  
  
##  <a name="operator_eq_eq"></a>CGdiObject::operator ==  
 Bestimmt, ob zwei GDI-Objekte logisch gleich sind.  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `obj`  
 Ein Verweis auf einen vorhandenen `CGdiObject`.  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt, ob ein GDI-Objekt auf der linken Seite gleich ein GDI-Objekt auf der rechten Seite ist.  
  
##  <a name="operator_hgdiobj"></a>CGdiObject::operator HGDIOBJ  
 Ruft eine `HANDLE` der angefügten Windows GDI-Objekt; andernfalls **NULL** Wenn kein Objekt zugeordnet ist.  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>CGdiObject:: UnrealizeObject  
 Setzt den Ursprung eines Pinsels oder setzt eine logische Palette.  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Während `UnrealizeObject` ist eine Memberfunktion der `CGdiObject` -Klasse, es sollte aufgerufen werden, nur auf `CBrush` oder `CPalette` Objekte.  
  
 Für `CBrush` Objekte `UnrealizeObject` weist das System den Ursprung der angegebenen Pinsel das nächste Mal zurücksetzen es einen Gerätekontext ausgewählt ist. Wenn das Objekt eine `CPalette` Objekt `UnrealizeObject` weist das System an der Palette zu erkennen, als wäre es nicht bereits erzielt wurde. Das nächste Mal die Anwendung ruft die [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) -Funktion für die angegebene Palette, das System vollständig ordnet die logische Palette der Systempalette.  
  
 Die `UnrealizeObject` Funktion sollte nicht mit vorhandenen Objekten verwendet werden. Die `UnrealizeObject` -Funktion muss aufgerufen werden, wenn Sie ein neuen Pinsel Ursprung festgelegt ist (von der [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) Funktion). Die `UnrealizeObject` Funktion darf nicht aufgerufen werden, für die aktuell ausgewählten Pinsel oder der aktuell ausgewählten Palette von einem beliebigen Anzeigekontext.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBitmap-Klasse](../../mfc/reference/cbitmap-class.md)   
 [CBrush-Klasse](../../mfc/reference/cbrush-class.md)   
 [CFont-Klasse](../../mfc/reference/cfont-class.md)   
 [CPalette-Klasse](../../mfc/reference/cpalette-class.md)   
 [CPen-Klasse](../../mfc/reference/cpen-class.md)   
 [CRgn-Klasse](../../mfc/reference/crgn-class.md)

