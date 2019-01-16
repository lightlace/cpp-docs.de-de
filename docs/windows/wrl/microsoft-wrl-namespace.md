---
title: Microsoft::WRL-Namespace
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL
- module/Microsoft::WRL
- async/Microsoft::WRL
- internal/Microsoft::WRL
- event/Microsoft::WRL
- ftm/Microsoft::WRL
- client/Microsoft::WRL
- corewrappers/Microsoft::WRL
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
ms.openlocfilehash: d402f2a1292088b52ce921bbc0007ab96554189e
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336821"
---
# <a name="microsoftwrl-namespace"></a>Microsoft::WRL-Namespace

Definiert die grundlegenden Typen, aus denen die Windows Runtime C++ Template Library besteht.

## <a name="syntax"></a>Syntax

```cpp
namespace Microsoft::WRL;
```

## <a name="members"></a>Member

### <a name="typedefs"></a>Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt | InhibitWeakReference>`|

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[ActivationFactory-Klasse](activationfactory-class.md)|Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.|
|[AsyncBase-Klasse](asyncbase-class.md)|Implementiert den asynchronen Zustandsautomat der Windows-Runtime.|
|[ClassFactory-Klasse](classfactory-class.md)|Implementiert die grundlegende Funktion der `IClassFactory`-Schnittstelle.|
|[ComPtr-Klasse](comptr-class.md)|Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. ComPtr verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf 0 geht.|
|[DeferrableEventArgs-Klasse](deferrableeventargs-class.md)|Eine für die Ereignisargumenttypen für Verzögerungen verwendete Vorlagenklasse.|
|[EventSource-Klasse](eventsource-class.md)|Stellt ein Ereignis dar. `EventSource`-Memberfunktionen fügen Ereignishandler hinzu, entfernen sie und rufen sie auf.|
|[FtmBase-Klasse](ftmbase-class.md)|Stellt ein Freethread-Marshaller-Objekt dar.|
|[Module-Klasse](module-class.md)|Stellt eine Auflistung von zugehörigen Objekten dar.|
|[RuntimeClass-Klasse](runtimeclass-class.md)|Stellt eine instanziierte Klasse dar, die die angegebene Anzahl von Schnittstellen erbt, und gewährt Unterstützung für die angegebene Windows-Runtime, klassisches COM und schwache Verweise.|
|[SimpleActivationFactory-Klasse](simpleactivationfactory-class.md)|Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.|
|[SimpleClassFactory-Klasse](simpleclassfactory-class.md)|Stellt einen grundlegenden Mechanismus zum Erstellen einer Basisklasse bereit.|
|[WeakRef-Klasse](weakref-class.md)|Stellt einen *schwachen Verweis* dar, der nur durch die Windows-Runtime und nicht durch die klassische COM verwendet werden kann. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|

### <a name="structures"></a>Strukturen

|Name|Beschreibung|
|----------|-----------------|
|[ChainInterfaces-Struktur](chaininterfaces-structure.md)|Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.|
|[CloakedIid-Struktur](cloakediid-structure.md)|Gibt an, um die `RuntimeClass`, `Implements` und `ChainInterfaces` Vorlagen, dass die angegebene Schnittstelle nicht zugegriffen werden kann, in der IID-Liste ist.|
|[Implements-Struktur](implements-structure.md)|Implementiert `QueryInterface` und `GetIid` für die angegebene Schnittstelle.|
|[MixIn-Struktur](mixin-structure.md)|Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.|
|[RuntimeClassFlags-Struktur](runtimeclassflags-structure.md)|Enthält den Typ für eine Instanz von einem [RuntimeClass](runtimeclass-class.md).|

### <a name="enumerations"></a>Enumerationen

|name|Beschreibung|
|----------|-----------------|
|[AsyncResultType-Enumeration](asyncresulttype-enumeration.md)|Gibt den Typ der zurückgegebenen Ergebnisse der `GetResults()` Methode.|
|[ModuleType-Enumeration](moduletype-enumeration.md)|Gibt an, ob ein Modul einen In-Process-Server oder einen Out-of-Process-Server unterstützen sollte. |
|[RuntimeClassType-Enumeration](runtimeclasstype-enumeration.md)|Gibt den Typ der [RuntimeClass](runtimeclass-class.md) -Instanz, die unterstützt wird.|

### <a name="functions"></a>Funktionen

|Name|Beschreibung|
|----------|-----------------|
|[AsWeak-Funktion](asweak-function.md)|Ruft einen schwachen Verweis zur angegebenen Instanz ab.|
|[Rückruffunktion (WRL)](callback-function-wrl.md)|Erstellt ein Objekt, dessen Memberfunktion eine Rückrufmethode ist.|
|[CreateActivationFactory-Funktion](createactivationfactory-function.md)|Erstellt eine Instanzen der angegebenen Klasse erstellende Factory, die durch die Windows-Runtime aktiviert werden kann.|
|[CreateClassFactory-Funktion](createclassfactory-function.md)|Erstellt eine Factory, die Instanzen der angegebenen Klasse erstellt.|
|[Make-Funktion](make-function.md)|Initialisiert die angegebene Windows-Runtime-Klasse.|

## <a name="requirements"></a>Anforderungen

**Header:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers-Namespace](microsoft-wrl-wrappers-namespace.md)