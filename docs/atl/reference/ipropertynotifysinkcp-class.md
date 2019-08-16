---
title: IPropertyNotifySinkCP-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: 9838a48b078cbc59a5ae86669ad9f26792d9816e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495629"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP-Klasse

Diese Klasse macht die [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) -Schnittstelle als ausgehende Schnittstelle für ein Verbindungs fähiges Objekt verfügbar.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IPropertyNotifySinkCP`abgeleitete Klasse.

*CDV*<br/>
Eine Klasse, die die Verbindungen zwischen einem Verbindungspunkt und seinen senken verwaltet. Der Standardwert ist [ccomdynamicunkarray](../../atl/reference/ccomdynamicunkarray-class.md), der unbegrenzte Verbindungen zulässt. Sie können auch [ccomunkarray](../../atl/reference/ccomunkarray-class.md)verwenden, das eine festgelegte Anzahl von Verbindungen angibt.

## <a name="remarks"></a>Hinweise

`IPropertyNotifySinkCP`erbt alle Methoden über die Basisklasse " [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)".

Die [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) -Schnittstelle ermöglicht einem Sink-Objekt das Empfangen von Benachrichtigungen über Eigenschafts Änderungen. Die `IPropertyNotifySinkCP` Klasse macht diese Schnittstelle als ausgehende Schnittstelle für ein Verbindungs fähiges Objekt verfügbar. Der Client muss die `IPropertyNotifySink` Methoden für die Senke implementieren.

Leiten Sie die Klasse `IPropertyNotifySinkCP` von ab, wenn Sie einen Verbindungspunkt erstellen möchten, `IPropertyNotifySink` der die Schnittstelle darstellt.

Weitere Informationen zum Verwenden von Verbindungs Punkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

## <a name="see-also"></a>Siehe auch

[IConnectionPointImpl-Klasse](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[IConnectionPointContainerImpl-Klasse](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
