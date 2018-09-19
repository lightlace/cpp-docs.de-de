---
title: IServiceProviderImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef8c497a681ae1b54ec833a048cddba29a72be7f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067586"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl-Klasse

Diese Klasse stellt eine Standardimplementierung von der `IServiceProvider` Schnittstelle.

## <a name="syntax"></a>Syntax

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IServiceProviderImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IServiceProviderImpl:: QueryService](#queryservice)|Erstellt oder auf den angegebenen Dienst zugreift, und gibt einen Schnittstellenzeiger zurück, auf die angegebene Schnittstelle für den Dienst.|

## <a name="remarks"></a>Hinweise

Die `IServiceProvider` Schnittstelle sucht einen angegebenen Dienst mithilfe der GUID und gibt Sie den Schnittstellenzeiger für die angeforderte Schnittstelle zurück, für den Dienst. Klasse `IServiceProviderImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit.

`IServiceProviderImpl` Gibt an, eine Methode: [QueryService](#queryservice), die erstellt wird, oder den angegebenen Dienst zugreift und gibt einen Schnittstellenzeiger zurück, auf die angegebene Schnittstelle für den Dienst.

`IServiceProviderImpl` verwendet eine dienstzuordnung, beginnend mit [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) und endend mit [END_SERVICE_MAP](service-map-macros.md#end_service_map).

Die dienstzuordnung enthält zwei Einträge: [SERVICE_ENTRY](service-map-macros.md#service_entry), die eine vom Objekt unterstützte angegebenen Dienst-Id (SID) angibt und [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain), welche Aufrufe `QueryService` , eine Verkettung mit einer anderen -Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="queryservice"></a>  IServiceProviderImpl:: QueryService

Erstellt oder auf den angegebenen Dienst zugreift, und gibt einen Schnittstellenzeiger zurück, auf die angegebene Schnittstelle für den Dienst.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parameter

*guidService*<br/>
[in] Zeiger auf eine Dienst-ID (SID).

*riid*<br/>
[in] Der Bezeichner der Schnittstelle, die der Aufrufer ist, um Zugriff zu erhalten.

*ppvObj*<br/>
[out] Indirekter Zeiger auf die angeforderte Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Der zurückgegebene HRESULT-Wert ist eine der folgenden:

|Rückgabewert|Bedeutung|
|------------------|-------------|
|S_OK|Der Dienst wurde erfolgreich erstellt oder abgerufen.|
|E_INVALIDARG|Mindestens eines der Argumente ist ungültig.|
|E_OUTOFMEMORY|Speicher ist nicht ausreichend, um den Dienst zu erstellen.|
|E_UNEXPECTED|Es ist ein unbekannter Fehler aufgetreten.|
|E_NOINTERFACE|Die angeforderte Schnittstelle ist nicht Teil dieses Dienstes oder des Diensts ist unbekannt.|

### <a name="remarks"></a>Hinweise

`QueryService` Gibt einen indirekten Zeiger auf die angeforderte Schnittstelle in den angegebenen Dienst zurück. Der Aufrufer ist verantwortlich für das this-Zeiger freigeben, wenn es nicht mehr benötigt wird.

Beim Aufruf `QueryService`, übergeben Sie sowohl eine Dienst-ID (*GuidService*) und einen Schnittstellenbezeichner (*Riid*). Die *GuidService* gibt Sie den Dienst, der Zugriff und die *Riid* identifiziert eine Schnittstelle, die Teil des Diensts ist. Im Gegenzug erhalten Sie einen indirekten Zeiger auf die Schnittstelle an.

Das Objekt, das die Schnittstelle implementiert, kann auch Schnittstellen implementieren, die von anderen Diensten gehören. Nehmen wir einmal die folgende Situation:

- Einige dieser Schnittstellen kann optional sein. Nicht alle Schnittstellen, die in der dienstbeschreibung definiert sind notwendigerweise vorhanden, für jede Implementierung des Diensts oder für jedes zurückgegebene Objekt.

- Im Gegensatz zum Aufrufen von `QueryInterface`, übergeben einen anderen Dienstbezeichner bedeutet nicht unbedingt, dass ein anderes Component Object Model (COM)-Objekt zurückgegeben wird.

- Das zurückgegebene Objekt möglicherweise weitere Schnittstellen, die nicht Teil der Definition des Diensts sind.

Zwei verschiedene Dienste, z. B. SID_SMyService und SID_SYourService, können sowohl die Verwendung der gleichen Schnittstelle angeben, auch wenn die Implementierung der Schnittstelle keine Gemeinsamkeit zwischen den beiden Diensten verfügen. Dies funktioniert, weil ein Aufruf von `QueryService` (SID_SMyService, IID_IDispatch) kann ein anderes Objekt als zurückgeben `QueryService` (SID_SYourService, IID_IDispatch). Identität des Objekts wird nicht angenommen werden, wenn Sie einen anderen Dienstbezeichner angeben.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
