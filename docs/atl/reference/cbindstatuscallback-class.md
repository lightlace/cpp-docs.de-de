---
title: Klasse CBindStatusCallback | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 50a0a27528f402cda5906658cd2c9cf57a5908e8
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback-Klasse
Diese Klasse implementiert die `IBindStatusCallback`-Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
 Die Klasse, die mit der Funktion, die aufgerufen werden, wenn die Daten empfangen werden.  
  
 *nBindFlags*  
 Gibt die Bindungsflags, die von zurückgegebenen [GetBindInfo](#getbindinfo). Die standardmäßige Implementierung wird die Bindung asynchron sein, ruft die neueste Version der dem Datenobjekt ab und speichert die abgerufenen Daten nicht im Datenträgercache.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Der Konstruktor.|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|Statische Methode, die der Downloadvorgang beginnt erstellt eine `CBindStatusCallback` -Objekt und ruft `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Wird von der asynchrone Moniker zum Abrufen von Informationen für den Typ der Bindung erstellt werden soll.|  
|[CBindStatusCallback::GetPriority](#getpriority)|Wird von den asynchrone Moniker, der die Priorität des Bindungsvorgangs abrufen. Der ATL-Implementierung zurückgegeben `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Wird aufgerufen, um die Daten für Ihre Anwendung bereitstellen, sobald sie verfügbar sind. Liest die Daten, und ruft dann die Funktion übergebenen Daten verwenden.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|Wird aufgerufen, wenn Ressourcen niedrig sind. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Wird von der asynchrone Moniker einen Schnittstellenzeiger Objekt an die Anwendung übergeben. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[CBindStatusCallback::OnProgress](#onprogress)|Wird aufgerufen, um den Fortschritt einer Datenübertragungsprozesses anzugeben. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Wird aufgerufen, wenn Bindung gestartet wird.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Wird aufgerufen, wenn die asynchrone Datenübertragung angehalten wird.|  
|[CBindStatusCallback:: StartAsyncDownload](#startasyncdownload)|Verfügbare Bytes initialisiert und gelesene Bytes&0; (null), erstellt ein Push-Typ-Stream-Objekt aus einer URL und ruft `OnDataAvailable` jedes Mal, wenn Daten verfügbar sind.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Anzahl der Bytes, die zum Lesen zur Verfügung.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Die Gesamtanzahl der gelesenen Bytes.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Zeiger auf die Funktion wird aufgerufen, wenn Daten verfügbar sind.|  
|[CBindStatusCallback::m_pT](#m_pt)|Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Zeiger auf die [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) Schnittstelle für die aktuelle Bind-Operation.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Zeiger auf die `IBinding` Schnittstelle für die aktuelle Bind-Operation.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Zeiger auf die [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) Schnittstelle für die zu verwendende URL.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle für die Datenübertragung.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CBindStatusCallback`-Klasse implementiert die `IBindStatusCallback`-Schnittstelle. `IBindStatusCallback`muss von der Anwendung implementiert werden, damit sie von einem asynchronen Datenübertragung Benachrichtigungen empfangen kann. Die vom System bereitgestellte asynchrone Moniker verwendet `IBindStatusCallback` Methoden zum Senden und Empfangen von Informationen über die asynchrone Daten in und aus dem Objekt zu übertragen.  
  
 In der Regel die `CBindStatusCallback` Objekt einer bestimmten Bindungsvorgang zugeordnet ist. Z. B. in der [ASYNC](../../visual-cpp-samples.md) Beispiel beim Festlegen der URL-Eigenschaft erstellt eine `CBindStatusCallback` Objekt im Aufruf von `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing&#86;](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 Asynchrone Moniker verwendet die Callback-Funktion `OnData` Ihrer Anwendung aufgerufen werden, wenn diese Daten enthält. Asynchrone Moniker wird vom System bereitgestellt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>CBindStatusCallback::CBindStatusCallback  
 Der Konstruktor.  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Objekt zum Empfangen von Benachrichtigungen über die asynchrone Datenübertragung. In der Regel wird ein Objekt für jeden Bindungsvorgang erstellt.  
  
 Außerdem initialisiert der Konstruktor [M_pT](#m_pt) und [M_pFunc](#m_pfunc) auf **NULL**.  
  
##  <a name="dtor"></a>CBindStatusCallback:: ~ CBindStatusCallback  
 Der Destruktor.  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="download"></a>CBindStatusCallback::Download  
 Erstellt eine `CBindStatusCallback` -Objekt und ruft `StartAsyncDownload` gestartet, das Daten asynchron aus der angegebenen URL herunterladen.  
  
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
 [in] Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert. Das `CBindStatusCallback` Objekt ist für diese Objektklasse vorlagenbasiert.  
  
 *pFunc*  
 [in] Ein Zeiger auf die Funktion, die die Daten empfängt, die gelesen wird. Die Funktion ist ein Member des Objekts Klasse vom Typ `T`. Finden Sie unter [StartAsyncDownload](#startasyncdownload) Syntax und ein Beispiel.  
  
 `bstrURL`  
 [in] Die URL zum Abrufen von Daten aus. Eine beliebige gültige URL oder Dateiname kann sein. Nicht **NULL**. Zum Beispiel:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] Die **IUnknown** des Containers. **NULL** standardmäßig.  
  
 `bRelative`  
 [in] Ein Flag, das angibt, ob die URL relativ oder absolut ist. **FALSE** standardmäßig, d. h. die URL ist absolut.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Mal, wenn Daten verfügbar sind übertragen an das Objekt über `OnDataAvailable`. `OnDataAvailable`liest die Daten und ruft die Funktion, die auf den *pFunc* (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm).  
  
##  <a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo  
 Wird aufgerufen, um dem Moniker wie gebunden werden soll.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pgrfBSCF*  
 [out] Ein Zeiger auf **BINDF** -Enumerationswerte, der angibt, wie die Bind-Operation erfolgen soll. Legen Sie werden standardmäßig mit der folgenden Enumerationswerte:  
  
 **BINDF_ASYNCHRONOUS** asynchrone herunterladen.  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable` gibt **E_PENDING** Wenn Daten nicht noch verfügbar ist und nicht blockiert, bis Daten verfügbar sind.  
  
 **BINDF_GETNEWESTVERSION** Bindungsvorgang die neueste Version der Daten abrufen soll.  
  
 **BINDF_NOWRITECACHE** Bindungsvorgang sollten Sie die abgerufenen Daten im Datenträgercache nicht speichern.  
  
 *pbindinfo*  
 [in, out] Ein Zeiger auf die **PARAMETERLÄNGE** Struktur erhalten weitere Informationen, wie das Objekt Bindung erfolgen soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung wird die Bindung asynchron sein und die Daten-Push-Modell verwenden. Im Daten-Push-Modell wird der Moniker dem asynchronen Bindungsvorgang-Laufwerken und kontinuierlich benachrichtigt den Client, wenn neue Daten verfügbar sind.  
  
##  <a name="getpriority"></a>CBindStatusCallback::GetPriority  
 Wird von den asynchrone Moniker, der die Priorität des Bindungsvorgangs abrufen.  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>Parameter  
 *pnPriority*  
 [out] Adresse der **lang** Variable, die bei Erfolg die Priorität erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="m_dwavailabletoread"></a>CBindStatusCallback::m_dwAvailableToRead  
 Kann verwendet werden, speichern Sie die Anzahl der Bytes, die gelesen werden kann.  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert auf&0; (null) `StartAsyncDownload`.  
  
##  <a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead  
 Die kumulierte Anzahl von Bytes Lesen in die asynchrone Übertragung.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Hinweise  
 Jedes Mal inkrementiert `OnDataAvailable` wird aufgerufen, um die Anzahl der tatsächlich gelesenen Bytes. Initialisiert auf&0; (null) `StartAsyncDownload`.  
  
##  <a name="m_pfunc"></a>CBindStatusCallback::m_pFunc  
 Die Funktion verweist `m_pFunc` wird aufgerufen, indem `OnDataAvailable` nach liest die verfügbaren Daten (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm).  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion auf den `m_pFunc` ist ein Member der Klasse des Objekts und weist die folgende Syntax:  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>CBindStatusCallback::m_pT  
 Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Hinweise  
 Das `CBindStatusCallback` Objekt ist für diese Objektklasse vorlagenbasiert.  
  
##  <a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx  
 Ein Zeiger auf eine [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) -Schnittstelle, die Zugriff auf den Bindungskontext (ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang gespeichert).  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert in `StartAsyncDownload`.  
  
##  <a name="m_spbinding"></a>CBindStatusCallback::m_spBinding  
 Ein Zeiger auf die `IBinding` Schnittstelle des aktuellen Bindungsvorgangs.  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert in `OnStartBinding` und im freigegebenen `OnStopBinding`.  
  
##  <a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker  
 Ein Zeiger auf die [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) Schnittstelle für die zu verwendende URL.  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert in `StartAsyncDownload`.  
  
##  <a name="m_spstream"></a>CBindStatusCallback::m_spStream  
 Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle des aktuellen Bindungsvorgangs.  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert in `OnDataAvailable` aus der **STGMEDIUM** beim Strukturieren der **BCSF** Flag ist **BCSF_FIRSTDATANOTIFICATION** und freigegeben, wenn die **BCSF** Flag ist **BCSF_LASTDATANOTIFICATION**.  
  
##  <a name="ondataavailable"></a>CBindStatusCallback::OnDataAvailable  
 Asynchrone Moniker systemeigene Aufrufe `OnDataAvailable` Daten für das Objekt bereitstellen, sobald sie verfügbar sind.  
  
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
 [in] Die kumulative Datenmenge (in Byte) seit dem Beginn der Bindung zur Verfügung. Kann&0; (null), der angibt, dass die Menge der Daten nicht relevant ist oder keine verfügbar war.  
  
 *pFormatEtc*  
 [in] Zeiger auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) -Struktur, die das Format der verfügbaren Daten enthält. Wenn kein Format vorhanden ist, kann **CF_NULL**.  
  
 *pstgmed*  
 [in] Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269) -Struktur, die den tatsächlichen jetzt verfügbar Daten.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 `OnDataAvailable`liest die Daten, und ruft dann eine Methode für die Klasse des Objekts (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm). Finden Sie unter [CBindStatusCallback:: StartAsyncDownload](#startasyncdownload) Details.  
  
##  <a name="onlowresource"></a>CBindStatusCallback::OnLowResource  
 Wird aufgerufen, wenn Ressourcen niedrig sind.  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>Parameter  
 `dwReserved`  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="onobjectavailable"></a>CBindStatusCallback::OnObjectAvailable  
 Wird von der asynchrone Moniker einen Schnittstellenzeiger Objekt an die Anwendung übergeben.  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>Parameter  
 `riid`  
 Der Schnittstellenbezeichner der angeforderten Schnittstelle. Nicht verwendet.  
  
 `punk`  
 Die Adresse der IUnknown-Schnittstelle. Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="onprogress"></a>CBindStatusCallback::OnProgress  
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
 Lange Ganzzahl ohne Vorzeichen. Nicht verwendet.  
  
 `ulProgressMax`  
 Lange ganze Zahl nicht verwendet.  
  
 `ulStatusCode`  
 Lange Ganzzahl ohne Vorzeichen. Nicht verwendet.  
  
 `szStatusText`  
 Die Adresse eines Zeichenfolgenwerts. Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="onstartbinding"></a>CBindStatusCallback::OnStartBinding  
 Legt das Datenelement [M_spBinding](#m_spbinding) an der `IBinding` Zeiger in `pBinding`.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>Parameter  
 `dwReserved`  
 Für zukünftige Verwendung reserviert.  
  
 `pBinding`  
 [in] Adresse der Schnittstelle des aktuellen IBinding Bindungsvorgang. Dies darf nicht NULL sein. Der Client sollte AddRef für diesen Zeiger als Referenz auf das Binding-Objekt aufrufen.  
  
##  <a name="onstopbinding"></a>CBindStatusCallback::OnStopBinding  
 Versionen der `IBinding` Zeiger im Datenmember [M_spBinding](#m_spbinding).  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>Parameter  
 `hresult`  
 Code, der aus dem Bindungsvorgang zurückgegeben.  
  
 szStatusText  
 Die Adresse eines Zeichenfolgenwerts wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Vom System bereitgestellte asynchrone Moniker an das Ende der Bind-Operation aufgerufen.  
  
##  <a name="startasyncdownload"></a>CBindStatusCallback:: StartAsyncDownload  
 Startet die Daten asynchron aus der angegebenen URL herunterladen.  
  
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
 [in] Ein Zeiger auf das Objekt, das die asynchrone Datenübertragung anfordert. Das `CBindStatusCallback` Objekt ist für diese Objektklasse vorlagenbasiert.  
  
 *pFunc*  
 [in] Ein Zeiger auf die Funktion, die die gelesenen Daten empfängt. Die Funktion ist ein Member des Objekts Klasse vom Typ `T`. Finden Sie unter **Hinweise** Syntax und ein Beispiel.  
  
 `bstrURL`  
 [in] Die URL zum Abrufen von Daten aus. Eine beliebige gültige URL oder Dateiname kann sein. Nicht **NULL**. Zum Beispiel:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] Die **IUnknown** des Containers. **NULL** standardmäßig.  
  
 `bRelative`  
 [in] Ein Flag, das angibt, ob die URL relativ oder absolut ist. **FALSE** standardmäßig, d. h. die URL ist absolut.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Mal, wenn Daten verfügbar sind übertragen an das Objekt über `OnDataAvailable`. `OnDataAvailable`liest die Daten und ruft die Funktion, die auf den *pFunc* (z. B. die Daten zu speichern oder drucken sie auf dem Bildschirm).  
  
 Die Funktion verweist *pFunc* ist ein Member der Klasse des Objekts und weist die folgende Syntax:  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD` `dwSize`  
  
 `);`  
  
 Im folgenden Beispiel (stammt aus der [ASYNC](../../visual-cpp-samples.md) Beispiel), die Funktion `OnData` schreibt die empfangenen Daten in ein Textfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#87;](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

