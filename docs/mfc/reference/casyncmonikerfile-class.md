---
title: CAsyncMonikerFile-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c40d012ba32d2ea656024af77779f2cf8f67419a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433023"
---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile-Klasse

Stellt Funktionalität für die Verwendung von asynchronen Monikern in ActiveX-Steuerelementen (früher OLE-Steuerelemente) bereit.

## <a name="syntax"></a>Syntax

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Erstellt ein `CAsyncMonikerFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncMonikerFile::Close](#close)|Schließt ein, und gibt alle Ressourcen frei.|
|[CAsyncMonikerFile::GetBinding](#getbinding)|Ruft einen Zeiger auf den asynchronen Transfer Bindung ab.|
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Ruft das Format der Daten in den Stream ab.|
|[CAsyncMonikerFile::Open](#open)|Öffnet eine Datei asynchron an.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Erstellt ein COM-Objekt, das implementiert `IBindStatusCallback`.|
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Wird aufgerufen, von der OLE-System-Bibliothek zum Anfordern von Informationen für den Typ der Bindung erstellt werden.|
|[CAsyncMonikerFile::GetPriority](#getpriority)|Wird aufgerufen, durch die OLE-System-Bibliothek, um die Priorität der Bindung zu erhalten.|
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Wird aufgerufen, um Daten bereitzustellen, wenn sie an den Client während der für asynchrone Bindungsvorgänge verfügbar.|
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Wird aufgerufen, wenn die Ressourcen niedrig sind.|
|[CAsyncMonikerFile::OnProgress](#onprogress)|Wird aufgerufen, um den Status des Datenübertragungsprozesses anzuzeigen.|
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Aufgerufen, wenn die Bindung gestartet wird.|
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Wird aufgerufen, wenn asynchrone Übertragung angehalten wird.|

## <a name="remarks"></a>Hinweise

Von abgeleiteten [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), die wiederum von abgeleitet ist [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` verwendet die [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) Schnittstelle für alle Datenstrom zuzugreifen asynchron, einschließlich asynchron laden von Dateien aus einer URL. Die Dateien können Datenpfad-Eigenschaften des ActiveX-Steuerelemente werden.

Asynchrone Moniker werden in erster Linie in internetfähige Anwendungen und ActiveX-Steuerelemente verwendet, um eine reaktionsfähige Benutzeroberfläche während der Übertragung von Dateien bereitzustellen. Ein gutes Beispiel hierfür ist die Verwendung von [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) zum Bereitstellen von asynchroner Eigenschaften für ActiveX-Steuerelemente. Die `CDataPathProperty` Objekt wiederholt einen Rückruf an, dass die Verfügbarkeit neuer Daten während einer langwierigen Eigenschaft Exchange erhalten.

Weitere Informationen zur Verwendung von asynchronen Monikern und ActiveX-Steuerelementen in Internet-Anwendungen finden Sie unter den folgenden Artikeln:

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

##  <a name="casyncmonikerfile"></a>  CAsyncMonikerFile::CAsyncMonikerFile

Erstellt ein `CAsyncMonikerFile`-Objekt.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>Hinweise

Er erstellt keine der `IBindHost` Schnittstelle. `IBindHost` wird nur verwendet, wenn Sie ihn im Angeben der `Open` Member-Funktion.

Eine Beschreibung der `IBindHost` Schnittstelle, finden Sie im Windows SDK.

##  <a name="close"></a>  CAsyncMonikerFile::Close

Mit dieser Funktion können Sie schließen, und gibt alle Ressourcen frei.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Kann für nicht geöffneten oder bereits geschlossenen Dateien aufgerufen werden.

##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback

Erstellt ein COM-Objekt, das implementiert `IBindStatusCallback`.

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>Parameter

*pUnkControlling*<br/>
Ein Zeiger auf die controlling Unknown (die äußere `IUnknown`) oder NULL, wenn Aggregation nicht verwendet wird.

### <a name="return-value"></a>Rückgabewert

