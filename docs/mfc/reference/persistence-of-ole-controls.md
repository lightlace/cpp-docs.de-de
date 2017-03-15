---
title: Persistenz der OLE-Steuerelemente | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
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
ms.openlocfilehash: b8bbf72a1ea16b37dabf88c5d41a34b1a03ba0d1
ms.lasthandoff: 02/24/2017

---
# <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente
Eine Funktion von OLE-Steuerelementen wird Persistenz (oder Serialisierung), wodurch das OLE-Steuerelement zum Lesen oder Schreiben von Eigenschaftswerten in und aus einer Datei oder einem Stream. Eine Steuerelementcontainer-Anwendung können Serialisierung um Eigenschaftswerte des Steuerelements zu speichern, auch nachdem die Anwendung das Steuerelement zerstört wurde. Die Eigenschaftswerte des OLE-Steuerelements können Sie dann aus der Datei gelesen werden, oder Datenstrom, wenn eine neue Instanz des Steuerelements zu einem späteren Zeitpunkt erstellt wird.  
  
### <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|Tauscht eine Steuerelementeigenschaft, die binary large Object (BLOB)-Daten speichert.|  
|[PX_Bool](#px_bool)|Tauscht die Eigenschaft eines Steuerelements vom Typ **BOOL**.|  
|[PX_Color](#px_color)|Tauscht die Color-Eigenschaft eines Steuerelements.|  
|[PX_Currency](#px_currency)|Tauscht die Eigenschaft eines Steuerelements vom Typ **CY**.|  
|[PX_DataPath](#px_datapath)|Tauscht die Eigenschaft eines Steuerelements vom Typ `CDataPathProperty`.|  
|[PX_Double](#px_double)|Tauscht die Eigenschaft eines Steuerelements vom Typ **doppelte**.|  
|[PX_Font](#px_font)|Tauscht eine Font-Eigenschaft eines Steuerelements an.|  
|[PX_Float](#px_float)|Tauscht die Eigenschaft eines Steuerelements vom Typ **Float**.|  
|[PX_IUnknown](#px_iunknown)|Tauscht die Eigenschaft eines Steuerelements eines undefinierten Typs.|  
|[PX_Long](#px_long)|Tauscht die Eigenschaft eines Steuerelements vom Typ **lang**.|  
|[PX_Picture](#px_picture)|Tauscht eine Picture-Eigenschaft eines Steuerelements an.|  
|[PX_Short](#px_short)|Tauscht die Eigenschaft eines Steuerelements vom Typ **kurze**.|  
|[PX_ULong](#px_ulong)|Tauscht die Eigenschaft eines Steuerelements vom Typ **ULONG**.|  
|[PX_UShort](#px_ushort)|Tauscht die Eigenschaft eines Steuerelements vom Typ **USHORT**.|  
|[PXstring](#px_string)|Tauscht eine Zeichenfolgeneigenschaft des Steuerelements Zeichen.|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|Tauscht ein VBX-Steuerelement Schriftarteigenschaften in eine OLE-Steuerelementeigenschaft Schriftart an.|  
  
 Darüber hinaus die `AfxOleTypeMatchGuid` globale Funktion wird bereitgestellt, um eine Übereinstimmung zwischen Testen einer `TYPEDESC` und einer angegebenen GUID.  
  
##  <a name="a-namepxbloba--pxblob"></a><a name="px_blob"></a>PX_Blob  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft, die binary large Object (BLOB)-Daten gespeichert.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `hBlob`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `hBlobDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft lesen oder auf die Variable, auf die verwiesen wird geschrieben `hBlob`nach Bedarf. Diese Variable initialisiert werden soll, um **NULL** vor dem ersten Aufrufen `PX_Blob` zum ersten Mal (in der Regel hierzu im Konstruktor des Steuerelements). Wenn `hBlobDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund das Steuerelement Initialisierung oder Serialisierung fehlschlägt.  
  
 Die Handles `hBlob` und `hBlobDefault` finden Sie in einen Speicherblock, der Folgendes enthält:  
  
-   Ein `DWORD` die Länge in Bytes, der Binärdaten enthält, die verwendet wird, unmittelbar gefolgt von  
  
-   Ein Speicherblock, der die Binärdaten enthält.  
  
 Beachten Sie, dass `PX_Blob` wird Arbeitsspeicher zuweisen, mit dem Windows [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) -API, die beim Laden von Eigenschaften vom Typ BLOB. Sie sind verantwortlich für die Freigabe dieser Speicher. Der Destruktor des Steuerelements sollte daher Aufrufen [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) in einer beliebigen Eigenschaft vom Typ BLOB einrichten Handles für freien Arbeitsspeicher, der dem Steuerelement zugeordnet.  
  
##  <a name="a-namepxboola--pxbool"></a><a name="px_bool"></a>PX_Bool  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **BOOL**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `bValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `bDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft lesen oder auf die Variable, auf die verwiesen wird geschrieben `bValue`nach Bedarf. Wenn `bDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxcolora--pxcolor"></a><a name="px_color"></a>PX_Color  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **OLE_COLOR**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `clrValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `clrDefault`  
 Der Standardwert für die Eigenschaft, die vom Entwickler Steuerelements definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft lesen oder auf die Variable, auf die verwiesen wird geschrieben `clrValue`nach Bedarf. Wenn `clrDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxcurrencya--pxcurrency"></a><a name="px_currency"></a>PX_Currency  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **Währung**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `cyValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `cyDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft lesen oder auf die Variable, auf die verwiesen wird geschrieben `cyValue`nach Bedarf. Wenn `cyDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxdatapatha--pxdatapath"></a><a name="px_datapath"></a>PX_DataPath  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder initialisieren eine Datenpfad-Eigenschaft des Typs [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `dataPathProperty`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Pfadeigenschaften Daten implementieren asynchroner Steuerelementeigenschaften. Der Wert der Eigenschaft lesen oder auf die Variable, auf die verwiesen wird geschrieben `dataPathProperty`nach Bedarf.  
  
##  <a name="a-namepxdoublea--pxdouble"></a><a name="px_double"></a>PX_Double  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **doppelte**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `doubleValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `doubleDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird `doubleValue`nach Bedarf. Wenn `doubleDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxfonta--pxfont"></a><a name="px_font"></a>PX_Font  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` Memberfunktion Serialisieren oder eine Eigenschaft vom Typ Schriftart zu initialisieren.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `font`  
 Ein Verweis auf ein `CFontHolder` -Objekt, das die Font-Eigenschaft enthält.  
  
 `pFontDesc`  
 Ein Zeiger auf eine **FONTDESC** Struktur, die die Werte verwenden, initialisieren Sie den Standardzustand der Font-Eigenschaft, in dem Fall, in dem `pFontDispAmbient` ist **NULL**.  
  
 `pFontDispAmbient`  
 Ein Zeiger auf die **IFontDisp** Schnittstelle einer Schriftart zu verwenden, initialisieren Sie den Standardzustand der Font-Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben `font`, `CFontHolder` -Verweis, wenn erforderlich. Wenn `pFontDesc` und `pFontDispAmbient` angegeben sind, werden zum Initialisieren der Eigenschaft Standardwert, bei Bedarf. Diese Werte werden verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt. Übergeben Sie i. d. r. **NULL** für `pFontDesc` und den der Rückgabewert von `COleControl::AmbientFont` für `pFontDispAmbient`. Hinweis, der das Font-Objekt zurückgegebene `COleControl::AmbientFont` müssen freigegeben werden, durch einen Aufruf der **IFontDisp::Release** Member-Funktion.  
  
##  <a name="a-namepxfloata--pxfloat"></a><a name="px_float"></a>PX_Float  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` Memberfunktion Serialisieren oder Initialisieren einer Eigenschaft vom Typ **Float**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `floatValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `floatDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird `floatValue`nach Bedarf. Wenn `floatDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxiunknowna--pxiunknown"></a><a name="px_iunknown"></a>PX_IUnknown  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` Memberfunktion Serialisieren oder Initialisieren einer Eigenschaft dargestellte Objekt mit einer **IUnknown**-Schnittstelle abgeleitet.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *pUnk*  
 Verweis auf eine Variable, die mit der Schnittstelle des Objekts, das den Wert der Eigenschaft darstellt.  
  
 `iid`  
 Eine Schnittstellen-ID, der angibt, welche Schnittstelle des Property-Objekts wird vom Steuerelement verwendet.  
  
 `pUnkDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird *pUnk*nach Bedarf. Wenn `pUnkDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxlonga--pxlong"></a><a name="px_long"></a>PX_Long  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **lang**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `lValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `lDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird `lValue`nach Bedarf. Wenn `lDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxpicturea--pxpicture"></a><a name="px_picture"></a>PX_Picture  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder eine Picture-Eigenschaft des Steuerelements zu initialisieren.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `pict`  
 Ein Verweis auf eine [CPictureHolder](../../mfc/reference/cpictureholder-class.md) Objekt, in dem die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `pictDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird `pict`nach Bedarf. Wenn `pictDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxshorta--pxshort"></a><a name="px_short"></a>PX_Short  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **kurze**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `sValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `sDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird `sValue`nach Bedarf. Wenn `sDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxulonga--pxulong"></a><a name="px_ulong"></a>PX_ULong  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ **ULONG**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `ulValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `ulDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird `ulValue`nach Bedarf. Wenn `ulDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxushorta--pxushort"></a><a name="px_ushort"></a>PX_UShort  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` -Memberfunktion, die serialisiert oder Initialisieren einer Eigenschaft vom Typ `unsigned` **kurze**.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *usValue*  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 *usDefault*  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird *UsValue*nach Bedarf. Wenn *UsDefault* angegeben ist, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxstringa--pxstring"></a><a name="px_string"></a>PXstring  
 Rufen Sie diese Funktion innerhalb des Steuerelements **DoPropExchange** -Memberfunktion, die serialisiert oder eine Zeichenfolgeneigenschaft Zeichen zu initialisieren.  
  
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
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `strValue`  
 Verweis auf die Variable, in die Eigenschaft gespeichert ist (in der Regel eine Membervariable der Klasse).  
  
 `strDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, um die Variable, auf die verwiesen wird `strValue`nach Bedarf. Wenn `strDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="a-namepxvbxfontconverta--pxvbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert  
 Rufen Sie diese Funktion innerhalb des Steuerelements `DoPropExchange` Memberfunktion Font-Eigenschaft, die durch Konvertieren eines VBX-Steuerelements Schriftarteigenschaften initialisiert werden.  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter übergeben `DoPropExchange`).  
  
 `font`  
 Die Font-Eigenschaft des OLE-Steuerelements, das den konvertierten VBX Schriftarteigenschaften enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur von OLE-Steuerelement verwendet werden, die als direkter Ersatz für ein VBX-Steuerelement dient. Der Visual Basic-Entwicklungsumgebung ein Formular mit einem VBX-Steuerelement zum Verwenden der entsprechenden Ersatz OLE-Steuerelement konvertiert, rufen Sie des Steuerelements **IDataObject::SetData** -Funktion übergeben einen Eigenschaftensatz, der VBX-Steuerelement die Daten enthält. Dieser Vorgang wiederum führt dazu, dass des Steuerelements `DoPropExchange` Funktion aufgerufen werden. `DoPropExchange`erreichen `PX_VBXFontConvert` VBX-Steuerelement Schriftarteigenschaften konvertieren (z. B. "FontName" "FontSize", usw.) in die entsprechenden Komponenten der Font-Eigenschaft des OLE-Steuerelements.  
  
 `PX_VBXFontConvert`sollte nur aufgerufen werden, wenn das Steuerelement tatsächlich aus einer VBX-Form-Anwendung konvertiert wird. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCActiveXControl&14;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl&#15;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

