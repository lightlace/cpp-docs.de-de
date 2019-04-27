---
title: Marshalling globale Funktionen
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: cac6e316ad6b5d3f49c171c940d9129060744aee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274693"
---
# <a name="marshaling-global-functions"></a>Marshalling globale Funktionen

Diese Funktionen bieten Unterstützung für das Marshallen und konvertieren Marshallen von Daten in den Schnittstellenzeiger auf.

> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Gibt die marschalldaten und `IStream` Zeiger.|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Erstellt ein neues Streamobjekt und marshallt den angegebenen Schnittstellenzeiger auf.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|Konvertiert die Marshallingdaten des Streams in einen Schnittstellenzeiger auf.|

## <a name="requirements"></a>Anforderungen:

**Header:** atlbase.h

##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream

Gibt die Marschalldaten im Stream und anschließend den Streamzeiger frei.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
[in] Ein Zeiger auf die `IStream` Schnittstelle für den Stream, der für das Marshalling verwendet.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [AtlMarshalPtrInProc](#atlmarshalptrinproc).

##  <a name="atlmarshalptrinproc"></a>  AtlMarshalPtrInProc

Erstellt ein neues Streamobjekt, schreibt die CLSID des Proxys in den Stream und marshallt den angegebenen Schnittstellenzeiger durch Schreiben der für die Initialisierung des Proxys erforderlichen Daten in den Stream.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
[in] Ein Zeiger auf die Schnittstelle, die gemarshallt werden.

*iid*<br/>
[in] Die GUID der Schnittstelle, die gemarshallt werden.

*ppStream*<br/>
[out] Ein Zeiger auf die `IStream` Schnittstelle für das neue Streamobjekt, das für das Marshalling verwendet.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die MSHLFLAGS_TABLESTRONG-Flag wird festgelegt, sodass der Zeiger in mehrere Datenströme gemarshallt werden kann. Der Zeiger kann auch Marshalling mehrmals sein.

Wenn Marshalling ein Fehler auftritt, wird der streamzeiger freigegeben.

`AtlMarshalPtrInProc` kann nur für einen Zeiger auf ein in-Process-Objekt verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

##  <a name="atlunmarshalptr"></a>  AtlUnmarshalPtr

Konvertiert die Marshallingdaten des Streams in einen Schnittstellenzeiger, der vom Client verwendet werden kann.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
[in] Ein Zeiger auf den Stream, werden Marshalling.

*iid*<br/>
[in] Die GUID der Schnittstelle werden Marshalling.

*ppUnk*<br/>
[out] Ein Zeiger auf die Marshalling-Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [AtlMarshalPtrInProc](#atlmarshalptrinproc).

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)
