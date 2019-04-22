---
title: CBindStatusCallback-Klasse
ms.date: 11/04/2016
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
ms.openlocfilehash: 6e5e55a23ee678bbedf76f608bc4fdf562cc1822
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773124"
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback-Klasse

Diese Klasse implementiert die `IBindStatusCallback` -Schnittstelle.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse, die mit der Funktion, die aufgerufen werden, wenn die Daten empfangen werden.

*nBindFlags*<br/>
Gibt an, die Bindungsflags, die von zurückgegeben werden [GetBindInfo](#getbindinfo). Die standardmäßige Implementierung wird die Bindung asynchron sein müssen, ruft die neueste Version des Datenobjekts/ab und speichert keine abgerufene Daten im Datenträgercache.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Der Konstruktor.|
|[CBindStatusCallback::~CBindStatusCallback](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBindStatusCallback::Download](#download)|Statische Methode, die den Downloadprozess beginnt erstellt eine `CBindStatusCallback` -Objekt, und ruft `StartAsyncDownload`.|
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Wird aufgerufen, durch den asynchronen Moniker zum Anfordern von Informationen für den Typ der Bindung erstellt werden.|
|[CBindStatusCallback::GetPriority](#getpriority)|Wird aufgerufen, durch den asynchronen Moniker, die die Priorität des Bindevorgangs zu erhalten. Gibt zurück, die ATL-Implementierung `E_NOTIMPL`.|
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Wird aufgerufen, um Daten zu Ihrer Anwendung bereitzustellen, sobald diese verfügbar werden. Liest die Daten, und ruft dann die Funktion übergeben, um die Daten zu verwenden.|
|[CBindStatusCallback::OnLowResource](#onlowresource)|Wird aufgerufen, wenn die Ressourcen niedrig sind. Es gibt S_OK zurück, die ATL-Implementierung.|
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Wird aufgerufen, durch den asynchronen Moniker, die einen Schnittstellenzeiger des Objekts an die Anwendung übergeben. Es gibt S_OK zurück, die ATL-Implementierung.|
|[CBindStatusCallback::OnProgress](#onprogress)|Wird aufgerufen, um den Fortschritt einer Datenübertragungsprozesses anzuzeigen. Es gibt S_OK zurück, die ATL-Implementierung.|
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Wird aufgerufen, wenn Bindung gestartet wird.|
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Wird aufgerufen, wenn die asynchrone Datenübertragung beendet wird.|
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Initialisiert die verfügbaren Bytes und gelesene Bytes 0 (null), einem Push-Type-Stream-Objekt erstellt, über eine URL, und ruft `OnDataAvailable` jedes Mal, wenn Daten verfügbar sind.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Anzahl der Bytes, die zum Lesen verfügbar.|
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Die Gesamtanzahl der gelesenen Bytes.|
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Zeiger auf die Funktion wird aufgerufen, wenn Daten verfügbar sind.|
|[CBindStatusCallback::m_pT](#m_pt)|Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordern.|
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Zeiger auf die [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) Schnittstelle für den aktuellen Bindungsvorgang.|
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Zeiger auf die `IBinding` Schnittstelle für den aktuellen Bindungsvorgang.|
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Zeiger auf die [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) Schnittstelle für die URL zu verwenden.|
|[CBindStatusCallback::m_spStream](#m_spstream)|Zeiger auf die [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Schnittstelle für die Datenübertragung.|

## <a name="remarks"></a>Hinweise

Die `CBindStatusCallback`-Klasse implementiert die `IBindStatusCallback`-Schnittstelle. `IBindStatusCallback` muss von der Anwendung implementiert werden, damit es Benachrichtigungen in eine asynchrone Datenübertragung empfangen kann. Der asynchrone Moniker, der vom System bereitgestellten verwendet `IBindStatusCallback` Methoden zum Senden und Empfangen von Informationen zu den asynchronen Daten in und aus Ihr Objekt zu übertragen.

In der Regel die `CBindStatusCallback` Objekt bezieht sich auf einen bestimmten Bindevorgang. Z. B. in der [ASYNC](../../overview/visual-cpp-samples.md) Beispiel, wenn Sie festlegen, dass die URL-Eigenschaft, es erstellt eine `CBindStatusCallback` Objekt im Aufruf von `Download`:

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

Der asynchrone Moniker verwendet die Callback-Funktion `OnData` Ihrer Anwendung aufgerufen, wenn es Daten enthält. Der asynchrone Moniker wird vom System bereitgestellt werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

`IBindStatusCallback`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="cbindstatuscallback"></a>  CBindStatusCallback::CBindStatusCallback

Der Konstruktor.

```
CBindStatusCallback();
```

### <a name="remarks"></a>Hinweise

Erstellt ein Objekt zum Empfangen von Benachrichtigungen über die asynchrone Datenübertragung. In der Regel wird ein Objekt für jeden Bindungsvorgang erstellt.

Der Konstruktor initialisiert zudem [M_pT](#m_pt) und [M_pFunc](#m_pfunc) auf NULL.

##  <a name="dtor"></a>  CBindStatusCallback:: ~ CBindStatusCallback

Der Destruktor.

```
~CBindStatusCallback();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei.

##  <a name="download"></a>  CBindStatusCallback::Download

Erstellt eine `CBindStatusCallback` -Objekt und ruft `StartAsyncDownload` starten, Daten aus der angegebenen URL asynchron herunterladen.

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Parameter

*pT*<br/>
[in] Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordern. Die `CBindStatusCallback` Objekt ist für die Klasse des Objekts vorlagenbasiert.

*pFunc*<br/>
[in] Ein Zeiger auf die Funktion, die die Daten empfängt, die gelesen wird. Die Funktion ist ein Member, der die Klasse des Objekts vom Typ `T`. Finden Sie unter [StartAsyncDownload](#startasyncdownload) für die Syntax und Beispielen.

*bstrURL*<br/>
[in] Die URL zum Abrufen von Daten aus. Ein gültiger URL-Zeichenfolge oder -Name kann sein. Darf nicht NULL sein. Zum Beispiel:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[in] Die `IUnknown` des Containers. Standardmäßig NULL.

*bRelative*<br/>
[in] Ein Flag, der angibt, ob die URL relativ oder absolut ist. Standardmäßig, d. h. die URL "false" ist absolut.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Jedes Mal, wenn Daten verfügbar sind an das Objekt über gesendet `OnDataAvailable`. `OnDataAvailable` liest die Daten und ruft die Funktion verweist *pFunc* (z. B. die Daten speichern oder drucken Sie ihn auf dem Bildschirm).

##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo

Wird aufgerufen, um dem Moniker binden mitzuteilen.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>Parameter

*pgrfBSCF*<br/>
[out] Ein Zeiger auf BINDF-Enumerationswerte, der angibt, wie der Bindungsvorgang erfolgen soll. Standardmäßig festgelegt, mit der folgenden Enumerationswerte:

BINDF_ASYNCHRONOUS asynchronen Download.

BINDF_ASYNCSTORAGE `OnDataAvailable` E_PENDING zurück, wenn die Daten noch nicht verfügbar ist und nicht blockiert, bis die Daten verfügbar sind.

BINDF_GETNEWESTVERSION der Bindungsvorgang sollten die neueste Version der Daten abgerufen werden.

Abgerufen, Daten im Datenträgercache BINDF_NOWRITECACHE, die der Bindungsvorgang nicht gespeichert werden sollten.

*pbindinfo*<br/>
[in, out] Ein Zeiger auf die `BINDINFO` Struktur, sodass Weitere Informationen, wie das Objekt die Bindung erfolgen soll.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung legt fest, die Bindung, die asynchron sein und das Daten-Push-Modell zu verwenden. Im Daten-Push-Modell der Moniker der asynchronen Bindungsvorgang Laufwerke und kontinuierlich benachrichtigt den Client, wenn neue Daten verfügbar sind.

##  <a name="getpriority"></a>  CBindStatusCallback::GetPriority

Wird aufgerufen, durch den asynchronen Moniker, die die Priorität des Bindevorgangs zu erhalten.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>Parameter

*pnPriority*<br/>
[out] Adresse von der **lange** Variable, die bei Erfolg die Priorität erhält.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

##  <a name="m_dwavailabletoread"></a>  CBindStatusCallback::m_dwAvailableToRead

Kann verwendet werden, speichern Sie die Anzahl der Bytes, die gelesen werden kann.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>Hinweise

Initialisiert auf 0 (null) `StartAsyncDownload`.

##  <a name="m_dwtotalread"></a>  CBindStatusCallback::m_dwTotalRead

Der kumulierte Gesamtbetrag von Bytes lesen, in die asynchrone Datenübertragung.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>Hinweise

Jedes Mal erhöht `OnDataAvailable` wird aufgerufen, um die Anzahl der tatsächlich gelesenen Bytes. Initialisiert auf 0 (null) `StartAsyncDownload`.

##  <a name="m_pfunc"></a>  CBindStatusCallback::m_pFunc

Die Funktion verweist `m_pFunc` wird aufgerufen, indem `OnDataAvailable` nach dem er liest die verfügbaren Daten (z. B. die Daten speichern oder drucken Sie ihn auf dem Bildschirm).

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>Hinweise

Die Funktion verweist `m_pFunc` ist ein Mitglied die Klasse des Objekts und weist die folgende Syntax:

```
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

##  <a name="m_pt"></a>  CBindStatusCallback::m_pT

Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordern.

```
T* m_pT;
```

### <a name="remarks"></a>Hinweise

Die `CBindStatusCallback` Objekt ist für die Klasse des Objekts vorlagenbasiert.

##  <a name="m_spbindctx"></a>  CBindStatusCallback::m_spBindCtx

Ein Zeiger auf ein [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) Schnittstelle, die Zugriff auf den Bindungskontext (ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang gespeichert) bereitstellt.

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>Hinweise

Im initialisierten `StartAsyncDownload`.

##  <a name="m_spbinding"></a>  CBindStatusCallback::m_spBinding

Ein Zeiger auf die `IBinding` Schnittstelle von der aktuellen Bindungsvorgang.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>Hinweise

Im initialisierten `OnStartBinding` und veröffentlichte in `OnStopBinding`.

##  <a name="m_spmoniker"></a>  CBindStatusCallback::m_spMoniker

Ein Zeiger auf die [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) Schnittstelle für die URL zu verwenden.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>Hinweise

Im initialisierten `StartAsyncDownload`.

##  <a name="m_spstream"></a>  CBindStatusCallback::m_spStream

Ein Zeiger auf die [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Schnittstelle von der aktuellen Bindungsvorgang.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>Hinweise

Im initialisierten `OnDataAvailable` aus der `STGMEDIUM` Struktur, wenn das Flag BCSF BCSF_FIRSTDATANOTIFICATION und freigegeben, wenn das Flag BCSF BCSF_LASTDATANOTIFICATION ist.

##  <a name="ondataavailable"></a>  CBindStatusCallback::OnDataAvailable

Die Aufrufe vom System bereitgestellten asynchronen Monikers `OnDataAvailable` Daten für das Objekt bereitgestellt wird, sobald diese verfügbar werden.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>Parameter

*grfBSCF*<br/>
[in] Ein Wert für den BSCF-Enumeration. Eine oder mehrere der folgenden: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION oder BSCF_LASTDATANOTIFICATION.

*dwSize*<br/>
[in] Den kumulativen Zeitraum (in Byte) der Daten, die seit dem Beginn der Bindung zur Verfügung. Kann 0 (null), der angibt, dass die Menge der Daten nicht relevant ist oder keine verfügbar war.

*pformatetc*<br/>
[in] Zeiger auf die [FORMATETC](/windows/desktop/com/the-formatetc-structure) -Struktur, die das Format der verfügbaren Daten enthält. Wenn kein Format wird kann CF_NULL sein.

*pstgmed*<br/>
[in] Zeiger auf die [STGMEDIUM](/windows/desktop/com/the-stgmedium-structure) -Struktur, die die tatsächlichen Daten, die jetzt verfügbar ist.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

`OnDataAvailable` liest die Daten, und ruft dann eine Methode, der die Klasse des Objekts (z. B. die Daten speichern oder drucken Sie ihn auf dem Bildschirm). Finden Sie unter [CBindStatusCallback:: StartAsyncDownload](#startasyncdownload) Details.

##  <a name="onlowresource"></a>  CBindStatusCallback::OnLowResource

Wird aufgerufen, wenn die Ressourcen niedrig sind.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>Parameter

*dwReserved*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="onobjectavailable"></a>  CBindStatusCallback::OnObjectAvailable

Wird aufgerufen, durch den asynchronen Moniker, die einen Schnittstellenzeiger des Objekts an die Anwendung übergeben.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Der Schnittstellenbezeichner der angeforderten Schnittstelle. Nicht verwendet.

*punk*<br/>
Die Adresse der IUnknown-Schnittstelle. Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="onprogress"></a>  CBindStatusCallback::OnProgress

Wird aufgerufen, um den Fortschritt einer Datenübertragungsprozesses anzuzeigen.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>Parameter

*ulProgress*<br/>
Long-Integer ohne Vorzeichen. Nicht verwendet.

*ulProgressMax*<br/>
Long-Ganzzahl ohne Vorzeichen nicht verwendet.

*ulStatusCode*<br/>
Long-Integer ohne Vorzeichen. Nicht verwendet.

*szStatusText*<br/>
Die Adresse eines Zeichenfolgenwerts. Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="onstartbinding"></a>  CBindStatusCallback::OnStartBinding

Legt den Datenmember [M_spBinding](#m_spbinding) auf die `IBinding` Zeiger in *pBinding*.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>Parameter

*dwReserved*<br/>
Für zukünftige Verwendung reserviert.

*pBinding*<br/>
[in] Adresse der Schnittstelle des aktuellen IBinding Bindungsvorgang. Dies darf nicht NULL sein. Der Client sollte "AddRef" für diesen Zeiger zu der einen Verweis auf das Binding-Objekt aufrufen.

##  <a name="onstopbinding"></a>  CBindStatusCallback::OnStopBinding

Versionen der `IBinding` Zeiger im Datenmember [M_spBinding](#m_spbinding).

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>Parameter

*hresult*<br/>
Statuscode zurückgegeben, aus dem Bindungsvorgang.

*szError*<br/>
Die Adresse eines Zeichenfolgenwerts. Nicht verwendet.

### <a name="remarks"></a>Hinweise

Wird aufgerufen, vom System bereitgestellte asynchrone Moniker, der das Ende des Bindevorgangs anzugeben.

##  <a name="startasyncdownload"></a>  CBindStatusCallback:: StartAsyncDownload

Beginnt, Daten aus der angegebenen URL asynchron herunterladen.

```
HRESULT StartAsyncDownload(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Parameter

*pT*<br/>
[in] Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordern. Die `CBindStatusCallback` Objekt ist für die Klasse des Objekts vorlagenbasiert.

*pFunc*<br/>
[in] Ein Zeiger auf die Funktion, die die Daten gelesen werden empfängt. Die Funktion ist ein Member, der die Klasse des Objekts vom Typ `T`. Finden Sie unter **"Hinweise"** für die Syntax und Beispielen.

*bstrURL*<br/>
[in] Die URL zum Abrufen von Daten aus. Ein gültiger URL-Zeichenfolge oder -Name kann sein. Darf nicht NULL sein. Zum Beispiel:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[in] Die `IUnknown` des Containers. Standardmäßig NULL.

*bRelative*<br/>
[in] Ein Flag, der angibt, ob die URL relativ oder absolut ist. Standardmäßig, d. h. die URL "false" ist absolut.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Jedes Mal, wenn Daten verfügbar sind an das Objekt über gesendet `OnDataAvailable`. `OnDataAvailable` liest die Daten und ruft die Funktion verweist *pFunc* (z. B. die Daten speichern oder drucken Sie ihn auf dem Bildschirm).

Die Funktion verweist *pFunc* ist ein Mitglied die Klasse des Objekts und weist die folgende Syntax:

```
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

Im folgenden Beispiel (stammt aus der [ASYNC](../../overview/visual-cpp-samples.md) Beispiel), die Funktion `OnData` schreibt die empfangenen Daten in ein Textfeld.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
