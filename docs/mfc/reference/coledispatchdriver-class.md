---
title: COleDispatchDriver-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
ms.openlocfilehash: fa88147b57b0506f7f9ab96d4a5d2f43fdd75458
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504181"
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver-Klasse

Implementiert die Clientseite der OLE-Automatisierung.

## <a name="syntax"></a>Syntax

```
class COleDispatchDriver
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Erstellt ein `COleDispatchDriver`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|Fügt eine `IDispatch` Verbindung mit dem `COleDispatchDriver` -Objekt an.|
|[COleDispatchDriver::CreateDispatch](#createdispatch)|Erstellt eine `IDispatch` Verbindung und fügt Sie an das `COleDispatchDriver` -Objekt an.|
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Trennt eine `IDispatch` Verbindung, ohne sie freizugeben.|
|[COleDispatchDriver::GetProperty](#getproperty)|Ruft eine Automatisierungs Eigenschaft ab.|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|Hilfsobjekt zum Aufrufen von Automatisierungsmethoden.|
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Gibt eine `IDispatch` Verbindung frei.|
|[COleDispatchDriver::SetProperty](#setproperty)|Legt eine Automatisierungs Eigenschaft fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::operator =](#operator_eq)|Kopiert den Quellwert in das `COleDispatchDriver` -Objekt.|
|[COleDispatchDriver:: Operator lpdispatch](#operator_lpdispatch)|Greift auf den `IDispatch` zugrunde liegenden Zeiger zu.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|Gibt an, ob die `IDispatch` während `ReleaseDispatch` -oder Objekt Zerstörung freigegeben werden soll.|
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|Gibt den Zeiger auf die `IDispatch` -Schnittstelle an `COleDispatchDriver`, die diesem zugeordnet ist.|

## <a name="remarks"></a>Hinweise

`COleDispatchDriver`weist keine Basisklasse auf.

OLE Dispatch-Schnittstellen ermöglichen den Zugriff auf die Methoden und Eigenschaften eines Objekts. Element Funktionen von `COleDispatchDriver` anfügen, trennen, erstellen und Freigeben einer dispatchverbindung vom Typ `IDispatch`. Andere Element Funktionen verwenden Variablen Argumentlisten zum Vereinfachen des `IDispatch::Invoke`Aufrufs von.

Diese Klasse kann direkt verwendet werden. Sie wird jedoch im Allgemeinen nur von Klassen verwendet, die vom Assistenten zum Hinzufügen von Klassen erstellt werden. Wenn Sie neue C++ Klassen erstellen, indem Sie eine Typbibliothek importieren, werden die neuen Klassen `COleDispatchDriver`von abgeleitet.

Weitere Informationen zur Verwendung von `COleDispatchDriver`finden Sie in den folgenden Artikeln:

- [Automatisierungsclients](../../mfc/automation-clients.md)

- [Automatisierungsserver](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`COleDispatchDriver`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="attachdispatch"></a>COleDispatchDriver:: attachdispatch

Rufen Sie die `AttachDispatch` -Memberfunktion auf, um dem `IDispatch` -Objekt einen `COleDispatchDriver` -Zeiger anzufügen. Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parameter

*lpDispatch*<br/>
Zeiger auf ein `IDispatch` -OLE-Objekt, der an das `COleDispatchDriver` -Objekt angefügt werden soll.

*bAutoRelease*<br/>
Gibt an, ob die Verteilung freigegeben werden soll, wenn dieses Objekt den Gültigkeitsbereich verlässt.

### <a name="remarks"></a>Hinweise

Diese Funktion gibt alle `IDispatch` -Zeiger zurück, die dem `COleDispatchDriver` -Objekt bereits angefügt wurden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>COleDispatchDriver:: COleDispatchDriver

Erstellt ein `COleDispatchDriver`-Objekt.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parameter

*lpDispatch*<br/>
Zeiger auf ein `IDispatch` -OLE-Objekt, der an das `COleDispatchDriver` -Objekt angefügt werden soll.

*bAutoRelease*<br/>
Gibt an, ob die Verteilung freigegeben werden soll, wenn dieses Objekt den Gültigkeitsbereich verlässt.

*dispatchSrc*<br/>
Verweis auf ein vorhandenes `COleDispatchDriver` -Objekt.

### <a name="remarks"></a>Hinweise

Das Formular `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) verbindet die [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)-Schnittstelle.

