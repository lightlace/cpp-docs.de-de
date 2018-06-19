---
title: Persistenz der OLE-Steuerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e84e26bae83bd131b53d10e4561ddb60854a8a5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378333"
---
# <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente
Eine Funktion der OLE-Steuerelemente ist Eigenschaft Persistenz (oder Serialisierung), womit die OLE-Steuerelements zum Lesen oder Schreiben von Eigenschaftswerten in und aus einer Datei oder einem Stream. Eine Steuerelementcontainer-Anwendung kann die Serialisierung verwenden, zum Speichern von Eigenschaftswerten für ein Steuerelement, auch nachdem die Anwendung das Steuerelement zerstört wurde. Die Eigenschaftswerte des OLE-Steuerelements können dann aus der Datei gelesen werden, oder Stream, wenn eine neue Instanz des Steuerelements zu einem späteren Zeitpunkt erstellt wird.  
  
### <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|Tauscht eine Steuerelementeigenschaft, die binary large Object (BLOB)-Daten gespeichert.|  
|[PX_Bool](#px_bool)|Tauscht die Eigenschaft eines Steuerelements vom Typ **BOOL**.|  
|[PX_Color](#px_color)|Tauscht eine Color-Eigenschaft eines Steuerelements an.|  
|[PX_Currency](#px_currency)|Tauscht die Eigenschaft eines Steuerelements vom Typ **CY**.|  
|[PX_DataPath](#px_datapath)|Tauscht die Eigenschaft eines Steuerelements vom Typ `CDataPathProperty`.|  
|[PX_Double](#px_double)|Tauscht die Eigenschaft eines Steuerelements vom Typ **doppelte**.|  
|[PX_Font](#px_font)|Tauscht eine Schriftarteigenschaft eines Steuerelements an.|  
|[PX_Float](#px_float)|Tauscht die Eigenschaft eines Steuerelements vom Typ **"float"**.|  
|[PX_IUnknown](#px_iunknown)|Tauscht eine Steuerelementeigenschaft eines undefinierten Typs an.|  
|[PX_Long](#px_long)|Tauscht die Eigenschaft eines Steuerelements vom Typ **lang**.|  
|[PX_Picture](#px_picture)|Tauscht eine Picture-Eigenschaft eines Steuerelements an.|  
|[PX_Short](#px_short)|Tauscht die Eigenschaft eines Steuerelements vom Typ **kurze**.|  
|[PX_ULong](#px_ulong)|Tauscht die Eigenschaft eines Steuerelements vom Typ **ULONG**.|  
|[PX_UShort](#px_ushort)|Tauscht die Eigenschaft eines Steuerelements vom Typ **"ushort"**.|  
|[PXstring](#px_string)|Tauscht eine Zeichenfolgeneigenschaft des Steuerelements Zeichen.|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|Tauscht schriftartbezogene Eigenschaften eines VBX-Steuerelements in eine OLE-Steuerelementeigenschaft Schriftart an.|  
  
 Darüber hinaus die `AfxOleTypeMatchGuid` globale Funktion wird bereitgestellt, um nach einer Übereinstimmung zwischen Testen einer `TYPEDESC` und einer angegebenen GUID.  
  
##  <a name="px_blob"></a>  PX_Blob  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft, die binary large Object (BLOB)-Daten gespeichert.  
  
```  
 
BOOL  
PX_Blob(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    HGLOBAL& 
hBlob  ,  
    HGLOBAL 
hBlobDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `hBlob`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `hBlobDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft aus gelesen oder geschrieben werden, auf die Variable verweist werden `hBlob`je nach Bedarf. Diese Variable muss erst initialisiert werden **NULL** vor dem ersten Aufrufen `PX_Blob` zum ersten Mal (in der Regel hierzu im Konstruktor des Steuerelements). Wenn `hBlobDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Initialisierung oder der Serialisierung des Steuerelements-Prozess ein Fehler auftritt.  
  
 Die Handles `hBlob` und `hBlobDefault` finden Sie in einen Speicherblock, die Folgendes enthält:  
  
-   Ein `DWORD` die Länge in Bytes, der Binärdaten enthält, das folgt, folgen unmittelbar  
  
-   Ein Speicherblock, der die binären Daten enthält.  
  
 Beachten Sie, dass `PX_Blob` belegt Arbeitsspeicher mithilfe der Windowsfunktion [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) -API, die beim Laden der BLOB-Typ-Eigenschaften. Sie sind verantwortlich für die Freigabe dieser Arbeitsspeicher. Der Destruktor des Steuerelements sollte daher Aufrufen [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) für alle BLOB-Type-Eigenschaft einrichten Handles für freien Arbeitsspeicher, der dem Steuerelement zugeordnet.  
  
##  <a name="px_bool"></a>  PX_Bool  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **BOOL**.  
  
```  
 
BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& bValue);

BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& 
bValue  ,  
    BOOL bDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `bValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `bDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft aus gelesen oder geschrieben werden, auf die Variable verweist werden `bValue`je nach Bedarf. Wenn `bDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_color"></a>  PX_Color  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **OLE_COLOR**.  
  
```  
 
BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& 
clrValue  ,  
    OLE_COLOR 
clrDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `clrValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `clrDefault`  
 Der Standardwert für die Eigenschaft, die vom Entwickler Steuerelements definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft aus gelesen oder geschrieben werden, auf die Variable verweist werden `clrValue`je nach Bedarf. Wenn `clrDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_currency"></a>  PX_Currency  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **Währung**.  
  
```  
 
BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& cyValue);

BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& 
cyValue  ,  
    CY cyDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `cyValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `cyDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft aus gelesen oder geschrieben werden, auf die Variable verweist werden `cyValue`je nach Bedarf. Wenn `cyDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_datapath"></a>  PX_DataPath  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder initialisieren eine Datenpfad-Eigenschaft des Typs [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).  
  
```  
 
BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    LPCTSTR 
pszPropName,  
    CDataPathProperty& dataPathProperty);

BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    CDataPathProperty& dataPathProperty);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `dataPathProperty`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Pfad der Dateneigenschaften implementieren asynchrone Steuerelementeigenschaften. Den Wert der Eigenschaft aus gelesen oder geschrieben werden, auf die Variable verweist werden `dataPathProperty`je nach Bedarf.  
  
##  <a name="px_double"></a>  PX_Double  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **doppelte**.  
  
```  
 
BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& doubleValue);

BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& 
doubleValue  ,  
    double doubleDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `doubleValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `doubleDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist `doubleValue`je nach Bedarf. Wenn `doubleDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_font"></a>  PX_Font  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder eine Eigenschaft des Typs Schriftart zu initialisieren.  
  
```  
 
BOOL  
PX_Font(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CFontHolder& 
font  ,  
    const 
FONTDESC  
FAR* 
pFontDesc  
= 
NULL,  
    LPFONTDISP 
pFontDispAmbient  
= NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `font`  
 Ein Verweis auf ein `CFontHolder` Objekt, das die Schriftarteigenschaft enthält.  
  
 `pFontDesc`  
 Ein Zeiger auf eine **FONTDESC** Struktur, enthält die Werte, die beim Initialisieren der Standardzustand der Font-Eigenschaft, in die Groß-/Kleinschreibung verwendet, in denen `pFontDispAmbient` ist **NULL**.  
  
 `pFontDispAmbient`  
 Ein Zeiger auf die **IFontDisp** Schnittstelle einer Schriftart beim Initialisieren der Standardzustand der Font-Eigenschaft verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben `font`ein `CFontHolder` verweisen, wenn erforderlich. Wenn `pFontDesc` und `pFontDispAmbient` angegeben sind, werden sie zum Initialisieren der Eigenschaft Standardwert, bei Bedarf verwendet. Diese Werte werden verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt. Übergeben Sie in der Regel **NULL** für `pFontDesc` und den Ambiente-Rückgabewert durch `COleControl::AmbientFont` für `pFontDispAmbient`. Beachten Sie, die von der Schriftartobjekt zurückgegeben `COleControl::AmbientFont` müssen freigegeben werden, durch einen Aufruf der **IFontDisp::Release** Memberfunktion.  
  
##  <a name="px_float"></a>  PX_Float  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **"float"**.  
  
```  
 
BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& floatValue);

BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& 
floatValue  ,  
    float floatDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `floatValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `floatDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist `floatValue`je nach Bedarf. Wenn `floatDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_iunknown"></a>  PX_IUnknown  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` zu serialisierenden bzw. zu initialisieren eine Eigenschaft dargestellt wird, indem ein-Objekt ist, dessen Memberfunktion eine **IUnknown**-Schnittstelle abgeleitet.  
  
```  
 
BOOL  
PX_IUnknown(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    LPUNKNOWN& 
pUnk  ,  
    REFIID 
iid  ,  
    LPUNKNOWN 
pUnkDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *pUnk*  
 Verweis auf eine Variable, enthält die Schnittstelle des Objekts, das den Wert der Eigenschaft darstellt.  
  
 `iid`  
 Eine Schnittstellen-ID, der angibt, welche Schnittstelle des Eigenschaftenobjekts vom Steuerelement verwendet wird.  
  
 `pUnkDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *pUnk*je nach Bedarf. Wenn `pUnkDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_long"></a>  PX_Long  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **lang**.  
  
```  
 
BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& lValue);

BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& 
lValue  ,  
    long lDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `lValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `lDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist `lValue`je nach Bedarf. Wenn `lDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_picture"></a>  PX_Picture  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion zu serialisierenden bzw. eine Bildeigenschaft des Steuerelements zu initialisieren.  
  
```  
 
BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& pict);

BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& 
pict  ,  
    CPictureHolder& pictDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `pict`  
 Ein Verweis auf eine [CPictureHolder](../../mfc/reference/cpictureholder-class.md) Objekt, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `pictDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist `pict`je nach Bedarf. Wenn `pictDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_short"></a>  PX_Short  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **kurze**.  
  
```  
 
BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& sValue);

BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& 
sValue  ,  
    short sDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `sValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `sDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist `sValue`je nach Bedarf. Wenn `sDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_ulong"></a>  PX_ULong  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **ULONG**.  
  
```  
 
BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& ulValue);

BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& 
ulValue  ,  
    long ulDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `ulValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `ulDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist `ulValue`je nach Bedarf. Wenn `ulDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_ushort"></a>  PX_UShort  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ `unsigned` **kurze**.  
  
```  
 
BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& usValue);

BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& 
usValue  ,  
    USHORT usDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *usValue*  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 *usDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *UsValue*je nach Bedarf. Wenn *UsDefault* angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_string"></a>  PXstring  
 Mit dieser Funktion werden innerhalb des Steuerelements **DoPropExchange** Memberfunktion, die serialisiert oder eine Zeichenfolgeneigenschaft Zeichen zu initialisieren.  
  
```  
 
BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& strValue);

BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& 
strValue  ,  
    CString strDefault);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `strValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `strDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Den Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist `strValue`je nach Bedarf. Wenn `strDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess für das Steuerelement ein Fehler auftritt.  
  
##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert  
 Mit dieser Funktion werden innerhalb des Steuerelements `DoPropExchange` Memberfunktion eine Schriftarteigenschaft, die durch Konvertieren eines Steuerelements VBX Schriftarteigenschaften initialisiert.  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 `font`  
 Die Schriftarteigenschaft des OLE-Steuerelements, die die konvertierten VBX schriftartbezogene Eigenschaften enthalten soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur von OLE-Steuerelements verwendet werden, die als direkter Ersatz für ein Steuerelement VBX entwickelt wurde. Wenn die Visual Basic-Entwicklungsumgebung konvertiert werden, ein Formular, das ein VBX-Steuerelement, um die entsprechenden Ersetzung OLE-Steuerelements verwenden, rufen Sie des Steuerelements **IDataObject::SetData** -Funktion übergeben, die in einer Eigenschaft festlegen, die enthält Daten, die VBX-Steuerelement-Eigenschaft. Dieser Vorgang wiederum führt dazu, dass des Steuerelements `DoPropExchange` Funktion, die aufgerufen werden. `DoPropExchange` Aufrufen `PX_VBXFontConvert` VBX-Steuerelement Schriftarteigenschaften konvertieren (z. B. "FontName," "FontSize," usw.) in die entsprechenden Komponenten von Font-Eigenschaft des OLE-Steuerelements.  
  
 `PX_VBXFontConvert` sollte nur aufgerufen werden, wenn das Steuerelement aus einer Form-Anwendung VBX tatsächlich konvertiert wird. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
