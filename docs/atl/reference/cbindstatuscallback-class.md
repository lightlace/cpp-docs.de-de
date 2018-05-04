---
title: Klasse CBindStatusCallback | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43a51b98710ea92f153581945007f21864dca6f4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback-Klasse
Diese Klasse implementiert die `IBindStatusCallback`-Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse, die mit der Funktion, die aufgerufen wird, wie die Daten empfangen werden.  
  
 *nBindFlags*  
 Gibt an, die Bindungsflags, die von zurückgegeben werden [GetBindInfo](#getbindinfo). Die standardmäßige Implementierung Festlegen der Bindung asynchron ist, ruft die neueste Version das Datenobjekt ab und abgerufene Daten nicht in den Datenträgercache gespeichert.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Der Konstruktor.|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|Statische Methode, die der Downloadvorgang beginnt erstellt eine `CBindStatusCallback` -Objekt und ruft `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Wird aufgerufen, durch die asynchrone Moniker zum Anfordern von Informationen für den Typ der Bindung erstellt werden soll.|  
|[CBindStatusCallback::GetPriority](#getpriority)|Wird aufgerufen, durch die asynchrone Moniker die Priorität der Bind-Operation abgerufen. Gibt die ATL-Implementierung `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Wird aufgerufen, um Daten für Ihre Anwendung bereitstellen, sobald sie verfügbar sind. Liest die Daten und ruft dann die Funktion übergeben, um die Daten verwenden.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|Wird aufgerufen, wenn nicht genügend Ressourcen verfügbar sind. Gibt die ATL-Implementierung `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Wird aufgerufen, durch die asynchrone Moniker einen Schnittstellenzeiger Objekt an die Anwendung übergeben. Gibt die ATL-Implementierung `S_OK`.|  
|[CBindStatusCallback::OnProgress](#onprogress)|Wird aufgerufen, um den Fortschritt einer Datenübertragungsprozesses anzugeben. Gibt die ATL-Implementierung `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Wird aufgerufen, wenn Bindung gestartet wird.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Wird aufgerufen, wenn die asynchrone Übertragung beendet wird.|  
|[CBindStatusCallback:: StartAsyncDownload](#startasyncdownload)|Verfügbare Bytes initialisiert und ein Push-Type-Streamobjekt Bytes gelesen, um 0 (null), erstellt werden, aus einer URL, und ruft `OnDataAvailable` jedes Mal, wenn Daten verfügbar sind.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Anzahl der Bytes, die zum Lesen verfügbar.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Die Gesamtanzahl der gelesenen Bytes.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Zeiger auf die Funktion wird aufgerufen, wenn Daten verfügbar sind.|  
|[CBindStatusCallback::m_pT](#m_pt)|Zeiger auf das Objekt, das den asynchronen Datenübertragung anfordern.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Zeiger auf die [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) Schnittstelle für den aktuellen Bindungsvorgang.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Zeiger auf die `IBinding` Schnittstelle für den aktuellen Bindungsvorgang.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Zeiger auf die [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) Schnittstelle für die zu verwendende URL.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle für die Datenübertragung.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CBindStatusCallback`-Klasse implementiert die `IBindStatusCallback`-Schnittstelle. `IBindStatusCallback` muss von der Anwendung implementiert werden, damit es Benachrichtigungen in einer asynchronen Datenübertragung empfangen kann. Wird verwendet, die vom System bereitgestellte asynchrone Moniker `IBindStatusCallback` Methoden zum Senden und Empfangen von Informationen zu den asynchronen Daten übertragen und aus Ihr Objekt.  
  
 In der Regel die `CBindStatusCallback` Objekt einer bestimmten Bindungsvorgang zugeordnet ist. Beispielsweise ist in der [ASYNC](../../visual-cpp-samples.md) Beispiel wird beim Festlegen der URL-Eigenschaft, es erstellt eine `CBindStatusCallback` Objekt im Aufruf von `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 Asynchrone Moniker verwendet die Rückruffunktion `OnData` Ihrer Anwendung aufgerufen werden, wenn es Daten enthält. Asynchrone Moniker wird vom System bereitgestellt.  
  
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
 Erstellt ein Objekt, um Benachrichtigungen über die asynchrone Datenübertragung zu erhalten. In der Regel wird ein Objekt für jeden Bindungsvorgang erstellt.  
  
 Außerdem initialisiert der Konstruktor [M_pT](#m_pt) und [M_pFunc](#m_pfunc) auf **NULL**.  
  
##  <a name="dtor"></a>  CBindStatusCallback:: ~ CBindStatusCallback  
 Der Destruktor.  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="download"></a>  CBindStatusCallback::Download  
 Erstellt eine `CBindStatusCallback` -Objekt und ruft `StartAsyncDownload` Herunterladen von Daten aus der angegebenen URL asynchron gestartet.  
  
```
static HRESULT Download(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 [in] Ein Zeiger auf das Objekt, das den asynchronen Datenübertragung anfordern. Die `CBindStatusCallback` Objekt ist für dieses Objekt Klasse vorlagenbasiert.  
  
 *pFunc*  
 [in] Ein Zeiger auf die Funktion, die die Daten empfängt, die gelesen wird. Die Funktion ist ein Member des Objekts Klasse vom Typ `T`. Finden Sie unter [StartAsyncDownload](#startasyncdownload) Syntax und ein Beispiel.  
  
 `bstrURL`  
 [in] Die URL zum Abrufen von Daten aus. Kann einen beliebigen gültiger URL- oder Namen. Nicht mit **NULL**. Zum Beispiel:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] Die **IUnknown** des Containers. **NULL** standardmäßig.  
  
 `bRelative`  
 [in] Ein Flag, das angibt, ob die URL relativ oder absolut ist. **"False"** standardmäßig, d. h. die URL ist absolut.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Mal, wenn Daten verfügbar sind zu diesem Objekt über gesendete `OnDataAvailable`. `OnDataAvailable` liest die Daten und ruft die Funktion verweist, zu *pFunc* (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm).  
  
##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo  
 Wird aufgerufen, um dem Moniker anweisen, wie binden.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pgrfBSCF*  
 [out] Ein Zeiger auf **BINDF** Enumerationswerte, der angibt, wie die Bind-Operation erfolgen soll. Standardmäßig festgelegt, mit der folgenden Enumerationswerte:  
  
 **BINDF_ASYNCHRONOUS** asynchronen Download.  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable` gibt **E_PENDING** bei Daten ist noch nicht verfügbar und nicht blockiert, bis Daten verfügbar sind.  
  
 **BINDF_GETNEWESTVERSION** dem Bindungsvorgang sollten die neueste Version der Daten abzurufen.  
  
 **BINDF_NOWRITECACHE** die Bind-Operation sollte abgerufene Daten nicht in den Datenträgercache gespeichert.  
  
 *pbindinfo*  
 [in, out] Ein Zeiger auf die **PARAMETERLÄNGE** Struktur ermöglicht Weitere Informationen, wie das Objekt Bindung, die auftreten, möchte.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung legt fest, die Bindung, asynchron sein und das Pushmodell von Daten verwendet wird. Im Modell datenpush-der Moniker der asynchronen Bindungsvorgangs Laufwerke und kontinuierlich den Client benachrichtigt, sobald neue Daten verfügbar ist.  
  
##  <a name="getpriority"></a>  CBindStatusCallback::GetPriority  
 Wird aufgerufen, durch die asynchrone Moniker die Priorität der Bind-Operation abgerufen.  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>Parameter  
 *pnPriority*  
 [out] Der Adresse der **lange** Variable, die bei Erfolg, die Priorität empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="m_dwavailabletoread"></a>  CBindStatusCallback::m_dwAvailableToRead  
 Kann verwendet werden, speichern Sie die Anzahl der Bytes, die gelesen werden kann.  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert auf 0 (null) `StartAsyncDownload`.  
  
##  <a name="m_dwtotalread"></a>  CBindStatusCallback::m_dwTotalRead  
 Die kumulierte Anzahl von Bytes in der asynchronen Datenübertragung zu lesen.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Hinweise  
 Jedes Mal erhöht, wenn `OnDataAvailable` wird aufgerufen, um die Anzahl der tatsächlich gelesenen Bytes. Initialisiert auf 0 (null) `StartAsyncDownload`.  
  
##  <a name="m_pfunc"></a>  CBindStatusCallback::m_pFunc  
 Die Funktion verweist `m_pFunc` wird aufgerufen, indem `OnDataAvailable` nachdem er liest die verfügbaren Daten (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm).  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion verweist `m_pFunc` ist ein Member der Klasse des Objekts und weist die folgende Syntax:  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>  CBindStatusCallback::m_pT  
 Ein Zeiger auf das Objekt, das den asynchronen Datenübertragung anfordern.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CBindStatusCallback` Objekt ist für dieses Objekt Klasse vorlagenbasiert.  
  
##  <a name="m_spbindctx"></a>  CBindStatusCallback::m_spBindCtx  
 Ein Zeiger auf ein [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) Schnittstelle, die Zugriff auf den Bindungskontext (ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang speichert) bereitstellt.  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>Hinweise  
 Im initialisierten `StartAsyncDownload`.  
  
##  <a name="m_spbinding"></a>  CBindStatusCallback::m_spBinding  
 Ein Zeiger auf die `IBinding` Schnittstelle des aktuellen Bindungsvorgangs.  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>Hinweise  
 Im initialisierten `OnStartBinding` und veröffentlichte in `OnStopBinding`.  
  
##  <a name="m_spmoniker"></a>  CBindStatusCallback::m_spMoniker  
 Ein Zeiger auf die [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) Schnittstelle für die zu verwendende URL.  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>Hinweise  
 Im initialisierten `StartAsyncDownload`.  
  
##  <a name="m_spstream"></a>  CBindStatusCallback::m_spStream  
 Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle des aktuellen Bindungsvorgangs.  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>Hinweise  
 Im initialisierten `OnDataAvailable` aus der **STGMEDIUM** Struktur, wenn die **BCSF** Flag ist **BCSF_FIRSTDATANOTIFICATION** und freigegeben, wenn die **BCSF**  Flag **BCSF_LASTDATANOTIFICATION**.  
  
##  <a name="ondataavailable"></a>  CBindStatusCallback::OnDataAvailable  
 Ruft die vom System bereitgestellten asynchrone Moniker `OnDataAvailable` Daten für das Objekt bereitstellen, sobald sie verfügbar sind.  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>Parameter  
 *grfBSCF*  
 [in] Ein **BSCF** -Enumerationswert. Eine oder mehrere der folgenden: **BSCF_FIRSTDATANOTIFICATION**, **BSCF_INTERMEDIARYDATANOTIFICATION**, oder **BSCF_LASTDATANOTIFICATION**.  
  
 `dwSize`  
 [in] Die kumulierte Datenmenge (in Byte) seit dem Beginn der Bindung zur Verfügung. Kann 0 (null), der angibt, dass die Menge der Daten nicht relevant ist oder keine bestimmten Betrag verfügbar war.  
  
 *pFormatEtc*  
 [in] Zeiger auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) -Struktur, die das Format der verfügbaren Daten enthält. Ist kein Format, kann **CF_NULL**.  
  
 *pstgmed*  
 [in] Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269) Struktur mit den tatsächlichen Daten jetzt verfügbar.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 `OnDataAvailable` liest die Daten, und ruft eine Methode für die Klasse des Objekts (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm). Finden Sie unter [CBindStatusCallback:: StartAsyncDownload](#startasyncdownload) Details.  
  
##  <a name="onlowresource"></a>  CBindStatusCallback::OnLowResource  
 Wird aufgerufen, wenn nicht genügend Ressourcen verfügbar sind.  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>Parameter  
 `dwReserved`  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="onobjectavailable"></a>  CBindStatusCallback::OnObjectAvailable  
 Wird aufgerufen, durch die asynchrone Moniker einen Schnittstellenzeiger Objekt an die Anwendung übergeben.  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>Parameter  
 `riid`  
 Der Schnittstellenbezeichner der angeforderten Schnittstelle. Nicht verwendet.  
  
 `punk`  
 Adresse von der IUnknown-Schnittstelle. Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="onprogress"></a>  CBindStatusCallback::OnProgress  
 Wird aufgerufen, um den Fortschritt einer Datenübertragungsprozesses anzugeben.  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>Parameter  
 `ulProgress`  
 Long-Integer ohne Vorzeichen. Nicht verwendet.  
  
 `ulProgressMax`  
 Long-Ganzzahl ohne Vorzeichen nicht verwendet.  
  
 `ulStatusCode`  
 Long-Integer ohne Vorzeichen. Nicht verwendet.  
  
 `szStatusText`  
 Die Adresse eines Zeichenfolgenwerts. Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="onstartbinding"></a>  CBindStatusCallback::OnStartBinding  
 Legt den Datenmember [M_spBinding](#m_spbinding) auf die `IBinding` Zeiger in `pBinding`.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>Parameter  
 `dwReserved`  
 Für zukünftige Verwendung reserviert.  
  
 `pBinding`  
 [in] Adresse der Schnittstelle des aktuellen IBinding Bindungsvorgangs. Dies darf nicht NULL sein. Der Client sollte auf dieser Zeiger auf ein Verweis auf das Bindungsobjekt verbleibt AddRef aufrufen.  
  
##  <a name="onstopbinding"></a>  CBindStatusCallback::OnStopBinding  
 Versionen der `IBinding` Zeiger in den Datenmember [M_spBinding](#m_spbinding).  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>Parameter  
 `hresult`  
 Der Statuscode aus der Bind-Operation zurückgegeben.  
  
 szStatusText  
 Die Adresse eines Zeichenfolgenwerts nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Vom System bereitgestellte asynchrone Moniker an das Ende der Bind-Operation aufgerufen.  
  
##  <a name="startasyncdownload"></a>  CBindStatusCallback:: StartAsyncDownload  
 Startet das Herunterladen von Daten aus der angegebenen URL asynchron.  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 [in] Ein Zeiger auf das Objekt, das den asynchronen Datenübertragung anfordern. Die `CBindStatusCallback` Objekt ist für dieses Objekt Klasse vorlagenbasiert.  
  
 *pFunc*  
 [in] Ein Zeiger auf die Funktion, die die Daten gelesen werden empfängt. Die Funktion ist ein Member des Objekts Klasse vom Typ `T`. Finden Sie unter **"Hinweise"** Syntax und ein Beispiel.  
  
 `bstrURL`  
 [in] Die URL zum Abrufen von Daten aus. Kann einen beliebigen gültiger URL- oder Namen. Nicht mit **NULL**. Zum Beispiel:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] Die **IUnknown** des Containers. **NULL** standardmäßig.  
  
 `bRelative`  
 [in] Ein Flag, das angibt, ob die URL relativ oder absolut ist. **"False"** standardmäßig, d. h. die URL ist absolut.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Mal, wenn Daten verfügbar sind zu diesem Objekt über gesendete `OnDataAvailable`. `OnDataAvailable` liest die Daten und ruft die Funktion verweist, zu *pFunc* (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm).  
  
 Die Funktion verweist *pFunc* ist ein Member der Klasse des Objekts und weist die folgende Syntax:  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD` `dwSize`  
  
 `);`  
  
 Im folgenden Beispiel (entnommen der [ASYNC](../../visual-cpp-samples.md) Beispiel), die Funktion `OnData` schreibt die empfangenen Daten in ein Textfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
