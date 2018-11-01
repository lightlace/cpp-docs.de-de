---
title: CPropExchange-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
ms.openlocfilehash: 772388d069bdec274bd396b776d404711b694771
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560370"
---
# <a name="cpropexchange-class"></a>CPropExchange-Klasse

Unterstützt die Implementierung der Dauerhaftigkeit für die OLE-Steuerelemente.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|Tauscht die Eigenschaft ein großes Binärobjekt (BLOB).|
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Tauscht eine Font-Eigenschaft.|
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Tauscht eine Eigenschaft zwischen einem Steuerelement und eine Datei an.|
|[CPropExchange::ExchangeProp](#exchangeprop)|Tauscht die Eigenschaften eines beliebigen integrierten Typs.|
|[CPropExchange::ExchangeVersion](#exchangeversion)|Tauscht die Versionsnummer eines OLE-Steuerelements.|
|[CPropExchange::GetVersion](#getversion)|Ruft die Versionsnummer eines OLE-Steuerelements ab.|
|[CPropExchange::IsAsynchronous](#isasynchronous)|Bestimmt, ob die Eigenschaft Austausch asynchron durchgeführt werden.|
|[CPropExchange::IsLoading](#isloading)|Gibt an, ob die Eigenschaften werden in das Steuerelement geladen oder gespeichert werden, aus.|

## <a name="remarks"></a>Hinweise

`CPropExchange` eine Basisklasse keinen.

Legt den Kontext und die Richtung von den Austausch einer Eigenschaft an.

Persistenz ist der Austausch von Informationen des Steuerelements, in der Regel durch die Eigenschaften, zwischen dem Steuerelement selbst und einem mittleren dargestellt.

Das Framework erstellt ein Objekt, die von abgeleiteten `CPropExchange` Wenn sie darüber benachrichtigt wird, dass ein OLE-Steuerelement-Eigenschaften sind, geladen werden oder gespeicherten in den persistenten Speicher.

Das Framework übergibt einen Zeiger auf diese `CPropExchange` -Objekt des Steuerelements `DoPropExchange` Funktion. Wenn Sie einen Assistenten verwendet haben, erstellen Sie die Ausgangsdateien für des Steuerelements, das Steuerelement des `DoPropExchange` Funktionsaufrufe `COleControl::DoPropExchange`. Die Basisklassenversion tauscht vordefinierten Eigenschaften des Steuerelements; Ändern Sie die abgeleitete Klasse-Version, um Eigenschaften von Exchange, dass Sie das Steuerelement hinzugefügt haben.

`CPropExchange` kann zum Serialisieren von Eigenschaften eines Steuerelements, oder Initialisieren der Eigenschaften eines Steuerelements, nach dem Laden oder die Erstellung eines Steuerelements verwendet werden. Die `ExchangeProp` und `ExchangeFontProp` Memberfunktionen der `CPropExchange` können Eigenschaften zum Speichern und sie von einem anderen Medium zu laden.

Weitere Informationen zur Verwendung von `CPropExchange`, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CPropExchange`

## <a name="requirements"></a>Anforderungen

**Header:** afxctl.h

##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp

Serialisiert eine Eigenschaft, die binary large Object (BLOB)-Daten gespeichert.

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>Parameter

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht werden.

*phBlob*<br/>
Zeiger auf eine Variable, die auf, in dem die Eigenschaft gespeichert wird (Variable in der Regel ist ein Member der Klasse).

*hBlobDefault*<br/>
Der Standardwert für die Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.

### <a name="remarks"></a>Hinweise

Der Wert der Eigenschaft von geschrieben oder daraus gelesen, je nach Bedarf die Variable verweist, zu *PhBlob*. Wenn *hBlobDefault* angegeben ist, er wird als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn aus irgendeinem Grund des Steuerelements Serialisierung ein Fehler auftritt.

Die Funktionen `CArchivePropExchange::ExchangeBlobProp`, `CResetPropExchange::ExchangeBlobProp`, und `CPropsetPropExchange::ExchangeBlobProp` außer Kraft setzen diese rein virtuelle Funktion.

##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp

Tauscht eine Font-Eigenschaft zwischen einem Speichermedium und das Steuerelement an.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>Parameter

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht werden.

*Schriftart*<br/>
Ein Verweis auf eine [CFontHolder](../../mfc/reference/cfontholder-class.md) -Objekt, das die Schriftarteigenschaft enthält.

*pFontDesc*<br/>
Ein Zeiger auf eine [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc) Struktur, die Werte zum Initialisieren der Standardzustand der Font-Eigenschaft bei *pFontDispAmbient* ist NULL.

*pFontDispAmbient*<br/>
Ein Zeiger auf die `IFontDisp` Schnittstelle einer Schriftart zum Initialisieren der Standardzustand der Font-Eigenschaft verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.

### <a name="remarks"></a>Hinweise

Wenn die Font-Eigenschaft von dem Datenträger für das Steuerelement geladen wird, werden Schriftmerkmale abgerufen, von dem Datenträger und die `CFontHolder` Objekt, auf *Schriftart* wird initialisiert, indem sie. Wenn sich die Schriftarteigenschaft gespeichert wird, werden die Eigenschaften in die Schriftartobjekt, das Medium geschrieben.

Die Funktionen `CArchivePropExchange::ExchangeFontProp`, `CResetPropExchange::ExchangeFontProp`, und `CPropsetPropExchange::ExchangeFontProp` außer Kraft setzen diese rein virtuelle Funktion.

##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp

Tauscht eine Eigenschaft zwischen dem Steuerelement und eine Datei an.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>Parameter

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht werden.

*ppUnk*<br/>
Ein Zeiger auf eine Variable, die einen Zeiger auf die der Eigenschaft enthält `IUnknown` Schnittstelle (diese Variable ist in der Regel ein Member der Klasse).

*IID*<br/>
Schnittstellen-ID der Schnittstelle, für die Eigenschaft, die das Steuerelement verwendet.

*pUnkDefault*<br/>
Der Standardwert für die Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.

### <a name="remarks"></a>Hinweise

Wenn die Eigenschaft aus der Datei an das Steuerelement geladen wird, wird die Eigenschaft erstellt und initialisiert aus der Datei. Wenn die Eigenschaft gespeichert wird, wird der Wert in die Datei geschrieben.

Die Funktionen `CArchivePropExchange::ExchangePersistentProp`, `CResetPropExchange::ExchangePersistentProp`, und `CPropsetPropExchange::ExchangePersistentProp` außer Kraft setzen diese rein virtuelle Funktion.

##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp

Tauscht die eine Eigenschaft zwischen einem Speichermedium und Steuerelement.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>Parameter

*pszPropName*<br/>
Der Name der Eigenschaft, die ausgetauscht werden.

*vtProp*<br/>
Ein Symbol, die den Typ der Eigenschaft, die ausgetauscht werden. Dabei sind folgende Werte möglich:

|Symbol|Eigenschaftentyp|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_BOOL|**BOOL**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**float**|
|VT_R8|**double**|

*pvProp*<br/>
Ein Zeiger auf den Wert der Eigenschaft.

*pvDefault*<br/>
Zeiger auf einen Standardwert für die Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn der Vorgang fehlschlägt.

### <a name="remarks"></a>Hinweise

Wenn die Eigenschaft von dem Datenträger für das Steuerelement geladen wird, den Wert der Eigenschaft von dem Datenträger abgerufen und gespeichert, in dem Objekt verweist *PvProp*. Wenn die Eigenschaft auf dem-Medium gespeichert wird, der Wert des Objekts verweist *PvProp* an das Medium geschrieben wird.

Die Funktionen `CArchivePropExchange::ExchangeProp`, `CResetPropExchange::ExchangeProp`, und `CPropsetPropExchange::ExchangeProp` außer Kraft setzen diese rein virtuelle Funktion.

##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion

Wird aufgerufen, durch das Framework um Persistenz der eine Versionsnummer zu behandeln.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>Parameter

*dwVersionLoaded*<br/>
Verweis auf eine Variable, in dem die Versionsnummer der die zu ladenden persistenten Daten gespeichert werden.

*dwVersionDefault*<br/>
Die aktuelle Versionsnummer des Steuerelements.

*bConvert*<br/>
Gibt an, ob permanente Daten auf die aktuelle Version konvertiert, oder behalten sie die gleiche Version, die geladen wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

##  <a name="getversion"></a>  CPropExchange::GetVersion

Rufen Sie diese Funktion, um die Versionsnummer des Steuerelements abzurufen.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Rückgabewert

Die Versionsnummer des Steuerelements.

##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous

Bestimmt, ob die Eigenschaft Austausch asynchron durchgeführt werden.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true", wenn Eigenschaften sind ausgetauscht asynchron ist, andernfalls "false".

##  <a name="isloading"></a>  CPropExchange::IsLoading

Mit dieser Funktion können Sie bestimmen, ob die Eigenschaften werden für das Steuerelement geladen oder aus dem es gespeichert.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn Eigenschaften geladen werden; andernfalls 0.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)