Wenn *pUnkControlling* ist nicht NULL ist, die Funktion gibt einen Zeiger auf die innere `IUnknown` auf eine neue COM-Unterstützung `IBindStatusCallback`. Wenn `pUnkControlling` NULL ist, die Funktion gibt einen Zeiger auf ein `IUnknown` auf eine neue COM-Unterstützung `IBindStatusCallback`.

### <a name="remarks"></a>Hinweise

`CAsyncMonikerFile` erfordert einen COM-Objekt, das implementiert `IBindStatusCallback`. MFC implementiert ein solches Objekt, und es aggregiert. Sie können außer Kraft setzen `CreateBindStatusCallback` eigene COM-Objekt zurück. Das COM-Objekt kann die Implementierung von MFC aggregieren, durch den Aufruf `CreateBindStatusCallback` mit dem unbekannten Steuern des COM-Objekts. COM-Objekte, die mithilfe von implementiert die `CCmdTarget` COM-Unterstützung kann rufen Sie die Steuerung des unbekannten mithilfe `CCmdTarget::GetControllingUnknown`.

Alternativ können Sie das COM-Objekt durch Aufrufen von MFC Implementierung delegieren kann `CreateBindStatusCallback( NULL )`.

[CAsyncMonikerFile::Open](#open) Aufrufe `CreateBindStatusCallback`.

Weitere Informationen zu asynchronen Monikern und asynchrone Datenbindung, finden Sie unter den [IBindStatusCallback](https://msdn.microsoft.com/library/ie/ms775060) Schnittstelle und [wie asynchrone Bindung "und" Speicher Arbeit](/windows/desktop/Stg/how-asynchronous-binding-and-storage-work). Eine Erläuterung der Aggregation, finden Sie unter [Aggregation](/windows/desktop/com/aggregation). Alle drei Themen sind im Windows SDK.

##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo

Wird aufgerufen, von der Client eines asynchronen Monikers dem asynchronen Moniker mitteilen, wie sie binden möchte.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>Rückgabewert

Ruft ab, das die Einstellungen für `IBindStatusCallBack`. Eine Beschreibung der `IBindStatusCallback` Schnittstelle, finden Sie im Windows SDK.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung legt fest, die Bindung an, das Daten-Push-Modell verwenden und mit einem Speichermedium (Datenstrom) asynchron sein. Überschreiben Sie diese Funktion, wenn Sie das Verhalten der Bindung ändern möchten.

So binden mithilfe des Daten-Pull-Modells anstelle des Daten-Push-Modells ist ein Grund dafür wäre. In einem Daten-Pull-Modell der Client steuert den Bindevorgang auszuführen, und der Moniker stellt Daten nur an den Client, wenn es gelesen wird. In einem Daten-Push-Modell der Moniker der asynchronen Bindungsvorgang Laufwerke und kontinuierlich benachrichtigt den Client, wenn neue Daten verfügbar sind.

##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding

Rufen Sie diese Funktion, um einen Zeiger auf den asynchronen Transfer Bindung abzurufen.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `IBinding` Schnittstelle, die bereitgestellt werden, wenn die asynchrone Übertragung beginnt. Gibt NULL bei einem beliebigen Grund die Übertragung können nicht asynchron erfolgen.

### <a name="remarks"></a>Hinweise

Dies können Sie steuern, die die Datenübertragung Prozess über den `IBinding` Schnittstelle, z. B. mit `IBinding::Abort`, `IBinding::Pause`, und `IBinding::Resume`.

Eine Beschreibung der `IBinding` Schnittstelle, finden Sie im Windows SDK.

##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc

Rufen Sie diese Funktion, um das Format der Daten in den Datenstrom abzurufen.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Windows-Struktur [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) für den aktuell geöffneten Stream. Gibt NULL zurück, wenn der Moniker nicht gebunden wurde, wenn es nicht asynchron ist, oder wenn der asynchrone Vorgang noch nicht begonnen hat.

##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority

Vom Client der eines asynchronen Monikers aufgerufen, während des Bindungsvorgangs gestartet wird, erhalten Sie die Priorität an den Thread für die Durchführung des Bindungsvorgangs.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>Rückgabewert

Die Priorität, an der die asynchrone Übertragung stattfinden soll. Zu den Flags der standard-Thread-Priorität: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST fest, THREAD_PRIORITY_NORMAL und THREAD_PRIORITY_TIME_CRITICAL. Finden Sie im Windows-Funktion [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) eine Beschreibung dieser Werte.

### <a name="remarks"></a>Hinweise

`GetPriority` sollte nicht direkt aufgerufen werden. THREAD_PRIORITY_NORMAL wird von der Standardimplementierung zurückgegeben.

##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable

Ruft ein asynchrones Monikers `OnDataAvailable` binden Sie um die Daten an den Client bereitzustellen, sobald diese verfügbar werden, während der asynchronen Vorgänge.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>Parameter

*dwSize*<br/>
Den kumulativen Zeitraum (in Byte) der Daten, die seit dem Beginn der Bindung zur Verfügung. Kann 0 (null), der angibt, dass die Menge der Daten nicht für den Betrieb relevant ist oder keine verfügbar war.

*bscfFlag*<br/>
Ein Wert für den BSCF-Enumeration. Eine oder mehrere der folgenden Werte sind möglich:

- BSCF_FIRSTDATANOTIFICATION identifiziert, der erste Aufruf `OnDataAvailable` für einen angegebenen Bindevorgang.

- BSCF_INTERMEDIATEDATANOTIFICATION identifiziert einen zwischengeschalteten Aufruf `OnDataAvailable` für einen Bindevorgang.

- BSCF_LASTDATANOTIFICATION identifiziert, den letzten Aufruf von `OnDataAvailable` für einen Bindevorgang.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Das folgende Beispiel veranschaulicht ein Beispiel für die Implementierung wird angezeigt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource

Wird vom Moniker aufgerufen, wenn die Ressourcen niedrig sind.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>Hinweise

Die Standardimplementierung ruft `GetBinding( )-> Abort( )`.

##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress

Wird aufgerufen, durch den Moniker wiederholt, um den aktuellen Status dieses Vorgangs gebunden, in der Regel in angemessenen Abständen während eines längeren Vorgangs anzugeben.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>Parameter

*ulProgress*<br/>
Gibt den aktuellen Status des Bindevorgangs relativ zum erwarteten maximalen in angegebenen *UlProgressMax*.

*ulProgressMax*<br/>
Gibt an, der erwartete maximale Wert des *UlProgress* für die Dauer der Aufrufe von `OnProgress` für diesen Vorgang.

*ulStatusCode*<br/>
Enthält zusätzliche Informationen über den Status des Bindevorgangs. Gültige Werte stammen aus der `BINDSTATUS` Enumeration. Mögliche Werte finden Sie unter "Hinweise".

*szStatusText*<br/>
Informationen zum aktuellen Status, abhängig vom Wert *UlStatusCode*. Mögliche Werte finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Mögliche Werte für *UlStatusCode* (und die *SzStatusText* für jeden Wert) sind:

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |Der Bindungsvorgang findet die Ressource, die das Objekt oder den Speicher, die an enthält. Die *SzStatusText* gibt den Anzeigenamen der Ressource gesucht wird für (beispielsweise "www.microsoft.com").  |
|BINDSTATUS_CONNECTING  |Der Bindungsvorgang ist mit der Ressource verbunden, die das Objekt oder den Speicher, die an enthält. Die *SzStatusText* gibt den Anzeigenamen der Ressource, die mit (z. B. eine IP-Adresse) verbunden wird.  |
|BINDSTATUS_SENDINGREQUEST|Der Bindungsvorgang anfordert das Objekt oder den Speicher, die an. Die *SzStatusText* gibt den Anzeigenamen des Objekts (z. B. ein Dateiname).|
|BINDSTATUS_REDIRECTING  |Der Bindungsvorgang wurde auf einen anderen Datenspeicherort umgeleitet. Die *SzStatusText* gibt den Anzeigenamen des neuen Datenspeicherorts an.  |
|BINDSTATUS_USINGCACHEDCOPY  |Der Bindungsvorgang abruft das angeforderte Objekt oder den Speicher aus einer zwischengespeicherten Kopie. Die *SzStatusText* ist NULL.  |
|BINDSTATUS_BEGINDOWNLOADDATA  |Der Bindungsvorgang wurde gestartet empfangen des Objekts oder Speichers, die gebunden wird. Die *SzStatusText* gibt den Anzeigenamen des Datenspeicherorts an.|
|BINDSTATUS_DOWNLOADINGDATA  |Der Bindungsvorgang fortgesetzt wird, zum Empfangen des Objekts oder Speichers, die gebunden wird. Die *SzStatusText* gibt den Anzeigenamen des Datenspeicherorts an.  |
|BINDSTATUS_ENDDOWNLOADDATA  |Der Bindungsvorgang wurde empfangen des Objekts oder Speichers, die gebunden wird. Die *SzStatusText* gibt den Anzeigenamen des Datenspeicherorts an.  |
|BINDSTATUS_CLASSIDAVAILABLE  |Eine Instanz des Objekts an wird nur erstellt werden. Die *SzStatusText* bietet die CLSID des neuen Objekts im Zeichenfolgenformat, sodass die Möglichkeit zum Abbrechen der Bindungsvorgang bei Bedarf.  |

##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding

Überschreiben Sie diese Funktion in Ihrer abgeleiteten Klassen, die Aktionen ausführen, wenn die Bindung gestartet wird.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird vom Moniker wieder aufgerufen. Bei der Standardimplementierung wird keine Aktion ausgeführt.

##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding

Wird aufgerufen, durch den Moniker am Ende der Bindungsvorgang.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>Parameter

*HRESULT*<br/>
Ein HRESULT, das den Fehler oder Warnungswert ist.

*szErrort*<br/>
Eine Zeichenfolge, die Beschreibung des Fehlers.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um Aktionen durchzuführen, wenn der Transfer beendet ist. Standardmäßig gibt die Funktion `IBinding`.

Eine Beschreibung der `IBinding` Schnittstelle, finden Sie im Windows SDK.

##  <a name="open"></a>  CAsyncMonikerFile::Open

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

*lpszURL*<br/>
Ein Zeiger auf die Datei, die asynchron geöffnet werden. Die Datei kann es sich um gültige URL oder der Dateiname sein.

*pError*<br/>
Ein Zeiger auf die Datei-Ausnahmen. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.

*pMoniker*<br/>
Ein Zeiger auf die Schnittstelle für asynchrone Moniker `IMoniker`, eine genaue Moniker, der die Kombination aus den Moniker des Dokuments ist, die Sie mit abrufen können `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`, und einen Moniker, der aus dem Pfadnamen erstellt. Das Steuerelement kann diesen Moniker zum Binden verwenden, dies ist jedoch nicht den Moniker, die, den das Steuerelement gespeichert werden sollen.

*pBindHost*<br/>
Ein Zeiger auf die `IBindHost` -Schnittstelle, die verwendet wird, um den Moniker aus einen ggf. relativen Pfadnamen zu erstellen. Wenn der Host für die Bindung ungültig ist oder keine Moniker bietet, der Aufruf wird standardmäßig `Open(lpszFileName,pError)`. Eine Beschreibung der `IBindHost` Schnittstelle, finden Sie im Windows SDK.

*pServiceProvider*<br/>
Ein Zeiger auf die `IServiceProvider`-Schnittstelle. Wenn der Dienstanbieter ungültig ist, oder geben Sie den Dienst für nicht `IBindHost`, der Aufruf standardmäßig `Open(lpszFileName,pError)`.

*pUnknown*<br/>
Ein Zeiger auf die `IUnknown`-Schnittstelle. Wenn `IServiceProvider` gefunden wird, wird die Funktion fragt `IBindHost`. Wenn der Dienstanbieter ungültig ist, oder geben Sie den Dienst für nicht `IBindHost`, der Aufruf standardmäßig `Open(lpszFileName,pError)`.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Datei erfolgreich geöffnet wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Dieser Aufruf initiiert den Bindungsprozess.

Sie können eine URL oder einen Dateinamen für die *LpszURL* Parameter. Zum Beispiel:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- oder –

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>Siehe auch

[CMonikerFile-Klasse](../../mfc/reference/cmonikerfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMonikerFile-Klasse](../../mfc/reference/cmonikerfile-class.md)<br/>
[CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)
