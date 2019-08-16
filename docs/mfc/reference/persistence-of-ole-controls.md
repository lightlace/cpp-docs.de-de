---
title: Persistenz der OLE-Steuerelemente
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: 42e70f9e48339eddb2a5af4fa288400cce01f490
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502042"
---
# <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente

Eine Funktion von OLE-Steuerelementen ist die Eigenschafts Persistenz (oder Serialisierung), die es dem OLE-Steuerelement ermöglicht, Eigenschaftswerte in eine Datei oder einen Stream zu lesen oder zu schreiben. Eine Containeranwendung kann die Serialisierung verwenden, um die Eigenschaftswerte eines Steuer Elements zu speichern, auch nachdem die Anwendung das Steuerelement zerstört hat. Die Eigenschaftswerte des OLE-Steuer Elements können dann aus der Datei oder dem Datenstrom gelesen werden, wenn eine neue Instanz des Steuer Elements zu einem späteren Zeitpunkt erstellt wird.

### <a name="persistence-of-ole-controls"></a>Persistenz der OLE-Steuerelemente

|||
|-|-|
|[PX_Blob](#px_blob)|Tauscht eine Steuerelement Eigenschaft aus, die Binary Large Object (BLOB)-Daten speichert.|
|[PX_Bool](#px_bool)|Tauscht eine Steuerelement Eigenschaft vom Typ **bool**aus.|
|[PX_Color](#px_color)|Tauscht eine Farb Eigenschaft eines-Steuer Elements aus.|
|[PX_Currency](#px_currency)|Tauscht eine Steuerelement Eigenschaft des Typs **CY**aus.|
|[PX_DataPath](#px_datapath)|Tauscht eine Steuerelement Eigenschaft vom `CDataPathProperty`Typ aus.|
|[PX_Double](#px_double)|Tauscht eine Steuerelement Eigenschaft vom Typ **Double**aus.|
|[PX_Font](#px_font)|Tauscht eine Schriftart Eigenschaft eines-Steuer Elements aus.|
|[PX_Float](#px_float)|Tauscht eine Steuerelement Eigenschaft vom Typ **float**aus.|
|[PX_IUnknown](#px_iunknown)|Tauscht eine Steuerelement Eigenschaft von undefiniertem Typ aus.|
|[PX_Long](#px_long)|Tauscht eine Steuerelement Eigenschaft vom Typ **Long**aus.|
|[PX_Picture](#px_picture)|Tauscht eine Bild Eigenschaft eines-Steuer Elements aus.|
|[PX_Short](#px_short)|Tauscht eine Steuerelement Eigenschaft vom Typ **Short**aus.|
|[PX_ULong](#px_ulong)|Tauscht eine Steuerelement Eigenschaft vom Typ **ulong**aus.|
|[PX_UShort](#px_ushort)|Tauscht eine Steuerelement Eigenschaft vom Typ " **UShort**" aus.|
|[Pxstring](#px_string)|Tauscht eine Zeichen folgen-Steuerelement Eigenschaft aus.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|Tauscht die Schriftart bezogenen Eigenschaften eines VBX-Steuer Elements in eine Schriftart Eigenschaft des OLE-Steuer Elements aus.|

Außerdem wird die `AfxOleTypeMatchGuid` globale Funktion bereitgestellt, um eine Entsprechung zwischen einer TYPEDESC und einer angegebenen GUID zu testen.

##  <a name="px_blob"></a>PX_Blob

Sie können diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements zum Serialisieren oder Initialisieren einer Eigenschaft, die Binary Large Object (BLOB)-Daten speichert, abrufen.

```
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*hBlob*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*hBlobDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird von der Variablen, auf die von *hblob*verwiesen wird, gelesen oder in diese geschrieben. Diese Variable sollte mit NULL initialisiert werden, bevor Sie `PX_Blob` zum ersten Mal aufgerufen wird (in der Regel kann dies im Konstruktor des Steuer Elements erfolgen). Wenn *hblobdefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Initialisierungs-oder Serialisierungsprozess des-Steuer Elements aus irgendeinem Grund fehlschlägt.

Die Handles *hblob* und *hblobdefault* verweisen auf einen Speicherblock, der Folgendes enthält:

- Ein DWORD, das die Länge der folgenden Binärdaten (in Bytes) enthält, gefolgt von

- Ein Speicherblock, der die eigentlichen Binärdaten enthält.

Beachten Sie `PX_Blob` , dass beim Laden von BLOB-Typeigenschaften mithilfe der Windows [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) -API Arbeitsspeicher belegt. Sie sind dafür verantwortlich, diesen Arbeitsspeicher freizugeben. Daher sollte der Dekonstruktor des Steuer Elements [Global Free](/windows/win32/api/winbase/nf-winbase-globalfree) für alle Eigenschaften Handles des BLOB-Typs aufgerufen werden, um den Arbeitsspeicher freizugeben, der dem Steuerelement zugeordnet ist.

##  <a name="px_bool"></a>PX_Bool

Mit dieser Funktion innerhalb der Member- `DoPropExchange` Funktion des Steuer Elements können Sie eine Eigenschaft des Typs bool Serialisieren oder initialisieren.

```
BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue);

BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue,
    BOOL bDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*bValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*bDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird nach Bedarf aus der Variablen gelesen oder in diese geschrieben, auf die von *bvalue*verwiesen wird. Wenn *bdefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_color"></a>PX_Color

Mit dieser Funktion können Sie innerhalb der `DoPropExchange` Member-Funktion des Steuer Elements eine Eigenschaft vom Typ OLE_COLOR Serialisieren oder initialisieren.

```
BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue,
    OLE_COLOR clrDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*clrValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*clrDefault*<br/>
Der Standardwert für die Eigenschaft, wie vom Steuerelement Entwickler definiert.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird nach Bedarf aus der Variablen gelesen oder in diese geschrieben. Wenn *clrdefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_currency"></a>PX_Currency

Mit dieser Funktion innerhalb der Member- `DoPropExchange` Funktion des Steuer Elements können Sie eine Eigenschaft vom Typ **Currency**Serialisieren oder initialisieren.

```
BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue);

BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue,
    CY cyDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*cyValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*cyDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird in der Variablen, auf die von *cyvalue*verwiesen wird, gelesen oder in diese geschrieben. Wenn *cydefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_datapath"></a>PX_DataPath

Verwenden Sie diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements, um eine Daten Pfadeigenschaft des Typs " [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)" zu serialisieren oder zu initialisieren.

```
BOOL PX_DataPath(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CDataPathProperty& dataPathProperty);

BOOL PX_DataPath(
    CPropExchange* pPX,
    CDataPathProperty& dataPathProperty);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*dataPathProperty*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Daten Pfad Eigenschaften implementieren asynchrone Steuerelement Eigenschaften. Der Wert der Eigenschaft wird von der Variablen, auf die von *datapathproperty*verwiesen wird, gelesen oder in diese geschrieben.

##  <a name="px_double"></a>PX_Double

Sie können diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **Double**abrufen.

```
BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue);

BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue,
    double doubleDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*doubleValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*doubleDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird in der Variablen, auf die von *Double value*verwiesen wird, gelesen oder in diese geschrieben. Wenn *Double default* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_font"></a>PX_Font

Sie können diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ Schriftart abrufen.

```
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*font*<br/>
Ein Verweis auf ein `CFontHolder` -Objekt, das die Font-Eigenschaft enthält.

*pFontDesc*<br/>
Ein Zeiger auf eine `FONTDESC` -Struktur, die die Werte enthält, die beim Initialisieren des Standardstatus der Schriftart Eigenschaft verwendet werden sollen, falls *pfontdispambient* NULL ist.

*pFontDispAmbient*<br/>
Ein Zeiger auf die `IFontDisp` -Schnittstelle einer Schriftart, die beim Initialisieren des Standardstatus der Schriftart Eigenschaft verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird bei Bedarf aus einem `font` `CFontHolder` Verweis gelesen oder geschrieben. Wenn *pfontde SC* und *pfontdispambient* angegeben werden, werden Sie bei Bedarf zum Initialisieren des Standardwerts der Eigenschaft verwendet. Diese Werte werden verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt. In der Regel übergeben Sie NULL für *pfontbesc* und den von `COleControl::AmbientFont` zurückgegebenen Ambient-Wert für *pfontdispambient*. Beachten Sie, dass das von `COleControl::AmbientFont` zurückgegebene Schriftart Objekt durch einen-Rückruf der `IFontDisp::Release` Member-Funktion freigegeben werden muss.

##  <a name="px_float"></a>PX_Float

Sie können diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ " **float**" aufzurufen.

```
BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue);

BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue,
    float floatDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*floatValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*floatDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird in der Variablen, auf die von *floatvalue*verwiesen wird, gelesen oder in diese geschrieben. Wenn *floatdefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_iunknown"></a>PX_IUnknown

Aufrufen Sie diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements, um eine Eigenschaft zu serialisieren oder zu initialisieren `IUnknown`, die von einem-Objekt mit einer von abgeleiteten Schnittstelle

```
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*pUnk*<br/>
Verweis auf eine Variable, die die-Schnittstelle des-Objekts enthält, das den Wert der-Eigenschaft darstellt.

*iid*<br/>
Eine Schnittstellen-ID, die angibt, welche Schnittstelle des Eigenschafts Objekts vom Steuerelement verwendet wird.

*pUnkDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird in der Variablen, auf die von *Punk*verwiesen wird, gelesen oder in diese geschrieben. Wenn " *punkdefault* " angegeben ist, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_long"></a>PX_Long

Sie können diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **Long**abrufen.

```
BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue);

BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue,
    long lDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*lValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*lDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird nach Bedarf aus der Variablen gelesen oder in diesegeschrieben. Wenn " *ldefault* " angegeben ist, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_picture"></a>PX_Picture

Mit dieser Funktion innerhalb der Member- `DoPropExchange` Funktion des Steuer Elements können Sie eine Bild Eigenschaft des Steuer Elements Serialisieren oder initialisieren.

```
BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict);

BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict,
    CPictureHolder& pictDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*pict*<br/>
Verweis auf ein [CPictureHolder](../../mfc/reference/cpictureholder-class.md) -Objekt, in dem die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*pictDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird nach Bedarf aus der Variablen gelesen oder in diesegeschrieben. Wenn *pictdefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_short"></a>PX_Short

Sie können diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **Short**aufruft.

```
BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue);

BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue,
    short sDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*sValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*sDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird in der Variablen, auf die von *sValue*verwiesen wird, gelesen oder in diese geschrieben. Wenn *sdefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_ulong"></a>PX_ULong

Mit dieser Funktion innerhalb der Member- `DoPropExchange` Funktion des Steuer Elements können Sie eine Eigenschaft des Typs **ulong**Serialisieren oder initialisieren.

```
BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue);

BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue,
    long ulDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der auszutauschenden Eigenschaft.

*ulValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*ulDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird in der Variablen, auf die von *ULValue*verwiesen wird, gelesen oder in diese geschrieben. Wenn *uldefault* angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_ushort"></a>PX_UShort

Sie können diese Funktion innerhalb der Member `DoPropExchange` -Funktion des Steuer Elements zum Serialisieren oder Initialisieren einer Eigenschaft vom Typ **Ganzzahl ohne Vorzeichen Short**abrufen.

```
BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue);

BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue,
    USHORT usDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der auszutauschenden Eigenschaft.

*usValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*usDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird nach Bedarf aus der Variablen gelesen oder in diesegeschrieben. Wenn " *Standard* Wert" angegeben wird, wird er als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_string"></a>Pxstring

Mit dieser Funktion können Sie in der `DoPropExchange` Member-Funktion des Steuer Elements eine Zeichen folgen Eigenschaft serialisieren oder initialisieren.

```
BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue);

BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue,
    CString strDefault);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht wird.

*strValue*<br/>
Verweis auf die Variable, in der die Eigenschaft gespeichert ist (in der Regel eine Member-Variable ihrer Klasse).

*strDefault*<br/>
Der Standardwert für die-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft wird nach Bedarf aus der Variablen gelesen oder in diesegeschrieben. Wenn "- *Standard* " angegeben ist, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn der Serialisierungsprozess des Steuer Elements aus irgendeinem Grund fehlschlägt.

##  <a name="px_vbxfontconvert"></a>PX_VBXFontConvert

Mit dieser Funktion können Sie in der `DoPropExchange` Member-Funktion des Steuer Elements eine Schriftart Eigenschaft initialisieren, indem Sie die Schriftart bezogenen Eigenschaften eines VBX-Steuer Elements umrechnen.

```
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>Parameter

*pPX*<br/>
Zeiger auf das [CPropExchange](../../mfc/reference/cpropexchange-class.md) -Objekt (in der Regel als Parameter `DoPropExchange`an übergeben).

*font*<br/>
Die Font-Eigenschaft des OLE-Steuer Elements, die die konvertierten VBX-Schriftart bezogenen Eigenschaften enthalten soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Austausch erfolgreich war. 0, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur von einem OLE-Steuerelement verwendet werden, das als direkter Ersatz für ein VBX-Steuerelement konzipiert ist. Wenn in der Visual Basic Entwicklungsumgebung ein Formular mit einem VBX-Steuerelement konvertiert wird, um das entsprechende Replace OLE-Steuerelement zu `IDataObject::SetData` verwenden, wird die-Funktion des Steuer Elements aufgerufen und ein Eigenschaften Satz übergeben, der die Eigenschaften Daten des VBX-Steuer Elements enthält. Dieser Vorgang bewirkt wiederum, dass die `DoPropExchange` Funktion des Steuer Elements aufgerufen wird. `DoPropExchange`kann aufgerufen `PX_VBXFontConvert` werden, um die Schriftart bezogenen Eigenschaften des VBX-Steuer Elements (z. b. FontName, "FontSize" usw.) in die entsprechenden Komponenten der Schriftart Eigenschaft des OLE-Steuer Elements zu konvertieren.

`PX_VBXFontConvert`sollte nur aufgerufen werden, wenn das Steuerelement tatsächlich von einer VBX-Formular Anwendung konvertiert wird. Beispiel:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md)
