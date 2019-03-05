---
title: Eigenschaftenseiten (MFC)
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
ms.openlocfilehash: e2f75044c7cfbc1f9d2af1d9bda5c108f9afa881
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269213"
---
# <a name="property-pages-mfc"></a>Eigenschaftenseiten (MFC)

Eigenschaftenseiten werden die aktuellen Werte von bestimmten Eigenschaften der OLE-Steuerelements in einer anpassbaren, grafische Schnittstelle zum Anzeigen und bearbeiten, die durch die Unterstützung einer datenzuordnung Authentifizierungsmechanismus auf Grundlage der Dialogdatenaustausch (DDX) angezeigt.

Dieser Mechanismus für die datenzuordnung ordnet Steuerelemente der Seite Eigenschaft, die einzelnen Eigenschaften des OLE-Steuerelements. Der Wert der Steuerelementeigenschaft spiegelt wider, den Status oder den Inhalt des Eigenschaft-Steuerelement. Die Zuordnung zwischen Eigenschaften und Steuerelemente der Seite Eigenschaft wird angegeben, indem **DDP_** Funktionsaufrufe, die auf der Eigenschaftenseite `DoDataExchange` Member-Funktion. Im folgenden finden eine Liste der **DDP_** Funktionen, die exchange-Daten, die eingegeben wird, über die Eigenschaftenseite des Steuerelements:

### <a name="property-page-data-transfer"></a>Eigenschaft-Seite-Datenübertragung

