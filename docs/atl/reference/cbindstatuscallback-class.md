---
title: Cbindstatus Callback-Klasse
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
ms.openlocfilehash: 89c65ff034cf7471c379b28116a741b62269a00c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497604"
---
# <a name="cbindstatuscallback-class"></a>Cbindstatus Callback-Klasse

Diese Klasse implementiert die `IBindStatusCallback` -Schnittstelle.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse, die die Funktion enthält, die aufgerufen wird, wenn die Daten empfangen werden.

*nBindFlags*<br/>
Gibt die Bindungsflags an, die von [getbindinfo](#getbindinfo)zurückgegeben werden. Die Standard Implementierung legt die Bindung als asynchron fest, ruft die neueste Version des Daten/Objekts ab und speichert keine abgerufenen Daten im Datenträger Cache.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Der Konstruktor.|
|[CBindStatusCallback::~CBindStatusCallback](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBindStatusCallback::Download](#download)|Statische Methode, die den Downloadvorgang startet, ein `CBindStatusCallback` -Objekt erstellt und `StartAsyncDownload`aufruft.|
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Wird vom asynchronen Moniker aufgerufen, um Informationen über den Typ der zu erstellenden Bindung anzufordern.|
|[CBindStatusCallback::GetPriority](#getpriority)|Wird vom asynchronen Moniker aufgerufen, um die Priorität des Bindungs Vorgangs zu erhalten. Die ATL-Implementierung `E_NOTIMPL`gibt zurück.|
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Wird aufgerufen, um Daten für die Anwendung bereitzustellen, sobald Sie verfügbar wird. Liest die Daten und ruft dann die an Sie weiter gegebene Funktion auf, um die Daten zu verwenden.|
|[CBindStatusCallback::OnLowResource](#onlowresource)|Wird aufgerufen, wenn die Ressourcen niedrig sind. Die ATL-Implementierung gibt S_OK zurück.|
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Wird vom asynchronen Moniker aufgerufen, um einen Objekt Schnittstellen Zeiger an Ihre Anwendung zu übergeben. Die ATL-Implementierung gibt S_OK zurück.|
|[CBindStatusCallback::OnProgress](#onprogress)|Wird aufgerufen, um den Fortschritt eines Daten Downloadvorgangs anzugeben. Die ATL-Implementierung gibt S_OK zurück.|
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Wird aufgerufen, wenn die Bindung gestartet wird.|
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Wird aufgerufen, wenn die asynchrone Datenübertragung beendet wird.|
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Initialisiert die verfügbaren Bytes und Bytes, die auf 0 (null) gelesen werden, erstellt ein Streamobjekt vom pushtyp aus einer URL und ruft `OnDataAvailable` jedes Mal auf, wenn Daten verfügbar sind.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Anzahl der zu lesenden Bytes.|
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Gesamtanzahl der gelesenen Bytes.|
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Ein Zeiger auf die Funktion, die aufgerufen wird, wenn Daten verfügbar sind.|
|[CBindStatusCallback::m_pT](#m_pt)|Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert.|
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Zeiger auf die [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) -Schnittstelle für den aktuellen Bindungs Vorgang.|
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Ein Zeiger auf `IBinding` die-Schnittstelle für den aktuellen Bindungs Vorgang.|
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Ein Zeiger auf die [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) -Schnittstelle für die zu verwendende URL.|
|[CBindStatusCallback::m_spStream](#m_spstream)|Ein Zeiger auf die [IStream](/windows/win32/api/objidl/nn-objidl-istream) -Schnittstelle für die Datenübertragung.|

## <a name="remarks"></a>Hinweise

Die `CBindStatusCallback`-Klasse implementiert die `IBindStatusCallback`-Schnittstelle. `IBindStatusCallback`muss von Ihrer Anwendung implementiert werden, damit Benachrichtigungen von einer asynchronen Datenübertragung empfangen werden können. Der asynchrone Moniker, der vom System bereit `IBindStatusCallback` gestellt wird, verwendet Methoden zum Senden und empfangen von Informationen über die asynchrone Datenübertragung an das und aus dem-Objekt.

In der Regel `CBindStatusCallback` ist das-Objekt einem bestimmten Bindungs Vorgang zugeordnet. Beispielsweise wird im Beispiel [Async](../../overview/visual-cpp-samples.md) beim Festlegen der URL-Eigenschaft ein `CBindStatusCallback` -Objekt im-Aufrufen von `Download`erstellt:

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

Der asynchrone Moniker verwendet die Rückruffunktion `OnData` , um die Anwendung aufzurufen, wenn Sie Daten enthält. Der asynchrone Moniker wird vom System bereitgestellt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

`IBindStatusCallback`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="cbindstatuscallback"></a>Cbindstatus Callback:: cbindstatus Callback

Der Konstruktor.

```
CBindStatusCallback();
```

### <a name="remarks"></a>Hinweise

Erstellt ein-Objekt, um Benachrichtigungen über die asynchrone Datenübertragung zu empfangen. In der Regel wird für jeden Bindungs Vorgang ein-Objekt erstellt.

Der Konstruktor initialisiert auch [m_pT](#m_pt) und [m_pFunc](#m_pfunc) auf NULL.

##  <a name="dtor"></a>Cbindstatus Callback:: ~ cbindstatus Callback

Der Destruktor.

```
~CBindStatusCallback();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei.

##  <a name="download"></a>Cbindstatus Callback::D ownload

Erstellt ein `CBindStatusCallback` -Objekt und `StartAsyncDownload` Ruft auf, um das asynchrone herunterladen von Daten aus der angegebenen URL zu starten.

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
in Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert. Das `CBindStatusCallback` -Objekt ist in der Klasse dieses Objekts Vorlagen basiert.

*pFunc*<br/>
in Ein Zeiger auf die Funktion, die die gelesenen Daten empfängt. Die-Funktion ist ein Member der Klasse Ihres Objekts vom Typ `T`. Unter [StartAsyncDownload finden Sie](#startasyncdownload) Syntax und ein Beispiel.

*bstrURL*<br/>
in Die URL, aus der Daten abgerufen werden sollen. Kann eine beliebige gültige URL oder ein beliebiger Dateiname sein. Lässt keine NULL-Werte zu. Beispiel:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
in Der `IUnknown` des Containers. Standardmäßig NULL.

*bRelative*<br/>
in Ein Flag, das angibt, ob die URL relativ oder absolut ist. Standardmäßig false, was bedeutet, dass die URL absolut ist.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Jedes Mal, wenn Daten verfügbar sind, wird Sie über `OnDataAvailable`an das-Objekt gesendet. `OnDataAvailable`liest die Daten und ruft die Funktion auf, auf die *pFunc* verweist (z. b., um die Daten zu speichern oder auf dem Bildschirm zu drucken).

##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo

Wird aufgerufen, um dem Moniker mitzuteilen, wie er gebunden werden soll.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>Parameter

*pgrfBSCF*<br/>
vorgenommen Ein Zeiger auf bindf-Enumerationswerte, die angeben, wie der Bindungs Vorgang erfolgen soll. Legen Sie standardmäßig mit den folgenden Enumerationswerten fest:

BINDF_ASYNCHRONOUS asynchroner Download.

BINDF_ASYNCSTORAGE `OnDataAvailable` gibt E_PENDING zurück, wenn noch keine Daten verfügbar sind, anstatt zu blockieren, bis die Daten verfügbar sind.

BINDF_GETNEWESTVERSION beim Bindungs Vorgang sollte die neueste Version der Daten abgerufen werden.

BINDF_NOWRITECACHE beim Bindungs Vorgang sollten keine abgerufenen Daten im Datenträger Cache gespeichert werden.

*pbindinfo*<br/>
[in, out] Ein Zeiger auf die `BINDINFO` -Struktur, die mehr Informationen darüber gibt, wie das-Objekt eine Bindung durchführen soll.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Mit der Standard Implementierung wird die Bindung als asynchron festgelegt und das datenpushmodell verwendet. Im Daten Push-Modell steuert der Moniker den asynchronen Bindungs Vorgang und benachrichtigt den Client kontinuierlich, wenn neue Daten verfügbar sind.

##  <a name="getpriority"></a>Cbindstatus Callback:: GetPriority

Wird vom asynchronen Moniker aufgerufen, um die Priorität des Bindungs Vorgangs zu erhalten.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>Parameter

*pnPriority*<br/>
vorgenommen Adresse der **Long** -Variablen, die bei Erfolg die Priorität erhält.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

##  <a name="m_dwavailabletoread"></a>Cbindstatus Callback:: m_dwAvailableToRead

Kann verwendet werden, um die Anzahl der zu lesenden Bytes zu speichern.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>Hinweise

Initialisiert mit 0 ( `StartAsyncDownload`null) in.

##  <a name="m_dwtotalread"></a>Cbindstatus Callback:: m_dwTotalRead

Die kumulierte Gesamtsumme der in der asynchronen Datenübertragung gelesenen Bytes.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>Hinweise

Jedes Mal `OnDataAvailable` inkrementiert wird von der Anzahl der tatsächlich gelesenen Bytes aufgerufen. Initialisiert mit 0 ( `StartAsyncDownload`null) in.

##  <a name="m_pfunc"></a>Cbindstatus Callback:: m_pFunc

Die Funktion, auf die `m_pFunc` von verwiesen wird `OnDataAvailable` , wird von aufgerufen, nachdem die verfügbaren Daten gelesen wurden (z. b. zum Speichern der Daten oder zum Drucken auf dem Bildschirm).

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>Hinweise

Die Funktion, auf die `m_pFunc` verweist, ist ein Member der-Klasse des Objekts und weist die folgende Syntax auf:

```
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

##  <a name="m_pt"></a>Cbindstatus Callback:: m_pT

Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert.

```
T* m_pT;
```

### <a name="remarks"></a>Hinweise

Das `CBindStatusCallback` -Objekt ist in der Klasse dieses Objekts Vorlagen basiert.

##  <a name="m_spbindctx"></a>Cbindstatus Callback:: m_spBindCtx

Ein Zeiger auf eine [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) -Schnittstelle, die Zugriff auf den Bindungs Kontext bietet (ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang speichert).

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>Hinweise

Initialisiert in `StartAsyncDownload`.

##  <a name="m_spbinding"></a>Cbindstatus Callback:: m_spBinding

Ein Zeiger auf die `IBinding` -Schnittstelle des aktuellen Bindungs Vorgangs.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>Hinweise

Wurde in `OnStartBinding` initialisiert und in `OnStopBinding`veröffentlicht.

##  <a name="m_spmoniker"></a>Cbindstatus Callback:: m_spMoniker

Ein Zeiger auf die [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) -Schnittstelle für die zu verwendende URL.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>Hinweise

Initialisiert in `StartAsyncDownload`.

##  <a name="m_spstream"></a>Cbindstatus Callback:: m_spStream

Ein Zeiger auf die [IStream](/windows/win32/api/objidl/nn-objidl-istream) -Schnittstelle des aktuellen Bindungs Vorgangs.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>Hinweise

Wird in `OnDataAvailable` aus der `STGMEDIUM` -Struktur initialisiert, wenn das bcsf-Flag BCSF_FIRSTDATANOTIFICATION ist und freigegeben wird, wenn das bcsf-Flag BCSF_LASTDATANOTIFICATION ist.

##  <a name="ondataavailable"></a>Cbindstatus Callback:: ondataavailable

Der vom System bereitgestellte asynchrone Moniker `OnDataAvailable` Ruft auf, um Daten für das Objekt bereitzustellen, sobald es verfügbar wird.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>Parameter

*grfBSCF*<br/>
in Ein BSCF-Enumerationswert. Eine oder mehrere der folgenden: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION oder BSCF_LASTDATANOTIFICATION.

*dwSize*<br/>
in Der kumulative Betrag der Daten (in Bytes), die seit dem Anfang der Bindung verfügbar sind. Kann NULL sein, was bedeutet, dass die Menge der Daten nicht relevant ist oder dass kein bestimmter Betrag verfügbar wurde.

*pformatetc*<br/>
in Ein Zeiger auf die [FORMATETC](/windows/win32/com/the-formatetc-structure) -Struktur, die das Format der verfügbaren Daten enthält. Wenn kein Format vorhanden ist, kann CF_NULL sein.

*pstgmed*<br/>
in Ein Zeiger auf die [STGMEDIUM](/windows/win32/com/the-stgmedium-structure) -Struktur, die die eigentlichen Daten enthält, die jetzt verfügbar sind.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

`OnDataAvailable`liest die Daten und ruft dann eine Methode der-Klasse des Objekts auf (z. b., um die Daten zu speichern oder auf dem Bildschirm zu drucken). Weitere Informationen finden [Sie unter cbindstatus-Rückruf:: StartAsyncDownload](#startasyncdownload) .

##  <a name="onlowresource"></a>Cbindstatus Callback:: onlowresource

Wird aufgerufen, wenn die Ressourcen niedrig sind.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>Parameter

*dwReserved*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="onobjectavailable"></a>Cbindstatus Callback:: onobjectavailable

Wird vom asynchronen Moniker aufgerufen, um einen Objekt Schnittstellen Zeiger an Ihre Anwendung zu übergeben.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Der Schnittstellen Bezeichner der angeforderten Schnittstelle. Nicht verwendet.

*Kro*<br/>
Adresse der IUnknown-Schnittstelle. Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="onprogress"></a>CBindStatusCallback:: OnProgress

Wird aufgerufen, um den Fortschritt eines Daten Downloadvorgangs anzugeben.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>Parameter

*ulProgress*<br/>
Lange ganze Zahl ohne Vorzeichen. Nicht verwendet.

*ulProgressMax*<br/>
Unsigned long Integer-Wert nicht verwendet.

*ulStatusCode*<br/>
Lange ganze Zahl ohne Vorzeichen. Nicht verwendet.

*szStatusText*<br/>
Adresse eines Zeichen folgen Werts. Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="onstartbinding"></a>Cbindstatus Callback:: onstartbinding

Legt den [m_spBinding](#m_spbinding) -Datenmember auf `IBinding` den Zeiger in *pbinding*fest.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>Parameter

*dwReserved*<br/>
Zur künftigen Verwendung reserviert.

*pBinding*<br/>
in Adresse der ibinding-Schnittstelle des aktuellen Bindungs Vorgangs. Dieser Wert darf nicht NULL sein. Der Client sollte die adressf für diesen Zeiger abrufen, um einen Verweis auf das Bindungs Objekt zu erhalten.

##  <a name="onstopbinding"></a>Cbindstatus Callback:: onstopbinding

Gibt den `IBinding` Zeiger im Datenmember [m_spBinding](#m_spbinding)frei.

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>Parameter

*HRESULT*<br/>
Der vom Bindungs Vorgang zurückgegebene Status Code.

*szError*<br/>
Adresse eines Zeichen folgen Werts. Nicht verwendet.

### <a name="remarks"></a>Hinweise

Wird vom vom System bereitgestellten asynchronen Moniker aufgerufen, um das Ende des Bindungs Vorgangs anzugeben.

##  <a name="startasyncdownload"></a>Cbindstatus Callback:: StartAsyncDownload

Startet asynchron das Herunterladen von Daten aus der angegebenen URL.

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
in Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert. Das `CBindStatusCallback` -Objekt ist in der Klasse dieses Objekts Vorlagen basiert.

*pFunc*<br/>
in Ein Zeiger auf die Funktion, die die gelesenen Daten empfängt. Die-Funktion ist ein Member der Klasse Ihres Objekts vom Typ `T`. Weitere Informationen finden Sie unter **Hinweise** zur Syntax und ein Beispiel.

*bstrURL*<br/>
in Die URL, aus der Daten abgerufen werden sollen. Kann eine beliebige gültige URL oder ein beliebiger Dateiname sein. Lässt keine NULL-Werte zu. Beispiel:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
in Der `IUnknown` des Containers. Standardmäßig NULL.

*bRelative*<br/>
in Ein Flag, das angibt, ob die URL relativ oder absolut ist. Standardmäßig false, was bedeutet, dass die URL absolut ist.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Jedes Mal, wenn Daten verfügbar sind, wird Sie über `OnDataAvailable`an das-Objekt gesendet. `OnDataAvailable`liest die Daten und ruft die Funktion auf, auf die *pFunc* verweist (z. b., um die Daten zu speichern oder auf dem Bildschirm zu drucken).

Die Funktion, auf die von *pFunc* verwiesen wird, ist ein Member der Klasse Ihres Objekts und weist die folgende Syntax auf:

```
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

Im folgenden Beispiel (aus dem [Async](../../overview/visual-cpp-samples.md) -Beispiel entnommen) schreibt die- `OnData` Funktion die empfangenen Daten in ein Textfeld.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
