---
title: CAsyncMonikerFile-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: eb8727e6fe884c98fe010beab072fb7268f2e2c4
ms.lasthandoff: 02/24/2017

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
|[CAsyncMonikerFile::Close](#close)|Schließt und gibt alle Ressourcen frei.|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|Ruft einen Zeiger auf die asynchrone Übertragung binden.|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Ruft das Format der Daten in den Stream ab.|  
|[CAsyncMonikerFile::Open](#open)|Öffnet eine Datei asynchron an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Erstellt ein COM-Objekt, das `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Wird von der OLE-System-Bibliothek zum Abrufen von Informationen für den Typ der Bindung erstellt werden soll.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|Wird von der OLE-System-Bibliothek die Priorität der Bindung abrufen.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Wird aufgerufen, um Daten bereitstellen, sobald sie an den Client während der für asynchrone Bindungsvorgänge verfügbar.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Wird aufgerufen, wenn Ressourcen niedrig sind.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|Wird aufgerufen, um Fortschritt des Datenübertragungsprozesses anzugeben.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Aufgerufen, wenn die Bindung neu gestartet wird.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Wird aufgerufen, wenn asynchrone Übertragung beendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Abgeleitet von [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), die wiederum von abgeleitet ist [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` verwendet die [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) -Schnittstelle, um alle Datenstrom asynchron zuzugreifen einschließlich asynchrones Laden von Dateien von einer URL. Die Dateien können Datenpfad-Eigenschaften von ActiveX-Steuerelementen sein.  
  
 Asynchrone Moniker sind hauptsächlich in internetfähigen und ActiveX-Steuerelementen verwendet, um eine reaktionsfähige Benutzeroberfläche während der Übertragung von Dateien bereitzustellen. Ein gutes Beispiel hierfür ist die Verwendung von [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) zum Bereitstellen asynchroner Eigenschaften für ActiveX-Steuerelemente. Das `CDataPathProperty` Objekt erhalten wiederholt einen Rückruf, der Verfügbarkeit von neuen Daten während einer langwierigen Eigenschaft Exchange anzugeben.  
  
 Weitere Informationen zur Verwendung von asynchronen Monikern und ActiveX-Steuerelemente im Internet Applications finden Sie unter den folgenden Artikeln:  
  
- [Internetgrundlagen: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [Internetgrundlagen: ActiveX-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="a-namecasyncmonikerfilea--casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile  
 Erstellt ein `CAsyncMonikerFile`-Objekt.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellt nicht die `IBindHost` Schnittstelle. `IBindHost`wird nur verwendet, wenn Sie ihn in angeben der **öffnen** Member-Funktion.  
  
 Eine Beschreibung der `IBindHost` Benutzeroberfläche, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameclosea--casyncmonikerfileclose"></a><a name="close"></a>CAsyncMonikerFile::Close  
 Rufen Sie diese Funktion zum Schließen und alle Ressourcen freizugeben.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Kann auf geöffnete oder bereits geschlossene Dateien aufgerufen werden.  
  
##  <a name="a-namecreatebindstatuscallbacka--casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback  
 Erstellt ein COM-Objekt, das `IBindStatusCallback`.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkControlling`  
 Ein Zeiger auf der controlling Unknown (die äußere **IUnknown**) oder **NULL** Wenn Aggregation nicht verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `pUnkControlling` nicht **NULL**, die Funktion gibt einen Zeiger auf die innere **IUnknown** auf eine neue COM-Unterstützung `IBindStatusCallback`. Wenn `pUnkControlling` ist **NULL**, die Funktion gibt einen Zeiger auf eine **IUnknown** auf eine neue COM-Unterstützung `IBindStatusCallback`.  
  
### <a name="remarks"></a>Hinweise  
 `CAsyncMonikerFile`erfordert ein COM-Objekt, das `IBindStatusCallback`. MFC ein solches Objekt implementiert, und es aggregiert. Sie können außer Kraft setzen `CreateBindStatusCallback` eigene COM-Objekt zurück. Das COM-Objekt kann durch Aufrufen der MFC-Implementierung aggregieren `CreateBindStatusCallback` mit der controlling Unknown des COM-Objekts. COM-Objekte implementiert, mit der `CCmdTarget` COM-Unterstützung kann rufen Sie die Steuerung des unbekannten mithilfe **CCmdTarget::GetControllingUnknown**.  
  
 Auch das COM-Objekt durch Aufrufen von MFC Implementierung delegieren kann **CreateBindStatusCallback (NULL)**.  
  
 [CAsyncMonikerFile::Open](#open) Aufrufe `CreateBindStatusCallback`.  
  
 Weitere Informationen zu asynchronen Monikern und asynchrone Bindung finden Sie unter der [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) Schnittstelle und [wie asynchrone Bindung und Speicher arbeiten](http://msdn.microsoft.com/library/windows/desktop/aa379152). Eine Erläuterung der Aggregation, finden Sie unter [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558). Alle drei Themen sind in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbindinfoa--casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo  
 Vom Client an eine asynchrone Moniker asynchrone Moniker mitteilen, wie sie binden möchte aufgerufen.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft die Einstellungen für **IBindStatusCallBack**. Eine Beschreibung der `IBindStatusCallback` Benutzeroberfläche, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung wird die Bindung asynchron auf einem Speichermedium (einen Strom) verwenden und das Daten-Push-Modell zu verwenden sein. Überschreiben Sie diese Funktion, wenn Sie das Verhalten der Bindung ändern möchten.  
  
 Ein Grund dafür wäre binden mithilfe des Daten-Pull-Modells anstelle des Daten-Push-Modells. In einem Daten-Pull-Modell der Client dem Bindungsvorgang Laufwerke und der Moniker stellt Daten nur an den Client beim Lesen. In einem Daten-Push-Modell wird der Moniker asynchrone Bindungsvorgang-Laufwerken und kontinuierlich benachrichtigt den Client, wenn neue Daten verfügbar sind.  
  
##  <a name="a-namegetbindinga--casyncmonikerfilegetbinding"></a><a name="getbinding"></a>CAsyncMonikerFile::GetBinding  
 Rufen Sie diese Funktion, um einen Zeiger auf die asynchrone Übertragung Bindung abzurufen.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IBinding` Schnittstelle bereitgestellt, wenn asynchrone Übertragung beginnt. Gibt **NULL** Wenn aus irgendeinem Grund die Übertragung asynchron durchgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Dies können Sie steuern, die Übertragung der Daten-Prozess über die `IBinding` Schnittstelle, z. B. mit **IBinding::Abort**, **IBinding::Pause**, und **IBinding::Resume**.  
  
 Eine Beschreibung der `IBinding` Benutzeroberfläche, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetformatetca--casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc  
 Rufen Sie diese Funktion, um das Format der Daten in den Datenstrom abzurufen.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Windows-Struktur [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) für den aktuell geöffneten Stream. Gibt **NULL** , wenn der Moniker nicht gebunden wurde, wenn es nicht asynchron ist, oder wenn der asynchrone Vorgang noch nicht begonnen hat.  
  
##  <a name="a-namegetprioritya--casyncmonikerfilegetpriority"></a><a name="getpriority"></a>CAsyncMonikerFile::GetPriority  
 Vom Client an eine asynchrone Moniker wird aufgerufen, wenn der Bindungsprozess gestartet wird, erhalten Sie die Priorität für den Thread für den Bindungsvorgang.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Priorität, an der die asynchrone Übertragung stattfindet. Um eine der standard-Thread-Priorität: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**, **THREAD_PRIORITY_IDLE**, **THREAD_PRIORITY_LOWEST fest**, **THREAD_PRIORITY_NORMAL**, und **THREAD_PRIORITY_TIME_CRITICAL**. Finden Sie im Windows-Funktion [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) eine Beschreibung dieser Werte.  
  
### <a name="remarks"></a>Hinweise  
 `GetPriority`sollte nicht direkt aufgerufen werden. **THREAD_PRIORITY_NORMAL** wird durch die standardmäßige Implementierung zurückgegeben.  
  
##  <a name="a-nameondataavailablea--casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable  
 Ruft eine asynchrone Moniker `OnDataAvailable` binden Sie Daten an den Client bereitstellen, sobald sie verfügbar sind, während asynchrone Vorgänge.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>Parameter  
 `dwSize`  
 Die kumulative Datenmenge (in Byte) seit dem Beginn der Bindung zur Verfügung. Kann&0; (null), der angibt, dass die Menge der Daten nicht für den Betrieb ist oder keine verfügbar war.  
  
 *bscfFlag*  
 Ein **BSCF** -Enumerationswert. Eine oder mehrere der folgenden Werte sind möglich:  
  
- **BSCF_FIRSTDATANOTIFICATION** gibt der erste Aufruf von `OnDataAvailable` für einen bestimmten Bindungsvorgang.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** identifiziert einen zwischengeschalteten Aufruf von `OnDataAvailable` für einen Vorgang gebunden.  
  
- **BSCF_LASTDATANOTIFICATION** identifiziert beim letzten Aufruf von `OnDataAvailable` für einen Vorgang gebunden.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Finden Sie im folgende Beispiel für eine beispielimplementierung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWinInet&5;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="a-nameonlowresourcea--casyncmonikerfileonlowresource"></a><a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource  
 Aufgerufen von der Moniker bei geringen Ressourcen.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `GetBinding( )-> Abort( )`.  
  
##  <a name="a-nameonprogressa--casyncmonikerfileonprogress"></a><a name="onprogress"></a>CAsyncMonikerFile::OnProgress  
 Wird von der Moniker wiederholt, um den aktuellen Status dieses Vorgangs binden, in der Regel in angemessenen Abständen während eines längeren Vorgangs anzugeben.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>Parameter  
 `ulProgress`  
 Gibt den aktuellen Status der Bindungsvorgang relativ zum erwarteten maximalen gemäß `ulProgressMax`.  
  
 `ulProgressMax`  
 Gibt die erwarteten maximalen Wert des `ulProgress` für die Dauer der Aufrufe an `OnProgress` für diesen Vorgang.  
  
 `ulStatusCode`  
 Enthält zusätzliche Informationen über den Status des Bindungsvorgangs. Gültige Werte stammen aus den `BINDSTATUS` Enumeration. Mögliche Werte finden Sie unter "Hinweise".  
  
 `szStatusText`  
 Informationen zum aktuellen Status, abhängig vom Wert `ulStatusCode`. Mögliche Werte finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Mögliche Werte für `ulStatusCode` (und die `szStatusText` für jeden Wert) sind:  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 Der Bindungsvorgang findet die Ressource, die das Objekt oder an Speicher enthält. Die `szStatusText` enthält den Anzeigenamen der zu durchsuchenden Ressource für (z. B. "www.microsoft.com").  
  
 **BINDSTATUS_CONNECTING**  
 Der Bindungsvorgang Verbindung die Ressource, die das Objekt oder an Speicher enthält. Die `szStatusText` enthält den Anzeigenamen der Ressource (z. B. eine IP-Adresse) mit verbunden wird.  
  
 **BINDSTATUS_SENDINGREQUEST**  
 Der Bindungsvorgang fordert das Objekt oder einen Speicher an. Die `szStatusText` enthält den Anzeigenamen des Objekts (z. B. ein Dateiname).  
  
 **BINDSTATUS_REDIRECTING**  
 Der Bindungsvorgang wurde an einen anderen Speicherort umgeleitet. Die `szStatusText` enthält den Anzeigenamen für den neuen Datenspeicherort.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 Der Bindungsvorgang ist das angeforderte Objekt oder Speicher über eine zwischengespeicherte Kopie abrufen. The `szStatusText` is **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 Der Bindungsvorgang begonnen hat, empfängt das Objekt oder einen Speicher an. Die `szStatusText` enthält den Anzeigenamen des Datenspeicherorts.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 Der Bindungsvorgang weiterhin das Objekt bzw. die gebunden wird, um Speicher zu erhalten. Die `szStatusText` enthält den Anzeigenamen des Datenspeicherorts.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 Der Bindungsvorgang wurde empfangen, das Objekt oder einen Speicher an. Die `szStatusText` enthält den Anzeigenamen des Datenspeicherorts.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 Eine Instanz des Objekts an gebunden wird, wird nur erstellt werden. Die `szStatusText` enthält die CLSID des neuen Objekts im Zeichenfolgenformat, durch die der Client, den Bindungsvorgang abzubrechen, falls gewünscht.  
  
##  <a name="a-nameonstartbindinga--casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding  
 Überschreiben Sie diese Funktion in den abgeleiteten Klassen Aktionen durchzuführen, wenn die Bindung neu gestartet wird.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von den Moniker wieder aufgerufen. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="a-nameonstopbindinga--casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding  
 Wird von der Moniker am Ende der Bind-Operation aufgerufen.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>Parameter  
 `hresult`  
 Ein `HRESULT` , den Fehler oder Warnungswert.  
  
 *szErrort*  
 Eine Zeichenfolge, die den Fehler beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um Aktionen durchzuführen, wenn die Übertragung beendet wird. Standardmäßig gibt die Funktion `IBinding`.  
  
 Eine Beschreibung der `IBinding` Benutzeroberfläche, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameopena--casyncmonikerfileopen"></a><a name="open"></a>CAsyncMonikerFile::Open  
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
 Ein Zeiger auf die Datei, die asynchron geöffnet werden. Die Datei kann eine beliebige gültige URL oder der Dateiname sein.  
  
 `pError`  
 Ein Zeiger auf die Datei Ausnahmen. Falls ein Fehler auftritt wird es auf die Ursache festgelegt werden.  
  
 `pMoniker`  
 Ein Zeiger auf die Schnittstelle für asynchrone Moniker `IMoniker`, präzise Moniker, die Sie abrufen können, mit der Kombination aus den Moniker des Dokuments wird **IOleClientSite::GetMoniker (** *OLEWHICHMK_CONTAINER* **)**, und einen Moniker, der aus den Pfadnamen erstellt. Das Steuerelement kann diesen Moniker Binden verwenden, dies ist jedoch nicht den Moniker, den das Steuerelement gespeichert werden sollen.  
  
 *pBindHost*  
 Ein Zeiger auf die `IBindHost` -Schnittstelle, die verwendet wird, um den Moniker aus einen ggf. relativen Pfadnamen zu erstellen. Wenn die Bind-Host ungültig ist oder keinen Moniker bietet, der Aufruf wird standardmäßig die **öffnen (** `lpszFileName` **,**`pError`**)**. Eine Beschreibung der `IBindHost` Benutzeroberfläche, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pServiceProvider`  
 Ein Zeiger auf die `IServiceProvider`-Schnittstelle. Wenn der Dienstanbieter ungültig ist oder nicht die versorgen `IBindHost`, der Aufruf wird standardmäßig auf **öffnen (** `lpszFileName` **,**`pError`**)**.  
  
 *pUnknown*  
 Ein Zeiger auf die **IUnknown** Schnittstelle. Wenn `IServiceProvider` gefunden wird, wird die Funktion fragt `IBindHost`. Wenn der Dienstanbieter ungültig ist oder nicht die versorgen `IBindHost`, der Aufruf wird standardmäßig auf **öffnen (** `lpszFileName` **,**`pError`**)**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Datei erfolgreich geöffnet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf startet der Bindung.  
  
 Sie können eine URL oder einen Dateinamen für die `lpszURL` Parameter. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWinInet&6;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 – oder –  
  
 [!code-cpp[NVC_MFCWinInet&#7;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CMonikerFile-Klasse](../../mfc/reference/cmonikerfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMonikerFile-Klasse](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)

