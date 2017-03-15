---
title: CBitmap-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmap
dev_langs:
- C++
helpviewer_keywords:
- drawing, tools
- CBitmap class
- GDI bitmap
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
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
ms.openlocfilehash: ccfe592bbbae8c0eff22baa6e1baac56754ef6fc
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmap-class"></a>CBitmap-Klasse
Kapselt eine Bitmap der Windows GDI (Graphics Device Interface) und stellt Memberfunktionen zur Bearbeitung der Bitmap bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|Erstellt ein `CBitmap`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|Initialisiert das Objekt mit einer Bitmap, geräteabhängige Speicher, die über einer angegebenen Breite, Höhe und Bitmuster verfügt.|  
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Initialisiert das Objekt mit einer Bitmap mit der Breite, Höhe und Bitmuster (falls vorhanden) in einem **BITMAP** Struktur.|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Das Objekt mit einer Bitmap initialisiert, so dass er mit einem bestimmten Gerät kompatibel ist.|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Initialisiert das Objekt mit einer entfernbar Bitmap, die mit einem bestimmten Gerät kompatibel ist.|  
|[CBitmap::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CBitmap` Objekt, wenn ein Handle zu einem Windows angegebenen `HBITMAP` Bitmap.|  
|[CBitmap::GetBitmap](#getbitmap)|Füllt ein **BITMAP** Struktur mit Informationen über die Bitmap.|  
|[CBitmap::GetBitmapBits](#getbitmapbits)|Kopiert die Bits des angegebenen Bitmap in den angegebenen Puffer.|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Gibt die Breite und Höhe der Bitmap. Die Höhe und Breite werden als zuvor festgelegt wurde, indem Sie die [SetBitmapDimension](#setbitmapdimension) Member-Funktion.|  
|[LoadBitmap](#loadbitmap)|Initialisiert das Objekt von einer benannten Bitmap-Ressource von ausführbaren Datei der Anwendung geladen und Anfügen der Bitmap für das Objekt.|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Lädt eine Bitmap und aktuellen Systemfarben Farben zugeordnet.|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Initialisiert das Objekt durch eine vordefinierte Windows-Bitmap lädt und Anfügen der Bitmap für das Objekt.|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|Legt die Bits einer Bitmap auf die angegebenen Bits-Werte.|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Weist eine Breite und Höhe einer Bitmap in Einheiten von 0,1 Millimeter.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmap::operator HBITMAP](#operator_hbitmap)|Gibt das Windows-Handle an der der `CBitmap` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CBitmap` -Objekt, erstellen Sie das Objekt, von einer von der Initialisierung Memberfunktionen ein Bitmaphandle zuordnen und dann das Objekt Memberfunktionen aufrufen.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten wie `CBitmap`, finden Sie unter [Grafik Objekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecbitmapa--cbitmapcbitmap"></a><a name="cbitmap"></a>CBitmap::CBitmap  
 Erstellt ein `CBitmap`-Objekt.  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>Hinweise  
 Das resultierende Objekt muss mit einem der Memberfunktionen Initialisierung initialisiert werden.  
  
##  <a name="a-namecreatebitmapa--cbitmapcreatebitmap"></a><a name="createbitmap"></a>CBitmap::CreateBitmap  
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
 `nWidth`  
 Gibt die Breite der Bitmap (in Pixeln) an.  
  
 `nHeight`  
 Gibt die Höhe der Bitmap (in Pixeln) an.  
  
 `nPlanes`  
 Gibt die Anzahl von Farbebenen in der Bitmap an.  
  
 `nBitcount`  
 Gibt die Anzahl der Farbbits pro Anzeigepixel an.  
  
 `lpBits`  
 Zeigt auf ein Array von Bytes, das die ursprünglichen Bitwerte der Bitmap enthält. Ist dieser Wert **NULL**, bleibt die neue Bitmap nicht initialisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Für eine Farbbitmap muss entweder der `nPlanes` - oder `nBitcount` -Parameter auf 1 festgelegt werden. Wenn beide Parameter auf 1 festgelegt sind, erstellt `CreateBitmap` eine monochrome Bitmap.  
  
 Obwohl eine Bitmap direkt für ein Anzeigegerät aktiviert werden kann, es kann ausgewählt werden als die aktuelle Bitmap für eine "Speicher-Gerätekontext" mit [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) und kopiert alle kompatiblen Gerätekontext mithilfe der [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) Funktion.  
  
 Wenn Sie mit dem `CBitmap` -Objekt fertig sind, das von der `CreateBitmap` -Funktion erstellt wurde, wählen Sie zunächst die Bitmap im Gerätekontext aus, und löschen Sie dann das `CBitmap` -Objekt.  
  
 Weitere Informationen finden Sie unter der Beschreibung des **bmBits** -Felds der **BITMAP** -Struktur. Die [BITMAP](../../mfc/reference/bitmap-structure.md) Struktur wird beschrieben, unter der [CBitmap::CreateBitmapIndirect](#createbitmapindirect) Member-Funktion.  
  
##  <a name="a-namecreatebitmapindirecta--cbitmapcreatebitmapindirect"></a><a name="createbitmapindirect"></a>CBitmap::CreateBitmapIndirect  
 Initialisiert eine Bitmap, die die Breite, Höhe und Bitmuster (falls vorhanden), die in der Struktur auf den angegebenen `lpBitmap`.  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBitmap`  
 Verweist auf eine [BITMAP](../../mfc/reference/bitmap-structure.md) -Struktur, die Informationen über die Bitmap enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Obwohl eine Bitmap direkt für ein Anzeigegerät aktiviert werden kann, es kann ausgewählt werden als die aktuelle Bitmap für einen Gerätekontext Speicher mithilfe von [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) und kopiert alle kompatiblen Gerätekontext mithilfe der [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) oder [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) Funktion. (Die [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) Funktion kann direkt auf den Gerätekontext für die Anzeige die Bitmap für den aktuellen Pinsel kopieren.)  
  
 Wenn die **BITMAP** Struktur verweist die `lpBitmap` Parameter ausgefüllt ist, mithilfe der `GetObject` -Funktion, die Bits der Bitmap nicht angegeben werden und die Bitmap ist nicht initialisiert. Um die Bitmap zu initialisieren, eine Anwendung mithilfe eine Funktion wie [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) oder [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) zum Kopieren von Bits aus der Bitmap der erste Parameter der identifizierten `CGdiObject::GetObject` für die Bitmap erstellt `CreateBitmapIndirect`.  
  
 Wenn Sie fertig sind, mit der `CBitmap` mit erstelltes Objekt `CreateBitmapIndirect` funktioniert, wählen Sie die Bitmap aus den Gerätekontext zunächst Löschen der `CBitmap` Objekt.  
  
##  <a name="a-namecreatecompatiblebitmapa--cbitmapcreatecompatiblebitmap"></a><a name="createcompatiblebitmap"></a>CBitmap::CreateCompatibleBitmap  
 Initialisiert eine Bitmap, die mit dem angegebenen Gerät kompatibel ist `pDC`.  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Gibt den Gerätekontext.  
  
 `nWidth`  
 Gibt die Breite der Bitmap (in Pixeln) an.  
  
 `nHeight`  
 Gibt die Höhe der Bitmap (in Pixeln) an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap hat die gleiche Anzahl von Farbebenen oder das gleiche Bits pro Pixel-Format als den angegebenen Gerätekontext. Es kann ausgewählt werden, als die aktuelle Bitmap für alle Speicher-Geräte, die kompatibel mit der `pDC`.  
  
 Wenn `pDC` ein Gerätekontext Arbeitsspeicher wird die Bitmap zurückgegeben hat das gleiche Format wie die derzeit ausgewählte Bitmap in diesen Gerätekontext. Ein "Speicher-Gerätekontext" ist ein Speicherblock, der eine Anzeigeoberfläche darstellt. Hiermit können Sie Bilder im Arbeitsspeicher vor dem Kopieren der tatsächlichen Anzeigeoberfläche des kompatiblen Geräts vorbereiten.  
  
 Wenn ein Speicher-Gerätekontext erstellt wird, wählt GDI automatisch eine monochrome Bitmap für die vordefinierte dafür.  
  
 Da ein Farbe Speicher-Gerätekontext Farbe oder monochrome Bitmaps ausgewählt aufweisen kann, wird das Format der Bitmap zurückgegeben, durch die `CreateCompatibleBitmap` Funktion ist nicht immer identisch, ist jedoch das Format für einen Gerätekontext Panik eine kompatible Bitmap immer in das Format des Geräts.  
  
 Wenn Sie fertig sind, mit der `CBitmap` Objekt erstellt, mit der `CreateCompatibleBitmap` funktioniert, wählen Sie die Bitmap aus den Gerätekontext zunächst Löschen der `CBitmap` Objekt.  
  
##  <a name="a-namecreatediscardablebitmapa--cbitmapcreatediscardablebitmap"></a><a name="creatediscardablebitmap"></a>CBitmap::CreateDiscardableBitmap  
 Initialisiert eine entfernbare Bitmap, die mit den Gerätekontext identifizierten kompatibel ist `pDC`.  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Gibt einen Gerätekontext.  
  
 `nWidth`  
 Gibt die Breite der Bitmap (in Bits).  
  
 `nHeight`  
 Gibt die Höhe der Bitmap (in Bits).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap hat die gleiche Anzahl von Farbebenen oder das gleiche Bits pro Pixel-Format als den angegebenen Gerätekontext. Eine Anwendung kann diese Bitmap auswählen, als die aktuelle Bitmap für ein Speichergerät, die kompatibel mit der `pDC`.  
  
 Windows kann eine Bitmap, die von dieser Funktion nur erstellt, wenn eine Anwendung nicht in einen Anzeigekontext ausgewählt verwerfen. Wenn Windows die Bitmap verwirft, wenn diese Option nicht ausgewählt ist und die Anwendung später versucht, auf die Option der [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) Funktion zurück **NULL**.  
  
 Wenn Sie fertig sind, mit der `CBitmap` Objekt erstellt, mit der `CreateDiscardableBitmap` funktioniert, wählen Sie die Bitmap aus den Gerätekontext zunächst Löschen der `CBitmap` Objekt.  
  
##  <a name="a-namefromhandlea--cbitmapfromhandle"></a><a name="fromhandle"></a>CBitmap::FromHandle  
 Gibt einen Zeiger auf ein `CBitmap` Objekt, wenn ein Handle für ein Windows-GDI-Bitmap zu erhalten.  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `hBitmap`  
 Gibt eine Windows-GDI-Bitmap.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CBitmap` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CBitmap` Objekt noch nicht angefügt, das Handle zu einem temporären `CBitmap` Objekt erstellt und angefügt wird. Dieser temporäre `CBitmap` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner Ereignisschleife aufweist, zu der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass das temporäre Objekt nur während der Verarbeitung der Nachricht ein Fenster gültig ist.  
  
##  <a name="a-namegetbitmapa--cbitmapgetbitmap"></a><a name="getbitmap"></a>CBitmap::GetBitmap  
 Ruft die Eigenschaften für die angefügte Bitmap ab.  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitMap`  
 Zeiger auf eine [Bitmapstruktur](../../mfc/reference/bitmap-structure.md) -Struktur, die die Eigenschaften zu erhalten. Dieser Parameter darf nicht `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Methode erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetbitmapbitsa--cbitmapgetbitmapbits"></a><a name="getbitmapbits"></a>CBitmap::GetBitmapBits  
 Kopiert das Bitmuster der angefügten Bitmap in den angegebenen Puffer.  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwCount`  
 Die Anzahl von Bytes, die in den Puffer kopiert werden sollen.  
  
 `lpBits`  
 Zeiger auf den Puffer, der die Bitmap zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die in den Puffer kopiert werden, wenn die Methode erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBitmap::GetBitmap](#getbitmap) um die erforderliche Puffergröße zu ermitteln.  
  
##  <a name="a-namegetbitmapdimensiona--cbitmapgetbitmapdimension"></a><a name="getbitmapdimension"></a>CBitmap::GetBitmapDimension  
 Gibt die Breite und Höhe der Bitmap.  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite und Höhe der Bitmap, gemessen in Einheiten von 0,1 Millimeter. Die Höhe wird der **cy** Mitglied der `CSize` -Objekt, und die Breite befindet sich in der **Cx** Member. Wenn die Bitmap-Breite und Höhe nicht mithilfe von festgelegt wurde `SetBitmapDimension`, wird 0 zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe und Breite wird angenommen, dass zuvor mithilfe von festgelegt wurden die [SetBitmapDimension](#setbitmapdimension) Member-Funktion.  
  
##  <a name="a-nameloadbitmapa--cbitmaploadbitmap"></a><a name="loadbitmap"></a>LoadBitmap  
 Lädt die Bitmap-Ressource mit dem Namen `lpszResourceName` oder durch die ID-Nummer identifiziert `nIDResource` aus der ausführbaren Datei der Anwendung.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen der Bitmapressource enthält.  
  
 `nIDResource`  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die geladene Bitmap angefügt ist die `CBitmap` Objekt.  
  
 Wenn die Bitmap identifizierte `lpszResourceName` ist nicht vorhanden oder ist nicht genügend Arbeitsspeicher zum Laden der Bitmap, die Funktion gibt 0 zurück.  
  
 Können Sie die [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Funktion für das Löschen Bitmap geladen werden, indem die `LoadBitmap` -Funktion oder die `CBitmap` Destruktor wird das Objekt gelöscht, Sie.  
  
> [!CAUTION]
>  Bevor Sie das Objekt löschen, stellen Sie sicher, dass sie keinen Gerätekontext ausgewählt ist.  
  
 Die folgenden Bitmaps wurden in Windows-Versionen 3.1 und höher hinzugefügt:  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 Diese Bitmaps werden im Gerätetreiber für Windows-Versionen 3.0 und früheren Versionen nicht gefunden. Eine vollständige Liste von Bitmaps sowie eine Anzeige ihrer Darstellung, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameloadmappedbitmapa--cbitmaploadmappedbitmap"></a><a name="loadmappedbitmap"></a>CBitmap::LoadMappedBitmap  
 Rufen Sie diese Memberfunktion zum Laden einer Bitmaps und die aktuellen Systemfarben Farben zuordnen.  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDBitmap`  
 Die ID der Bitmapressource.  
  
 `nFlags`  
 Ein Flag für eine Bitmap. Kann NULL sein oder **CMB_MASKED**.  
  
 `lpColorMap`  
 Ein Zeiger auf eine **COLORMAP** Struktur, die Farbe für den benötigten Informationen ordnen Sie die Bitmaps enthält. Wenn dieser Parameter **NULL**, verwendet die Funktion die Standard-Farbschema.  
  
 *nMapSize*  
 Die Anzahl der Zuordnungen Farbe auf den `lpColorMap`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `LoadMappedBitmap` werden häufig in der Schaltfläche Symbole verwendete Farben zugeordnet.  
  
 Informationen zum Erstellen einer Bitmap zugeordneten, finden Sie im Windows-Funktion [CreateMappedBitmap](http://go.microsoft.com/fwlink/linkid=230562) und [COLORMAP](http://msdn.microsoft.com/library/windows/desktop/bb760448) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameloadoembitmapa--cbitmaploadoembitmap"></a><a name="loadoembitmap"></a>CBitmap::LoadOEMBitmap  
 Lädt eine vordefinierte Bitmap, die von Windows verwendet wird.  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDBitmap`  
 ID-Nummer der vordefinierten Windows-Bitmap. Von WINDOWS wird die möglichen Werte aufgeführt. H:  
  
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
 Bitmap-Namen beginnen mit **OBM_OLD** Bitmaps, die von Windows-Versionen vor 3.0 verwendet darstellen.  
  
 Beachten Sie, dass die Konstante **OEMRESOURCE** muss definiert werden, bevor Sie WINDOWS. H, um das Verwenden der **OBM_** Konstanten.  
  
##  <a name="a-nameoperatorhbitmapa--cbitmapoperator-hbitmap"></a><a name="operator_hbitmap"></a>CBitmap::operator HBITMAP  
 Verwenden Sie diesen Operator zum Abrufen der angefügten Windows GDI-Handle für die `CBitmap` Objekt.  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CBitmap` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Typumwandlungsoperator verwendet, die direkte Verwendung von unterstützt ein `HBITMAP` Objekt.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbitmapbitsa--cbitmapsetbitmapbits"></a><a name="setbitmapbits"></a>CBitmap::SetBitmapBits  
 Legt die Bits einer Bitmap für die Bitwerte von `lpBits`.  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCount`  
 Gibt die Anzahl der Bytes, die auf den `lpBits`.  
  
 `lpBits`  
 Verweist auf die **BYTE** Array, die Pixelwerte zum Kopieren enthält, der `CBitmap` Objekt. Damit für die Bitmap, damit das Bild ordnungsgemäß gerendert werden kann sollte die Werte formatiert werden, um die Höhe, Breite und Farbe Tiefenwerte entsprechen, die angegeben wurden, wenn die CBitmap-Instanz erstellt wurde. Weitere Informationen finden Sie unter [CBitmap::CreateBitmap](#createbitmap).  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die bei der Festlegung der Bitmap-Bits verwendet; 0, wenn die Funktion fehlschlägt.  
  
##  <a name="a-namesetbitmapdimensiona--cbitmapsetbitmapdimension"></a><a name="setbitmapdimension"></a>CBitmap::SetBitmapDimension  
 Weist eine Breite und Höhe einer Bitmap in Einheiten von 0,1 Millimeter.  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Gibt die Breite der Bitmap (in Einheiten von 0,1-Millimeter).  
  
 `nHeight`  
 Gibt die Höhe der Bitmap (in Einheiten von 0,1-Millimeter).  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Bitmapdimensionen. Höhe ist der **cy** Membervariable der der `CSize` -Objekt und die Breite befindet sich in der **Cx** Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Die GDI verwendet diese Werte bis zum zurücksenden, wenn eine Anwendung ruft nicht die [GetBitmapDimension](#getbitmapdimension) Member-Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


