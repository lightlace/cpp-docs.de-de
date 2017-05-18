---
title: CAsyncMonikerFile Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- monikers [C++], MFC
- asynchronous controls [C++]
- CAsyncMonikerFile class
- IMoniker interface, binding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: 23
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 47ba3137b5d0d38aa59e9d627101de8350eebd50
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile-Klasse
Stellt Funktionalität für die Verwendung von asynchronen Monikern in ActiveX-Steuerelementen (früher OLE-Steuerelemente) bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Erstellt ein `CAsyncMonikerFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|Wird geschlossen, und gibt alle Ressourcen frei.|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|Ruft einen Zeiger auf die asynchrone Übertragung Bindung ab.|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Ruft das Format der Daten in den Stream ab.|  
|[CAsyncMonikerFile::Open](#open)|Öffnet eine Datei asynchron an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Erstellt ein COM-Objekt, das implementiert `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Wird aufgerufen, von der OLE-System-Bibliothek zum Anfordern von Informationen für den Typ der Bindung erstellt werden soll.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|Wird aufgerufen, von der OLE-System-Bibliothek, die Priorität der Bindung abgerufen wird.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Wird aufgerufen, um Daten bereitzustellen, sobald sie an den Client während der für asynchrone Bindungsvorgänge verfügbar.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Wird aufgerufen, wenn nicht genügend Ressourcen verfügbar sind.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|Wird aufgerufen, um Fortschritt des Datenübertragungsprozesses anzugeben.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Wird aufgerufen, wenn Bindung gestartet wird.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Wird aufgerufen, wenn asynchrone Übertragung beendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Abgeleitet [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), die wiederum von abgeleitet ist [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` verwendet die [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) -Schnittstelle verwenden, um einem beliebigen Datenstream asynchron ausgeführt wird, Zugriff auf einschließlich asynchron laden von Dateien von einer URL. Die Dateien können datenpfadclusterressourcen Eigenschaften von ActiveX-Steuerelementen sein.  
  
 Asynchrone Moniker dienen in erster Linie im Internet-fähigen Anwendungen und ActiveX-Steuerelementen reaktionsfähige Benutzeroberfläche während der Übertragung von Dateien anzugeben. Ein gutes Beispiel hierfür ist die Verwendung von [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) ActiveX-Steuerelemente asynchrone Eigenschaften bereit. Die `CDataPathProperty` Objekt wiederholt einen Rückruf an, dass die Verfügbarkeit der neuen Daten während einer langwierigen Eigenschaft Exchange erhalten.  
  
 Weitere Informationen zum Verwenden von asynchronen Monikern und ActiveX-Steuerelemente im Internet-Anwendungen finden Sie unter den folgenden Artikeln:  
  
- [Internetgrundlagen: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [Internetgrundlagen: ActiveX-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile  
 Erstellt ein `CAsyncMonikerFile`-Objekt.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>Hinweise  
 Werden keine erstellt die `IBindHost` Schnittstelle. `IBindHost`wird verwendet, nur dann, wenn Sie ihn im Angeben der **öffnen** Memberfunktion.  
  
 Eine Beschreibung der `IBindHost` Schnittstelle, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="close"></a>CAsyncMonikerFile::Close  
 Mit dieser Funktion wird zum Schließen und alle Ressourcen freizugeben.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Kann auf geöffnete oder bereits geschlossen Dateien aufgerufen werden.  
  
##  <a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback  
 Erstellt ein COM-Objekt, das implementiert `IBindStatusCallback`.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkControlling`  
 Ein Zeiger auf die controlling Unknown (die äußere **IUnknown**) oder **NULL** Aggregation nicht mehr verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `pUnkControlling` nicht **NULL**, die Funktion gibt einen Zeiger auf die innere **IUnknown** auf eine neue COM-Unterstützung `IBindStatusCallback`. Wenn `pUnkControlling` ist **NULL**, die Funktion gibt einen Zeiger auf eine **IUnknown** auf eine neue COM-Unterstützung `IBindStatusCallback`.  
  
### <a name="remarks"></a>Hinweise  
 `CAsyncMonikerFile`erfordert ein COM-Objekt, das implementiert `IBindStatusCallback`. MFC implementiert ein solches Objekt, und es aggregiert wird. Sie können außer Kraft setzen `CreateBindStatusCallback` eigene COM-Objekt zurückgegeben. Das COM-Objekt kann MFC Implementierung aggregieren, durch den Aufruf `CreateBindStatusCallback` mit der controlling Unknown COM-Objekts. COM-Objekte implementiert, mit der `CCmdTarget` COM-Unterstützung kann rufen Sie die steuernde unbekannte mithilfe **CCmdTarget::GetControllingUnknown**.  
  
 Klicken Sie alternativ das COM-Objekt durch Aufrufen von MFC Implementierung delegieren kann **CreateBindStatusCallback (NULL)**.  
  
 [CAsyncMonikerFile::Open](#open) Aufrufe `CreateBindStatusCallback`.  
  
 Weitere Informationen zu asynchronen Monikern und asynchrone Bindung finden Sie unter der [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) Schnittstelle und [wie asynchrone Bindung "und" Speicher-Arbeit](http://msdn.microsoft.com/library/windows/desktop/aa379152). Eine Erläuterung der Aggregation, finden Sie unter [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558). Alle drei Themen sind in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo  
 Vom Client an eine asynchrone Moniker asynchrone Moniker mitteilen, wie sie binden möchte aufgerufen.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft die Einstellungen ab **IBindStatusCallBack**. Eine Beschreibung der `IBindStatusCallback` Schnittstelle, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung legt fest, die Bindung auf einem Speichermedium (einen Stream) zu verwenden und so verwenden Sie das Modell datenpush-asynchron sein. Überschreiben Sie diese Funktion, wenn Sie das Verhalten der Bindung ändern möchten.  
  
 Ein Grund dafür wäre mithilfe des Daten-Pull-Modells anstelle des datenpush Modells zu binden. In einem Modell Daten Pull-Client Laufwerke die Bind-Operation, und der Moniker bietet Daten nur an den Client, wenn sie gelesen werden kann. In einem Modell datenpush-der Moniker der asynchronen Bindungsvorgangs Laufwerke und kontinuierlich den Client benachrichtigt, sobald neue Daten verfügbar ist.  
  
##  <a name="getbinding"></a>CAsyncMonikerFile::GetBinding  
 Rufen Sie diese Funktion, um einen Zeiger auf die asynchrone Übertragung binden abzurufen.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IBinding` Schnittstelle bereitgestellt, wenn asynchrone Übertragung beginnt. Gibt **NULL** Wenn aus irgendeinem Grund die Übertragung asynchron hergestellt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch können Sie steuern, die die Datenübertragung Prozess über den `IBinding` -Schnittstelle ein, z. B. mit **IBinding::Abort**, **IBinding::Pause**, und **IBinding::Resume**.  
  
 Eine Beschreibung der `IBinding` Schnittstelle, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc  
 Mit dieser Funktion wird zum Abrufen von des Formats der Daten in den Stream.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Windows-Struktur [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) für den aktuell geöffneten Stream. Gibt **NULL** , wenn der Moniker nicht gebunden wurde, wenn es nicht asynchron ist, oder wenn der asynchrone Vorgang nicht begonnen wurde.  
  
##  <a name="getpriority"></a>CAsyncMonikerFile::GetPriority  
 Vom Client an eine asynchrone Moniker wird aufgerufen, wenn die Bindung Prozessstart empfangen Sie die Priorität an den Thread des Bindungsvorgangs.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Priorität, an der der asynchrone Übertragung stattfindet. Eines der standardmäßigen Thread Priorität Flags: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**, **THREAD_PRIORITY_IDLE**, **Rangfolge von THREAD_PRIORITY_LOWEST**, **THREAD_PRIORITY_NORMAL**, und **THREAD_PRIORITY_TIME_CRITICAL**. Finden Sie im Windows-Funktion [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) eine Beschreibung dieser Werte.  
  
### <a name="remarks"></a>Hinweise  
 `GetPriority`sollte nicht direkt aufgerufen werden. **THREAD_PRIORITY_NORMAL** von die standardmäßige Implementierung zurückgegeben wird.  
  
##  <a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable  
 Ruft eine asynchrone Moniker `OnDataAvailable` binden Sie um die Daten an den Client bereitstellen, sobald sie verfügbar sind, während der asynchronen Vorgänge.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>Parameter  
 `dwSize`  
 Die kumulierte Datenmenge (in Byte) seit dem Beginn der Bindung zur Verfügung. Kann 0 (null), der angibt, dass die Menge der Daten nicht an den Vorgang relevant ist oder keine bestimmten Betrag verfügbar war.  
  
 *bscfFlag*  
 Ein **BSCF** -Enumerationswert. Hierbei kann es sich um eine oder mehrere der folgenden Werte sein:  
  
- **BSCF_FIRSTDATANOTIFICATION** bezeichnet den ersten Aufruf von `OnDataAvailable` für einen bestimmten Bindungsvorgangs.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** identifiziert einen zwischengeschalteten Aufruf `OnDataAvailable` für einen Bindevorgang.  
  
- **BSCF_LASTDATANOTIFICATION** identifiziert beim letzten Aufruf von `OnDataAvailable` für einen Bindevorgang.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Sehen Sie im folgenden Beispiel für eine beispielimplementierung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWinInet Nr. 5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource  
 Wird von der Moniker aufgerufen, wenn nicht genügend Ressourcen verfügbar sind.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft `GetBinding( )-> Abort( )`.  
  
##  <a name="onprogress"></a>CAsyncMonikerFile::OnProgress  
 Wird aufgerufen, durch den Moniker wiederholt, um den aktuellen Status dieses Vorgangs Bindung in der Regel in angemessenen Abständen während eines längeren Vorgangs anzugeben.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>Parameter  
 `ulProgress`  
 Gibt den aktuellen Status der relativ zum erwarteten maximalen angegeben, dem Bindungsvorgang `ulProgressMax`.  
  
 `ulProgressMax`  
 Gibt an, die erwartete maximale Wert des `ulProgress` für die Dauer der Aufrufe an `OnProgress` für diesen Vorgang.  
  
 `ulStatusCode`  
 Enthält zusätzliche Informationen über den Status des Bindungsvorgangs. Gültige Werte stammen aus den `BINDSTATUS` Enumeration. Mögliche Werte finden Sie unter "Hinweise".  
  
 `szStatusText`  
 Informationen zum aktuellen Status, abhängig vom Wert `ulStatusCode`. Mögliche Werte finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Mögliche Werte für `ulStatusCode` (und die `szStatusText` für jeden Wert) sind:  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 Die Bind-Operation findet die Ressource, die das Objekt oder die speicherplatzbegrenzung auf enthält. Die `szStatusText` enthält den Anzeigenamen der zu durchsuchenden Ressource für (z. B. "www.microsoft.com").  
  
 **BINDSTATUS_CONNECTING**  
 Die Bind-Operation wird auf die Ressource eine Verbindung herstellen, der das Objekt oder die speicherplatzbegrenzung enthält. Die `szStatusText` enthält den Anzeigenamen der Ressource, die aktuell mit verbunden sind (z. B. eine IP-Adresse).  
  
 **BINDSTATUS_SENDINGREQUEST**  
 Die Bind-Operation wird das Objekt oder die speicherplatzbegrenzung zu angefordert. Die `szStatusText` enthält den Anzeigenamen des Objekts (z. B. ein Dateiname).  
  
 **BINDSTATUS_REDIRECTING**  
 Die Bind-Operation wurde auf einen anderen Datenspeicherort umgeleitet. Die `szStatusText` enthält den Anzeigenamen für den neuen Datenspeicherort.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 Die Bind-Operation wird das angeforderte Objekt oder Speicher über eine zwischengespeicherte Kopie abrufen. The `szStatusText` is **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 Die Bind-Operation begonnen hat, das Objekt oder die speicherplatzbegrenzung zu empfangen. Die `szStatusText` enthält den Anzeigenamen des Datenspeicherorts.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 Bindung weiterhin auf das Objekt oder die speicherplatzbegrenzung zu erhalten. Die `szStatusText` enthält den Anzeigenamen des Datenspeicherorts.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 Die Bind-Operation wurde das Objekt oder die speicherplatzbegrenzung zu empfangen. Die `szStatusText` enthält den Anzeigenamen des Datenspeicherorts.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 Eine Instanz des Objekts an wird nur erstellt werden. Die `szStatusText` bietet die CLSID des neuen Objekts im Zeichenfolgenformat, sodass die Möglichkeit, die den Bindungsvorgang "Abbrechen" bei Bedarf.  
  
##  <a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding  
 Überschreiben Sie diese Funktion in Ihren abgeleiteten Klassen aus, um Aktionen durchzuführen, wenn die Bindung neu gestartet wird.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Moniker wieder aufgerufen werden. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding  
 Wird von der Moniker am Ende der Bind-Operation aufgerufen.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>Parameter  
 `hresult`  
 Ein `HRESULT` also den Fehler oder Warnungswert.  
  
 *szErrort*  
 Eine Zeichenfolge, die den Fehler beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um Aktionen durchzuführen, wenn die Übertragung beendet wird. Standardmäßig gibt die Funktion `IBinding`.  
  
 Eine Beschreibung der `IBinding` Schnittstelle, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="open"></a>CAsyncMonikerFile::Open  
 Rufen Sie diese Memberfunktion, um eine Datei asynchron zu öffnen.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszURL`  
 Ein Zeiger auf die Datei, die asynchron geöffnet werden. Die Datei kann eine beliebige gültige URL oder Dateiname sein.  
  
 `pError`  
 Ein Zeiger auf die Datei Ausnahmen. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.  
  
 `pMoniker`  
 Ein Zeiger auf die Schnittstelle für die asynchrone Moniker `IMoniker`, ein Moniker ist präzise, die Sie abrufen können, mit der Kombination aus den Moniker des Dokuments wird **IOleClientSite::GetMoniker (** *OLEWHICHMK_CONTAINER* **)**, und ein Moniker, der aus dem Pfadnamen erstellt. Das Steuerelement kann diesen Moniker Binden verwenden, jedoch ist dies nicht der verwendete Moniker, den des Steuerelements gespeichert werden soll.  
  
 *pBindHost*  
 Ein Zeiger auf die `IBindHost` -Schnittstelle, die verwendet wird, um den Moniker aus einem potenziell relativen Pfadnamen zu erstellen. Wenn der Bind-Host ungültig ist oder enthält keinen Moniker ist, wird standardmäßig der Aufruf zum **öffnen (** `lpszFileName` **,**`pError`**)**. Eine Beschreibung der `IBindHost` Schnittstelle, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pServiceProvider`  
 Ein Zeiger auf die `IServiceProvider`-Schnittstelle. Wenn der Dienstanbieter ungültig ist, oder geben Sie den Dienst für nicht `IBindHost`, der Aufruf wird standardmäßig auf **öffnen (** `lpszFileName` **,**`pError`**)**.  
  
 *pUnknown*  
 Ein Zeiger auf die **IUnknown** Schnittstelle. Wenn `IServiceProvider` gefunden wird, wird die Funktion fragt für `IBindHost`. Wenn der Dienstanbieter ungültig ist, oder geben Sie den Dienst für nicht `IBindHost`, der Aufruf wird standardmäßig auf **öffnen (** `lpszFileName` **,**`pError`**)**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Datei erfolgreich geöffnet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf initiiert des Bindungsvorgangs.  
  
 Sie können eine URL oder einen Dateinamen für die `lpszURL` Parameter. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWinInet 6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 - ODER  
  
 [!code-cpp[NVC_MFCWinInet #7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CMonikerFile-Klasse](../../mfc/reference/cmonikerfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMonikerFile-Klasse](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)

