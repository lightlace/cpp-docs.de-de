---
title: CBitmap-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
dev_langs:
- C++
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 476e9b0bc5e9f4c3eec64e5d0d36d3f900988f48
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954215"
---
# <a name="cbitmap-class"></a>CBitmap-Klasse
Kapselt eine Bitmap der Windows GDI (Graphics Device Interface) und stellt Memberfunktionen zur Bearbeitung der Bitmap bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|Erstellt ein `CBitmap`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|Initialisiert das Objekt mit einem Gerät geräteabhängige speicherbitmap, die einer angegebenen Breite, Höhe und Bitmuster aufweist.|  
|[CBitmap:: Createbitmapindirect](#createbitmapindirect)|Initialisiert das Objekt mit einer Bitmap mit der Breite, Höhe und Bitmuster (sofern diese angegeben ist), die im angegebenen eine **BITMAP** Struktur.|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Initialisiert das Objekt mit einer Bitmap, so, dass er mit einem angegebenen Gerät kompatibel ist.|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Initialisiert das Objekt mit einer entfernbar Bitmap, die mit einem angegebenen Gerät kompatibel ist.|  
|[CBitmap::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CBitmap` Objekt, wenn ein Handle zu einem Windows vorhanden `HBITMAP` mithilfe einer Bitmap.|  
|[CBitmap::GetBitmap](#getbitmap)|Füllt eine **BITMAP** Struktur mit Informationen über die Bitmap.|  
|[CBitmap::GetBitmapBits](#getbitmapbits)|Kopiert die Bits eines angegebenen Bitmap in den angegebenen Puffer.|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Gibt die Breite und Höhe der Bitmap an. Die Höhe und Breite werden als zuvor festgelegt wurden, indem die [SetBitmapDimension](#setbitmapdimension) Memberfunktion.|  
|[LoadBitmap](#loadbitmap)|Initialisiert das Objekt durch eine benannte Bitmapressource von ausführbare Datei der Anwendung geladen und Anfügen der Bitmap auf das Objekt an.|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Lädt eine Bitmap und aktuellen Systemfarben Farben zugeordnet.|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Initialisiert das Objekt durch das Laden einer vordefinierten Windows-Bitmap und Anfügen der Bitmap auf das Objekt an.|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|Legt die Bits einer Bitmap auf den angegebenen Bitwerte fest.|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Weist eine Breite und Höhe einer Bitmap in Einheiten von 0,1 Millimeter.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmap::operator HBITMAP](#operator_hbitmap)|Gibt die Windows-Handle an der die `CBitmap` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CBitmap` -Objekt, erstellen Sie das Objekt, fügen Sie ein Bitmaphandle an diese mit einem der Initialisierung Memberfunktionen und klicken Sie dann das Objekt Memberfunktionen aufrufen.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten wie `CBitmap`, finden Sie unter [Grafik Objekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cbitmap"></a>  CBitmap::CBitmap  
 Erstellt ein `CBitmap`-Objekt.  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>Hinweise  
 Das resultierende Objekt muss mit einem der Memberfunktionen Initialisierung initialisiert werden.  
  
##  <a name="createbitmap"></a>  CBitmap::CreateBitmap  
 Initialisiert eine geräteabhängige Speicherbitmap, die die angegebene Breite, Höhe und das angegebene Bitmuster aufweist.  
  
```  
BOOL CreateBitmap(
    int nWidth,  
    int nHeight,  
    UINT nPlanes,  
    UINT nBitcount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Parameter  
 *nWidth*  
 Gibt die Breite der Bitmap (in Pixeln) an.  
  
 *nHeight*  
 Gibt die Höhe der Bitmap (in Pixeln) an.  
  
 *nPlanes*  
 Gibt die Anzahl von Farbebenen in der Bitmap an.  
  
 *nBitcount*  
 Gibt die Anzahl der Farbbits pro Anzeigepixel an.  
  
 *lpBits*  
 Zeigt auf ein Array von Bytes, das die ursprünglichen Bitwerte der Bitmap enthält. Ist dieser Wert **NULL**, bleibt die neue Bitmap nicht initialisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Für eine Farbbitmap muss entweder der *nPlanes* oder *nBitcount* Parameter sollte auf 1 festgelegt werden. Wenn beide Parameter auf 1 festgelegt sind, erstellt `CreateBitmap` eine monochrome Bitmap.  
  
 Obwohl eine Bitmap kann nicht direkt für ein Anzeigegerät ausgewählt werden, er kann ausgewählt werden, als aktuelle Bitmap für einen "Speichergerätekontext" mithilfe von [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) und auf einen beliebigen kompatiblen Gerätekontext kopiert werden, mithilfe der [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) Funktion.  
  
 Wenn Sie mit dem `CBitmap` -Objekt fertig sind, das von der `CreateBitmap` -Funktion erstellt wurde, wählen Sie zunächst die Bitmap im Gerätekontext aus, und löschen Sie dann das `CBitmap` -Objekt.  
  
 Weitere Informationen finden Sie unter der Beschreibung des **bmBits** -Felds der **BITMAP** -Struktur. Die [BITMAP](../../mfc/reference/bitmap-structure.md) Struktur wird beschrieben, unter der [CBitmap:: Createbitmapindirect](#createbitmapindirect) Memberfunktion.  
  
##  <a name="createbitmapindirect"></a>  CBitmap:: Createbitmapindirect  
 Initialisiert eine Bitmap, die die Breite, Höhe und Bitmuster (sofern diese angegeben ist), die in der Struktur verweist angegeben hat *LpBitmap*.  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 *lpBitmap*  
 Verweist auf eine [BITMAP](../../mfc/reference/bitmap-structure.md) -Struktur, die Informationen über die Bitmap enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Obwohl eine Bitmap kann nicht direkt für ein Anzeigegerät ausgewählt werden, er kann ausgewählt werden, als aktuelle Bitmap für einen Gerätekontext Arbeitsspeicher mit [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) und auf einen beliebigen kompatiblen Gerätekontext kopiert werden, mithilfe der [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) oder [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) Funktion. (Die [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) Funktion kann die Bitmap für die aktuelle Pinsel direkt an den Anzeigekontext für das Gerät kopieren.)  
  
 Wenn die **BITMAP** Struktur an, die durch die *LpBitmap* Parameter ausgefüllt ist, mithilfe der `GetObject` -Funktion, die Bits der Bitmap wurden nicht angegeben und die Bitmap wird nicht initialisiert. Um das Bitmuster zu initialisieren, eine Anwendung können eine Funktion wie z. B. [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) oder [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) So kopieren Sie die Bits aus der Bitmap, die durch den ersten Parameter identifiziert `CGdiObject::GetObject` für die Bitmap erstellt von `CreateBitmapIndirect`.  
  
 Wenn Sie fertig sind, mit der `CBitmap` mit erstellte Objekt `CreateBitmapIndirect` funktionieren, zunächst wählen Sie die Bitmap im Gerätekontext, löschen Sie die `CBitmap` Objekt.  
  
##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap  
 Initialisiert eine Bitmap, die kompatibel mit den durch das angegebene Gerät ist *pDC*.  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Gibt den Gerätekontext.  
  
 *nWidth*  
 Gibt die Breite der Bitmap (in Pixeln) an.  
  
 *nHeight*  
 Gibt die Höhe der Bitmap (in Pixeln) an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap hat die gleiche Anzahl von Farbebenen oder das gleiche Bits pro Pixel-Format als den angegebenen Gerätekontext. Er kann ausgewählt werden, als aktuelle Bitmap für Arbeitsspeicher-Geräte, die kompatibel mit der vom angegebenen *pDC*.  
  
 Wenn *pDC* ist eine Speichergerätekontext Bitmap zurückgegeben hat das gleiche Format wie die aktuell ausgewählte Bitmap dieser Gerätekontext. Einen "Speichergerätekontext" ist ein Speicherblock, der eine Anzeigeoberfläche darstellt. Es dient zum Vorbereiten von Images im Arbeitsspeicher, bevor Sie sie der tatsächlichen Anzeigeoberfläche des Geräts kompatibel zu kopieren.  
  
 Wenn eine Speichergerätekontext erstellt wird, wählt GDI automatisch eine monochrome Bitmap für die vordefinierte dafür an.  
  
 Da eine Farbe Speichergerätekontext Farbe oder monochrome Bitmaps ausgewählt haben, kann, das Format der Bitmap zurückgegeben, durch die `CreateCompatibleBitmap` Funktion ist nicht immer identisch, allerdings ist das Format einer kompatiblen Bitmap für einen Gerätekontext Panik immer in der Format des Geräts.  
  
 Wenn Sie fertig sind, mit der `CBitmap` Objekt erstellt, mit der `CreateCompatibleBitmap` Funktion, zunächst die Bitmap im Gerätekontext auswählen und dann Löschen der `CBitmap` Objekt.  
  
##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap  
 Initialisiert eine entfernbare Bitmap, die kompatibel mit den Gerätekontext erkennbar ist *pDC*.  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Gibt einen Gerätekontext.  
  
 *nWidth*  
 Gibt die Breite (in Bits) der Bitmap an.  
  
 *nHeight*  
 Gibt die Höhe der Bitmap (in Bits) an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap hat die gleiche Anzahl von Farbebenen oder das gleiche Bits pro Pixel-Format als den angegebenen Gerätekontext. Eine Anwendung kann diese Bitmap wählen Sie als aktuelle Bitmap für ein Speichergerät, die kompatibel mit der vom angegebenen *pDC*.  
  
 Windows kann eine Bitmap, die von dieser Funktion nur erstellt, wenn eine Anwendung sie nicht in einen Anzeigekontext ausgewählt wurde verworfen. Wenn Windows verwirft die Bitmap aus, wenn es nicht aktiviert ist und die Anwendung später versucht wird, um diese auszuwählen, die [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) Funktion zurück **NULL**.  
  
 Wenn Sie fertig sind, mit der `CBitmap` Objekt erstellt, mit der `CreateDiscardableBitmap` Funktion, zunächst die Bitmap im Gerätekontext auswählen und dann Löschen der `CBitmap` Objekt.  
  
##  <a name="fromhandle"></a>  CBitmap::FromHandle  
 Gibt einen Zeiger auf ein `CBitmap` Objekt, wenn ein Handle zu einem Windows-GDI-Bitmap vorhanden.  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 *hBitmap*  
 Gibt eine Windows-GDI-Bitmap.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CBitmap` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CBitmap` Objekt ist nicht bereits angefügt an das Handle, das einen temporären `CBitmap` Objekt erstellt und angefügt. Dieser temporäre `CBitmap` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner-Ereignisschleife aufweist, zu dem alle temporären Grafik Zeit Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass der Zugriff auf das temporäre Objekt während der Verarbeitung der Nachricht von einem Fenster nur gültig ist.  
  
##  <a name="getbitmap"></a>  CBitmap::GetBitmap  
 Ruft Eigenschaften für die angefügte Bitmap ab.  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>Parameter  
 *pBitMap*  
 Zeiger auf eine [Bitmapstruktur](../../mfc/reference/bitmap-structure.md) -Struktur, die die abbildeigenschaften erhält. Dieser Parameter darf nicht `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getbitmapbits"></a>  CBitmap::GetBitmapBits  
 Kopiert das Bitmuster der Bitmap für die angefügte in den angegebenen Puffer.  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *dwCount*  
 Die Anzahl von Bytes, die in den Puffer kopiert werden sollen.  
  
 *lpBits*  
 Zeiger auf den Puffer, der die Bitmap empfangen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die in den Puffer kopiert werden, wenn die Methode erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBitmap::GetBitmap](#getbitmap) die erforderliche Puffergröße bestimmen.  
  
##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension  
 Gibt die Breite und Höhe der Bitmap an.  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite und Höhe der Bitmap, gemessen in Einheiten von 0,1 Millimeter. Die Höhe wird der **cy** Mitglied der `CSize` Objekt und die Breite befindet sich in der **Cx** Member. Wenn die Bitmap-Breite und Höhe mithilfe nicht festgelegt wurde `SetBitmapDimension`, wird 0 zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe und Breite werden als zuvor festgelegt wurden mithilfe der [SetBitmapDimension](#setbitmapdimension) Memberfunktion.  
  
##  <a name="loadbitmap"></a>  LoadBitmap  
 Lädt die Bitmapressource mit dem Namen von *LpszResourceName* oder durch die ID-Nummer in identifiziert *nIDResource* aus der ausführbaren Datei der Anwendung.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszResourceName*  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen der Bitmapressource enthält.  
  
 *nIDResource*  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die geladene Bitmap angefügt ist die `CBitmap` Objekt.  
  
 Wenn die Bitmap identifizierte *LpszResourceName* ist nicht vorhanden oder ist nicht genügend Arbeitsspeicher zum Laden der Bitmap, die Funktion gibt 0 zurück.  
  
 Können Sie die [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Funktion, um das Löschen der Bitmap geladen werden, indem die `LoadBitmap` -Funktion, oder die `CBitmap` Destruktor wird das Objekt für Sie zu löschen.  
  
> [!CAUTION]
>  Bevor Sie das Objekt löschen, stellen Sie sicher, dass er einen Gerätekontext nicht ausgewählt ist.  
  
 Windows-Versionen 3.1 und höher wurden die folgenden Bitmaps hinzugefügt:  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 Diese Bitmaps sind in der Gerätetreiber für Windows-Versionen 3.0 und früheren Versionen nicht gefunden. Eine vollständige Liste von Bitmaps sowie eine Anzeige ihrer Darstellung finden Sie im Windows-SDK.  
  
##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap  
 Rufen Sie diese Memberfunktion zum Laden einer Bitmaps und die Farben der aktuellen Systemfarben zuordnen.  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDBitmap*  
 Die ID der Bitmapressource.  
  
 *nFlags*  
 Ein Flag für eine Bitmap. Kann 0 (null) sein oder **CMB_MASKED**.  
  
 *lpColorMap*  
 Ein Zeiger auf eine **COLORMAP** Struktur, die die Farbe benötigten Informationen zum Zuordnen von Bitmaps enthält. Wenn dieser Parameter ist **NULL**, die Funktion verwendet die Standard-Farbkarte.  
  
 *nMapSize*  
 Die Anzahl der farbkarten enthalten verweist *LpColorMap*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `LoadMappedBitmap` werden häufig in der Schaltfläche Glyphen verwendete Farben zugeordnet.  
  
 Informationen zum Erstellen einer Bitmap zugeordneten finden Sie in der Windows-Funktion [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562) und [COLORMAP](http://msdn.microsoft.com/library/windows/desktop/bb760448) Struktur im Windows SDK.  
  
##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap  
 Lädt eine vordefinierte Bitmap, die von Windows verwendet.  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDBitmap*  
 ID-Nummer der vordefinierten Windows-Bitmap. Die möglichen Werte sind unten aufgeführt, von WINDOWS. H  
  
|||  
|-|-|  
|**OBM_BTNCORNERS**|**OBM_OLD_RESTORE**|  
|**OBM_BTSIZE**|**OBM_OLD_RGARROW**|  
|**OBM_CHECK**|**OBM_OLD_UPARROW**|  
|**OBM_CHECKBOXES**|**OBM_OLD_ZOOM**|  
|**OBM_CLOSE**|**OBM_REDUCE**|  
|**OBM_COMBO**|**OBM_REDUCED**|  
|**OBM_DNARROW**|**OBM_RESTORE**|  
|**OBM_DNARROWD**|**OBM_RESTORED**|  
|**OBM_DNARROWI**|**OBM_RGARROW**|  
|**OBM_LFARROW**|**OBM_RGARROWD**|  
|**OBM_LFARROWD**|**OBM_RGARROWI**|  
|**OBM_LFARROWI**|**OBM_SIZE**|  
|**OBM_MNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_CLOSE**|**OBM_UPARROWD**|  
|**OBM_OLD_DNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_LFARROW**|**OBM_ZOOM**|  
|**OBM_OLD_REDUCE**|**OBM_ZOOMD**|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Bitmap-Name mit beginnt **OBM_OLD** darstellen Bitmaps, die von Windows-Versionen vor 3.0 verwendet werden.  
  
 Beachten Sie, dass die Konstante **OEMRESOURCE** muss vor dem Einfügen von WINDOWS definiert werden. H, um das Verwenden der **OBM_** Konstanten.  
  
##  <a name="operator_hbitmap"></a>  CBitmap::operator HBITMAP  
 Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle Abrufen der `CBitmap` Objekt.  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CBitmap` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator wird ein Typumwandlungsoperator, die direkte Verwendung von unterstützt ein `HBITMAP` Objekt.  
  
 Weitere Informationen zum Verwenden von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) im Windows SDK.  
  
##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits  
 Legt die Bits einer Bitmap, die Bitwerten auf der Grundlage von *LpBits*.  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Parameter  
 *dwCount*  
 Gibt die Anzahl der Bytes, die durch *LpBits*.  
  
 *lpBits*  
 Verweist auf die **BYTE** Array, die Pixelwerte zum Kopieren enthält, der `CBitmap` Objekt. Damit für die Bitmap, damit das Bild ordnungsgemäß gerendert werden kann sollte die Werte formatiert werden, um die Höhe, Breite und Farbe Tiefenwerte entsprechen, die angegeben wurden, wenn die CBitmap-Instanz erstellt wurde. Weitere Informationen finden Sie unter [CBitmap::CreateBitmap](#createbitmap).  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die in der Einstellung der Bitmapbits verwendet; 0, wenn die Funktion fehlerhaft ist.  
  
##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension  
 Weist eine Breite und Höhe einer Bitmap in Einheiten von 0,1 Millimeter.  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 *nWidth*  
 Gibt die Breite der Bitmap (in Einheiten von 0,1-Millimeter).  
  
 *nHeight*  
 Gibt die Höhe der Bitmap (in Einheiten von 0,1-Millimeter).  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Bitmapdimensionen. Höhe ist der **cy** Membervariable der der `CSize` Objekt und die Breite befindet sich in der **Cx** Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Die GDI verwendet keinen dieser Werte mit Ausnahme von zum zurücksenden, wenn eine Anwendung ruft die [GetBitmapDimension](#getbitmapdimension) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

