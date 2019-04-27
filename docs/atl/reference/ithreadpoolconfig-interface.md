---
title: IThreadPoolConfig-Schnittstelle
ms.date: 11/04/2016
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
ms.openlocfilehash: b3757f0e90479962273a8295e055c91fb02260f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198186"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig-Schnittstelle

Diese Schnittstelle bietet Methoden zum Konfigurieren eines Threadpools.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[GetSize](#getsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool verfügbar machen.|
|[GetTimeout](#gettimeout)|Rufen Sie diese Methode rufen Sie die maximale Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.|
|[SetSize](#setsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool festlegen.|
|[SetTimeout](#settimeout)|Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle wird implementiert von [CThreadPool](../../atl/reference/cthreadpool-class.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlutil.h

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

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

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

[Klassen](../../atl/reference/atl-classes.md)<br/>
[CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)