|||
|-|-|
|[DDP_CBIndex](#ddp_cbindex)|Verknüpft die ausgewählte Zeichenfolge Index in einem Kombinationsfeld mit der Eigenschaft eines Steuerelements an.|
|[DDP_CBString](#ddp_cbstring)|Verknüpft die ausgewählte Zeichenfolge in einem Kombinationsfeld mit der Eigenschaft eines Steuerelements an. Die ausgewählte Zeichenfolge kann mit den Buchstaben des Eigenschaftswerts beginnen jedoch nicht vollständig Übereinstimmung.|
|[DDP_CBStringExact](#ddp_cbstringexact)|Verknüpft die ausgewählte Zeichenfolge in einem Kombinationsfeld mit der Eigenschaft eines Steuerelements an. Die ausgewählte Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|
|[DDP_Check](#ddp_check)|Verknüpft ein Kontrollkästchen des Steuerelements auf der Seite mit der Eigenschaft eines Steuerelements an.|
|[DDP_LBIndex](#ddp_lbindex)|Verknüpft die ausgewählte Zeichenfolge Index in einem Listenfeld mit der Eigenschaft eines Steuerelements an.|
|[DDP_LBString](#ddp_lbstring)|Verknüpft die ausgewählte Zeichenfolge in ein Listenfeld mit der Eigenschaft eines Steuerelements an. Die ausgewählte Zeichenfolge kann mit den Buchstaben des Eigenschaftswerts beginnen jedoch muss nicht vollständig damit übereinstimmen.|
|[DDP_LBStringExact](#ddp_lbstringexact)|Verknüpft die ausgewählte Zeichenfolge in ein Listenfeld mit der Eigenschaft eines Steuerelements an. Die ausgewählte Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|
|[DDP_PostProcessing](#ddp_postprocessing)|Beendet die Übertragung von Eigenschaftswerten über das Steuerelement an.|
|[DDP_Radio](#ddp_radio)|Links eine Gruppe von Optionsfeldern des Steuerelements auf der Seite mit der Eigenschaft eines Steuerelements.|
|[DDP_Text](#ddp_text)|Verknüpft ein Steuerelement des Steuerelements auf der Seite mit der Eigenschaft eines Steuerelements an. Diese Funktion behandelt die verschiedene Arten von Eigenschaften, z. B. **doppelte**, **kurze**, BSTR, und **lange**.|

Weitere Informationen zu den `DoDataExchange` -Funktion oder auf den Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).

Im folgenden finden eine Liste der Makros, die zum Erstellen und Verwalten von Eigenschaftenseiten für OLE-Steuerelements:

### <a name="property-pages"></a>Eigenschaftenseiten

|||
|-|-|
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|Beginnt die Liste der Eigenschaftenseiten-IDs an.|
|[END_PROPPAGEIDS](#end_proppageids)|Die Liste der Eigenschaftenseiten-IDs wird beendet.|
|[PROPPAGEID](#proppageid)|Deklariert eine Eigenschaftenseite der Steuerelement-Klasse.|

##  <a name="ddp_cbindex"></a>  DDP_CBIndex

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Ganzzahleigenschaft mit dem Index der aktuellen Auswahl in einem Kombinationsfeld auf der Eigenschaftenseite zu synchronisieren.

```
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Ressourcen-ID des Kombinationsfeld-Feld der Eigenschaft des Steuerelements anhand des zugeordneten Steuerelements *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname der Steuerelementeigenschaft mit dem Kombinationsfeld-Steuerelement, das vom angegebenen ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_CBIndex` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_cbstring"></a>  DDP_CBString

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft mit der aktuellen Auswahl in einem Kombinationsfeld auf der Eigenschaftenseite zu synchronisieren.

```
void AFXAPI DDP_CBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Ressourcen-ID des Kombinationsfeld-Feld der Eigenschaft des Steuerelements anhand des zugeordneten Steuerelements *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname der Steuerelementeigenschaft mit dem angegebenen Combo Box Zeichenfolge ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_CBString` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_cbstringexact"></a>  DDP_CBStringExact

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft zu synchronisieren, die die aktuelle Auswahl in einem Kombinationsfeld auf der Eigenschaftenseite genau übereinstimmt.

```
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Ressourcen-ID des Kombinationsfeld-Feld der Eigenschaft des Steuerelements anhand des zugeordneten Steuerelements *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname der Steuerelementeigenschaft mit dem angegebenen Combo Box Zeichenfolge ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_CBStringExact` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_check"></a>  DDP_Check

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` Funktion, um den Wert der Eigenschaft mit dem zugeordneten Eigenschaft Seite das Kontrollkästchen-Steuerelement zu synchronisieren.

```
void AFXAPI DDP_Check(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Ressourcen-ID des Kontrollkästchen-Steuerelements verknüpft ist, mit der Eigenschaft des Steuerelements gemäß *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname der Steuerelementeigenschaft mit dem Kontrollkästchen-Steuerelement, das anhand des ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_Check` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_lbindex"></a>  DDP_LBIndex

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Ganzzahleigenschaft mit dem Index der aktuellen Auswahl in einem Listenfeld auf der Eigenschaftenseite zu synchronisieren.

```
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Liste die Ressourcen-ID-Feld der Eigenschaft des Steuerelements anhand des zugeordneten Steuerelements *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname, der der Eigenschaft des Steuerelements mit der angegebenen Liste Feld Zeichenfolge ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_LBIndex` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_lbstring"></a>  DDP_LBString

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft mit der aktuellen Auswahl in einem Listenfeld auf der Eigenschaftenseite zu synchronisieren.

```
void AFXAPI DDP_LBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Liste die Ressourcen-ID-Feld der Eigenschaft des Steuerelements anhand des zugeordneten Steuerelements *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname, der der Eigenschaft des Steuerelements mit der angegebenen Liste Feld Zeichenfolge ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_LBString` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_lbstringexact"></a>  DDP_LBStringExact

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft zu synchronisieren, die die aktuelle Auswahl in einem Listenfeld auf der Eigenschaftenseite genau übereinstimmt.

```
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Liste die Ressourcen-ID-Feld der Eigenschaft des Steuerelements anhand des zugeordneten Steuerelements *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname, der der Eigenschaft des Steuerelements mit der angegebenen Liste Feld Zeichenfolge ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_LBStringExact` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_postprocessing"></a>  DDP_PostProcessing

Rufen Sie diese Funktion in Ihr Eigenschaftenseite `DoDataExchange` -Funktion verwendet, um die Übertragung von Eigenschaftswerten auf der Eigenschaftenseite zu Ihrem Steuerelement Fertig stellen, wenn Eigenschaftswerte gespeichert werden.

```
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, wenn Sie alle Dialogdatenaustausch-Funktionen durchgeführt haben. Zum Beispiel:

[!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_radio"></a>  DDP_Radio

Rufen Sie diese Funktion des Steuerelements `DoPropExchange` Funktion, um den Wert der Eigenschaft mit der zugehörigen Eigenschaft Seite Optionsfeld-Steuerelement zu synchronisieren.

```
void AFXAPI DDP_Radio(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Ressourcen-ID des Optionsfelds Schaltflächen-Steuerelement, die der Eigenschaft des Steuerelements anhand des zugeordneten *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname, der der Eigenschaft des Steuerelements mit das Optionsfeld-Steuerelement gemäß ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_Radio` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="ddp_text"></a>  DDP_Text

Rufen Sie diese Funktion des Steuerelements `DoDataExchange` Funktion, um den Wert der Eigenschaft mit dem Steuerelement zugeordnete Eigenschaft zu synchronisieren.

```
void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    BYTE & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    UINT & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    long & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    DWORD & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    float & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    double & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    CString & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*ID*<br/>
Die Ressourcen-ID des Steuerelements mit der Eigenschaft des Steuerelements anhand des verknüpften *PszPropName*.

*member*<br/>
Die Membervariable, die das Eigenschaftensteuerelement-Seite anhand des zugeordneten *Id* und durch die angegebene Eigenschaft *PszPropName*.

*pszPropName*<br/>
Der Eigenschaftenname der Steuerelementeigenschaft mit dem vom angegebenen Steuerelement ausgetauscht werden sollen *Id*.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, ehe die entsprechende `DDX_Text` Funktionsaufruf.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="begin_proppageids"></a>  BEGIN_PROPPAGEIDS

Beginn der Definition Ihres Steuerelements-Liste der Eigenschaftenseiten-IDs an.

```
BEGIN_PROPPAGEIDS(class_name,  count)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name des der Control-Klasse, die für die Eigenschaft Seiten angegeben werden.

*count*<br/>
Die Anzahl der Seiten, die von der Control-Klasse verwendet.

### <a name="remarks"></a>Hinweise

Klicken Sie in der Implementierungsdatei (.cpp), die die Member-Funktionen für die Klasse definiert, starten Sie die Eigenschaftenliste für die Seite mit dem BEGIN_PROPPAGEIDS-Makro, und klicken Sie dann fügen Sie die Makroeinträge für jede Eigenschaft, und schließen Sie die Eigenschaftenliste für die Seite mit den END_PROPPAGEIDS -Makro.

Weitere Informationen zu Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="end_proppageids"></a>  END_PROPPAGEIDS

Beendet die Definition der Eigenschaft Seite ID enthalten.

```
END_PROPPAGEIDS(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name der Steuerelement-Klasse, die auf der Seite der besitzt.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="proppageid"></a>  PROPPAGEID

Fügt eine Eigenschaftenseite für die Verwendung durch das OLE-Steuerelement hinzu.

```
PROPPAGEID(clsid)
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Die eindeutige Klasse-ID einer Eigenschaftenseite.

### <a name="remarks"></a>Hinweise

Alle PROPPAGEID-Makros müssen zwischen die BEGIN_PROPPAGEIDS und END_PROPPAGEIDS-Makros in der Implementierungsdatei des Steuerelements platziert werden.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