Das Formular `COleDispatchDriver`( **konstant**`COleDispatchDriver`&  `COleDispatchDriver` ) kopiert ein vorhandenes Objekt und erhöht den Verweis Zähler.`dispatchSrc`

Das Formular `COleDispatchDriver`() erstellt ein `COleDispatchDriver` -Objekt, stellt jedoch keine `IDispatch` Verbindung mit der-Schnittstelle her. Vor der `COleDispatchDriver`Verwendung von () ohne Argumente sollten Sie eine `IDispatch` mit entweder mit [COleDispatchDriver::](#createdispatch) up-oder [COleDispatchDriver:: attachdispatch](#attachdispatch)verbinden. Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

### <a name="example"></a>Beispiel

  Siehe dazu das Beispiel für [COleDispatchDriver::CreateDispatch](#createdispatch).

##  <a name="createdispatch"></a>COleDispatchDriver:: up-Dispatch

Erstellt ein [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) -Schnittstellenobjekt und fügt es zum `COleDispatchDriver` -Objekt hinzu.

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Die Klassen-ID, des zu erstellenden `IDispatch` -Verbindungsobjekts.

*pError*<br/>
Ein Zeiger auf ein OLE-Ausnahmeobjekt, das den Statuscode aufnimmt, der sich durch die Erstellung ergibt.

*lpszProgID*<br/>
Ein Zeiger auf den programmgesteuerten Bezeichner, z. B. „Excel.Document.5“, des Automatisierungsobjekts, für das das Dispatch-Objekt erstellt werden soll.

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>COleDispatchDriver::D etachdispatch

Trennt die aktuelle `IDispatch` Verbindung von diesem-Objekt.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das zuvor angefügte `IDispatch` OLE-Objekt.

### <a name="remarks"></a>Hinweise

Die `IDispatch` wird nicht freigegeben.

Weitere Informationen zum lpdispatch-Typ finden Sie unter [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

##  <a name="getproperty"></a>COleDispatchDriver:: GetProperty

Ruft die von *dwdispid*angegebene Objekt Eigenschaft ab.

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Eigenschaft an, die abgerufen werden soll.

*vtProp*<br/>
Gibt die Eigenschaft an, die abgerufen werden soll. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](#invokehelper).

*pvProp*<br/>
Adresse der Variablen, die den Eigenschafts Wert empfängt. Er muss mit dem von *vtprop*angegebenen Typ identisch sein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

##  <a name="invokehelper"></a>COleDispatchDriver:: InvokeHelper

Ruft die von *dwdispid*angegebene Objektmethode oder-Eigenschaft in dem durch *wFlags*angegebenen Kontext auf.

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Bezeichnet die aufzurufende Methode oder Eigenschaft.

*wFlags*<br/>
Flags, `IDispatch::Invoke`die den Kontext des Aufrufes beschreiben. . Eine Liste möglicher Werte finden Sie unter dem *wFlags* -Parameter in [IDispatch:: Aufrufen](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) in der Windows SDK.

*vtRet*<br/>
Gibt den Typ des Rückgabewerts an. Mögliche Werte finden Sie im Abschnitt „Hinweise“.

*pvRet*<br/>
Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Er muss mit dem Typ identisch sein, der von *vtret*angegeben wird.

*pbParamInfo*<br/>
Zeiger auf eine mit NULL endenden Byte Zeichenfolge, die die Typen der Parameter nach *pbparaminfo*angibt.

*...*<br/>
Variable Parameterliste, der in *pbparaminfo*angegebenen Typen.

### <a name="remarks"></a>Hinweise

Der *pbparaminfo* -Parameter gibt die Typen der Parameter an, die an die Methode oder Eigenschaft übergeben werden. Die variable Argumentliste wird in der Syntaxdeklaration durch **...** dargestellt.

Mögliche Werte für das *vtret* -Argument werden aus der varenumeration-Enumeration entnommen. Folgende Werte sind möglich:

|Symbol|Rückgabetyp|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**DATE**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**KONFIGUR**|
|VT_UNKNOWN|LPUNKNOWN|

Das *pbparaminfo* -Argument ist eine durch Leerzeichen getrennte Liste von **VTS_** -Konstanten. Einer oder mehrere dieser Werte, durch Leerzeichen (nicht Kommas) getrennt, gibt bzw. geben die Parameterliste der Funktion an. Die möglichen Werte sind beim Makro [EVENT_CUSTOM](event-maps.md#event_custom) aufgelistet.

Diese Funktion konvertiert die Parameter in VARIANTARG-Werte und ruft dann die [IDispatch:: Aufrufen](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) -Methode auf. Bei einem Fehler des Aufrufs von `Invoke` löst diese Funktion eine Ausnahme aus. Wenn der von zurückgegebene SCODE (Statuscode `IDispatch::Invoke` ) DISP_E_EXCEPTION ist, löst diese Funktion ein [COleException](../../mfc/reference/coleexception-class.md) -Objekt aus; andernfalls löst Sie eine [COleDispatchException](../../mfc/reference/coledispatchexception-class.md)aus.

Weitere Informationen finden Sie unter [VARIANTARG](/windows/win32/api/oaidl/ns-oaidl-variant), [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [IDispatch:: Aufrufen](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)und [Struktur von com-Fehler Codes](/windows/win32/com/structure-of-com-error-codes) in der Windows SDK.

### <a name="example"></a>Beispiel

  Siehe dazu das Beispiel für [COleDispatchDriver::CreateDispatch](#createdispatch).

##  <a name="m_bautorelease"></a>COleDispatchDriver:: m_bAutoRelease

TRUE gibt an, dass das COM-Objekt, auf das von [m_lpDispatch](#m_lpdispatch) zugegriffen wird, automatisch freigegeben wird, `COleDispatchDriver` Wenn [releasedispatch](#releasedispatch) aufgerufen wird oder wenn dieses Objekt zerstört wird.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Hinweise

Standardmäßig `m_bAutoRelease` ist im Konstruktor auf true festgelegt.

Weitere Informationen zum Freigeben von COM-Objekten finden Sie unter [Implementieren der Verweis Zählung](/windows/win32/com/implementing-reference-counting) und [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>COleDispatchDriver:: m_lpDispatch

Der Zeiger auf die `IDispatch` -Schnittstelle, `COleDispatchDriver`die diesem zugeordnet ist.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Hinweise

Der `m_lpDispatch` Datenmember ist eine öffentliche Variable vom Typ lpdispatch.

Weitere Informationen finden Sie unter [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) in der Windows SDK.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [COleDispatchDriver:: attachdispatch](#attachdispatch).

##  <a name="operator_eq"></a>COleDispatchDriver:: Operator =

Kopiert den Quellwert in das `COleDispatchDriver` -Objekt.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parameter

*dispatchSrc*<br/>
Ein Zeiger auf ein vorhandenes `COleDispatchDriver` -Objekt.

##  <a name="operator_lpdispatch"></a>COleDispatchDriver:: Operator lpdispatch

`IDispatch` Greift`COleDispatchDriver` auf den zugrunde liegenden Zeiger des-Objekts zu.

```
operator LPDISPATCH();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>COleDispatchDriver:: releasedispatch

Gibt die `IDispatch` Verbindung frei. Weitere Informationen finden Sie unter [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) .

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Hinweise

Wenn für diese Verbindung das automatische Release festgelegt wurde, ruft `IDispatch::Release` diese Funktion vor der Freigabe der-Schnittstelle auf.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [COleDispatchDriver:: attachdispatch](#attachdispatch).

##  <a name="setproperty"></a>COleDispatchDriver:: SetProperty

Legt die von *dwdispid*angegebene OLE-Objekt Eigenschaft fest.

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die festzulegende Eigenschaft an.

*vtProp*<br/>
Gibt den Typ der festzulegenden Eigenschaft an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](#invokehelper).

*...*<br/>
Ein einzelner Parameter des Typs, der von *vtprop*angegeben wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel für CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel-ACDual](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
