---
title: Persistenz der OLE-Steuerelemente | Microsoft-Dokumentation
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
ms.openlocfilehash: f07efa6ebbea70f83803238bf73e2d3e806ea457
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204568"
---
# <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente
Eine Funktion der OLE-Steuerelemente ist Persistenz (oder Serialisierung), wodurch die OLE-Steuerelements, das Lesen und Schreiben von Eigenschaftswerten in und aus einer Datei oder den Stream. Eine Container-Anwendung kann die Serialisierung verwenden, um Eigenschaftswerte des Steuerelements zu speichern, auch nachdem die Anwendung das Steuerelement gelöscht wurde. Die Eigenschaftswerte des OLE-Steuerelements können Sie dann aus der Datei gelesen werden, oder Stream, wenn eine neue Instanz des Steuerelements zu einem späteren Zeitpunkt erstellt wird.  
  
### <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|Tauscht die Eigenschaft eines Steuerelements, in der binary large Object (BLOB)-Daten gespeichert.|  
|[PX_Bool](#px_bool)|Tauscht die Eigenschaft eines Steuerelements vom Typ **"bool"**.|  
|[PX_Color](#px_color)|Tauscht eine Color-Eigenschaft eines Steuerelements an.|  
|[PX_Currency](#px_currency)|Tauscht die Eigenschaft eines Steuerelements vom Typ **CY**.|  
|[PX_DataPath](#px_datapath)|Tauscht die Eigenschaft eines Steuerelements vom Typ `CDataPathProperty`.|  
|[PX_Double](#px_double)|Tauscht die Eigenschaft eines Steuerelements vom Typ **doppelte**.|  
|[PX_Font](#px_font)|Tauscht eine Font-Eigenschaft eines Steuerelements an.|  
|[PX_Float](#px_float)|Tauscht die Eigenschaft eines Steuerelements vom Typ **"float"**.|  
|[PX_IUnknown](#px_iunknown)|Tauscht die eine Steuerelementeigenschaft eines undefinierten Typs.|  
|[PX_Long](#px_long)|Tauscht die Eigenschaft eines Steuerelements vom Typ **lange**.|  
|[PX_Picture](#px_picture)|Tauscht eine Picture-Eigenschaft eines Steuerelements an.|  
|[PX_Short](#px_short)|Tauscht die Eigenschaft eines Steuerelements vom Typ **kurze**.|  
|[PX_ULong](#px_ulong)|Tauscht die Eigenschaft eines Steuerelements vom Typ **ULONG**.|  
|[PX_UShort](#px_ushort)|Tauscht die Eigenschaft eines Steuerelements vom Typ **USHORT**.|  
|[PXstring](#px_string)|Tauscht die eine Steuerelementeigenschaft für Zeichen-Zeichenfolge.|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|Tauscht schriftartbezogene Eigenschaften eines VBX-Steuerelements in eine OLE-Steuerelementeigenschaft Schriftart an.|  
  
 Darüber hinaus die `AfxOleTypeMatchGuid` globale Funktion wird bereitgestellt, um nach einer Übereinstimmung zwischen TYPEDESC und einer angegebenen GUID zu testen.  
  
##  <a name="px_blob"></a>  PX_Blob  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder eine Eigenschaft, die speichert binary large Object (BLOB)-Daten zu initialisieren.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *hBlob*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *hBlobDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft wird gelesen oder geschrieben werden, auf die verwiesen wird, indem Sie Variable *hBlob*je nach Bedarf. Diese Variable sollte vor dem ersten Aufrufen auf NULL initialisiert werden `PX_Blob` zum ersten Mal (in der Regel, dies kann erfolgen im Konstruktor des Steuerelements). Wenn *hBlobDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund des Steuerelements Initialisierungs- oder Serialisierungswerte Prozess ein Fehler auftritt.  
  
 Die Handles *hBlob* und *hBlobDefault* finden Sie in einen Speicherblock, die Folgendes enthält:  
  
-   Ein DWORD, der die Länge in Bytes, der Binärdaten, die folgt enthält, unmittelbar gefolgt von  
  
-   Ein Speicherblock, der die Binärdaten enthält.  
  
 Beachten Sie, dass `PX_Blob` wird Arbeitsspeicher zuweisen, mit der Windows [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) -API, die beim Laden von Eigenschaften des BLOB-Typ. Sie sind verantwortlich für das Freigeben dieses Speichers. Aus diesem Grund sollte der Destruktor des Steuerelements aufrufen [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) auf einer beliebigen BLOB-Type-Eigenschaft Handles für kostenlose zu Ihrem Steuerelement zugewiesener Speicher einrichten.  
  
##  <a name="px_bool"></a>  PX_Bool  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zu serialisierenden bzw. zu eine Eigenschaft vom Typ "bool" zu initialisieren.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *bValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *bStandardstufe*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft wird gelesen oder geschrieben werden, auf die verwiesen wird, indem Sie Variable *bValue*je nach Bedarf. Wenn *bStandardstufe* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_color"></a>  PX_Color  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder eine Eigenschaft des Typs OLE_COLOR zu initialisieren.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *clrValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *clrDefault*  
 Der Standardwert für die Eigenschaft, die vom Entwickler Steuerelements definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft wird gelesen oder geschrieben werden, auf die verwiesen wird, indem Sie Variable *ClrValue*je nach Bedarf. Wenn *ClrDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_currency"></a>  PX_Currency  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **Währung**.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *cyValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *cyDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft wird gelesen oder geschrieben werden, auf die verwiesen wird, indem Sie Variable *CyValue*je nach Bedarf. Wenn *CyDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_datapath"></a>  PX_DataPath  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder initialisieren eine Datenpfad-Eigenschaft des Typs [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *dataPathProperty*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Pfadeigenschaften Daten implementieren asynchroner Steuerelementeigenschaften. Der Wert der Eigenschaft wird gelesen oder geschrieben werden, auf die verwiesen wird, indem Sie Variable *DataPathProperty*je nach Bedarf.  
  
##  <a name="px_double"></a>  PX_Double  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **doppelte**.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *doubleValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *doubleDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *DoubleValue*je nach Bedarf. Wenn *DoubleDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_font"></a>  PX_Font  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder eine Eigenschaft der TrueType-Schriftart zu initialisieren.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *Schriftart*  
 Ein Verweis auf eine `CFontHolder` -Objekt, das die Schriftarteigenschaft enthält.  
  
 *pFontDesc*  
 Ein Zeiger auf eine `FONTDESC` Struktur, die die Werte beim Initialisieren der Standardzustand der Font-Eigenschaft, in dem Fall verwendet, in denen *pFontDispAmbient* ist NULL.  
  
 *pFontDispAmbient*  
 Ein Zeiger auf die `IFontDisp` Schnittstelle eines Fonts, verwenden Sie in den Standardzustand der Font-Eigenschaft zu initialisieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben `font`, `CFontHolder` verweisen, bei Bedarf. Wenn *pFontDesc* und *pFontDispAmbient* angegeben sind, werden sie zum Initialisieren der Standardwert der Eigenschaft, bei Bedarf verwendet werden. Diese Werte werden verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt. In der Regel, übergeben Sie NULL für *pFontDesc* und der ambient-Wert von zurückgegebenen `COleControl::AmbientFont` für *pFontDispAmbient*. Beachten Sie, die von der Font-Objekt zurückgegeben `COleControl::AmbientFont` müssen freigegeben werden, durch einen Aufruf der `IFontDisp::Release` Member-Funktion.  
  
##  <a name="px_float"></a>  PX_Float  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **"float"**.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *floatValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *floatDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *FloatValue*je nach Bedarf. Wenn *FloatDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_iunknown"></a>  PX_IUnknown  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft dargestellt wird, indem Sie ein Objekt eine `IUnknown`-Schnittstelle abgeleitet.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *pUnk*  
 Verweis auf eine Variable, enthält die Schnittstelle des Objekts, das den Wert der Eigenschaft darstellt.  
  
 *IID*  
 Eine Schnittstellen-ID, der angibt, welche Schnittstelle des Eigenschaftenobjekts vom Steuerelement verwendet wird.  
  
 *pUnkDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *pUnk*je nach Bedarf. Wenn *pUnkDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_long"></a>  PX_Long  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **lange**.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *l-Wert*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *lDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *lValue*je nach Bedarf. Wenn *lDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_picture"></a>  PX_Picture  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder eine Bildeigenschaft des Steuerelements zu initialisieren.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *PICT*  
 Ein Verweis auf eine [CPictureHolder](../../mfc/reference/cpictureholder-class.md) Objekt, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *pictDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *Pict*je nach Bedarf. Wenn *PictDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_short"></a>  PX_Short  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **kurze**.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *sValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *sDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *sValue*je nach Bedarf. Wenn *sDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_ulong"></a>  PX_ULong  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **ULONG**.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *ulValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *ulDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *UlValue*je nach Bedarf. Wenn *UlDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_ushort"></a>  PX_UShort  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **unsigned short**.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *usValue*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *usDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *UsValue*je nach Bedarf. Wenn *UsDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_string"></a>  PXstring  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion, die zum Serialisieren oder eine Zeichenfolgeneigenschaft Zeichen zu initialisieren.  
  
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
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *pszPropName*  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 *strValue gespeichert*  
 Verweis auf die Variable, in dem die Eigenschaft gespeichert wird (in der Regel eine Membervariable der Klasse).  
  
 *strDefault*  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben werden, auf die Variable verweist *StrValue*je nach Bedarf. Wenn *StrDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund Serialisierungsprozess des Steuerelements ein Fehler auftritt.  
  
##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert  
 Mit dieser Funktion wird innerhalb des Steuerelements `DoPropExchange` Memberfunktion eine Font-Eigenschaft, die durch die Konvertierung eines VBX-Steuerelements schriftartbezogene Eigenschaften initialisiert werden.  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>Parameter  
 *pPX*  
 Zeiger auf die [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt (i. d. r. als Parameter an übergeben `DoPropExchange`).  
  
 *Schriftart*  
 Die Schriftarteigenschaft des OLE-Steuerelements, die die konvertierte VBX Schriftarteigenschaften enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur von OLE-Steuerelements verwendet werden, die als direkte Ersatz für ein Steuerelement VBX entwickelt wurde. Wenn die Visual Basic-Entwicklungsumgebung ein Formular mit einem VBX-Steuerelements zur Verwendung von OLE-Steuerelements über der entsprechenden Ersetzung konvertiert, wird es des Steuerelements aufrufen `IDataObject::SetData` Funktion auf und übergibt in einem Eigenschaftensatz, der Eigenschaftendaten der VBX-Steuerelements enthält. Dieser Vorgang wiederum des Steuerelements `DoPropExchange` Funktion aufgerufen werden. `DoPropExchange` Aufrufen `PX_VBXFontConvert` schriftartbezogene Eigenschaften des VBX-Steuerelements zu konvertieren (z. B. "FontName" "FontSize", usw.) in die entsprechenden Komponenten der Font-Eigenschaft des OLE-Steuerelements.  
  
 `PX_VBXFontConvert` sollte nur aufgerufen werden, wenn das Steuerelement tatsächlich aus einer Anwendung der VBX-Format konvertiert wird. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
