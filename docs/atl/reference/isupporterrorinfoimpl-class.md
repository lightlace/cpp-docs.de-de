---
title: ISupportErrorInfoImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: b3227142d6ca31d0015411a3619281894eb5e419
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520048"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl-Klasse

Diese Klasse stellt eine Standardimplementierung von der [ISupportErrorInfo Schnittstelle](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) und kann verwendet werden, wenn nur eine einzelne Schnittstelle Fehler bei einem Objekt generiert.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

#### <a name="parameters"></a>Parameter

*piid*<br/>
Ein Zeiger auf eine Schnittstelle, unterstützt die IID [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo).

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Gibt an, ob die Schnittstelle durch identifiziert `riid` unterstützt die [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) Schnittstelle.|

## <a name="remarks"></a>Hinweise

Die [ISupportErrorInfo Schnittstelle](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) wird sichergestellt, dass die Fehlerinformationen an den Client zurückgegeben werden kann. Objekten, `IErrorInfo` müssen implementieren `ISupportErrorInfo`.

Klasse `ISupportErrorInfoImpl` stellt eine Standardimplementierung von `ISupportErrorInfo` und kann verwendet werden, wenn nur eine einzelne Schnittstelle Fehler bei einem Objekt generiert. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

Gibt an, ob die Schnittstelle durch identifiziert `riid` unterstützt die [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) Schnittstelle.

```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ISupportErrorInfo:: InterfaceSupportsErrorInfo](/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) in das Windows SDK.

##  <a name="getsize"></a>  IThreadPoolConfig::GetSize

Rufen Sie diese Methode, um die Anzahl der Threads im Pool verfügbar machen.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>Parameter

*pnNumThreads*<br/>
[out] Die Adresse der Variablen, die bei Erfolg die Anzahl der Threads im Pool empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]

##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout

Rufen Sie diese Methode rufen Sie die maximale Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>Parameter

*pdwMaxWait*<br/>
[out] Die Adresse der Variablen, die bei Erfolg die maximale Zeit in Millisekunden empfängt, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="example"></a>Beispiel

Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).

##  <a name="setsize"></a>  IThreadPoolConfig::SetSize

Rufen Sie diese Methode, um die Anzahl der Threads im Pool festlegen.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>Parameter

*nNumThreads*<br/>
Die angeforderte Anzahl von Threads im Pool.

Wenn *nNumThreads* ist negativ, der Absolute Wert multipliziert die Anzahl der Prozessoren auf dem Computer, der die Gesamtzahl der Threads abzurufen.

Wenn *nNumThreads* ist 0 (null), ATLS_DEFAULT_THREADSPERPROC multipliziert die Anzahl der Prozessoren auf dem Computer, der die Gesamtzahl der Threads abzurufen.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="example"></a>Beispiel

Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).

##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout

Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>Parameter

*dwMaxWait*<br/>
Die angeforderte maximale Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="example"></a>Beispiel

Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
