---
title: 'Microsoft:: wrl-Namespace | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37d4d5391da4dfb6e25754eb1350224acb97e972
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881649"
---
# <a name="microsoftwrl-namespace"></a>Microsoft::WRL-Namespace
Definiert die grundlegenden Typen, aus denen die Windows Runtime C++ Template Library besteht.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Microsoft::WRL;  
```  
  
## <a name="members"></a>Member  
  
### <a name="typedefs"></a>Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt &#124; InhibitWeakReference>`|  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ActivationFactory-Klasse](../windows/activationfactory-class.md)|Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.|  
|[AsyncBase-Klasse](../windows/asyncbase-class.md)|Implementiert den asynchronen Zustandsautomat der Windows-Runtime.|  
|[ClassFactory-Klasse](../windows/classfactory-class.md)|Implementiert die grundlegende Funktion der `IClassFactory`-Schnittstelle.|  
|[ComPtr-Klasse](../windows/comptr-class.md)|Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. ComPtr verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf 0 geht.|  
|[DeferrableEventArgs-Klasse](../windows/deferrableeventargs-class.md)|Eine für die Ereignisargumenttypen für Verzögerungen verwendete Vorlagenklasse.|  
|[EventSource-Klasse](../windows/eventsource-class.md)|Stellt ein Ereignis dar. `EventSource`-Memberfunktionen fügen Ereignishandler hinzu, entfernen sie und rufen sie auf.|  
|[FtmBase-Klasse](../windows/ftmbase-class.md)|Stellt ein Freethread-Marshaller-Objekt dar.|  
|[Module-Klasse](../windows/module-class.md)|Stellt eine Auflistung von zugehörigen Objekten dar.|  
|[RuntimeClass-Klasse](../windows/runtimeclass-class.md)|Stellt eine instanziierte Klasse dar, die die angegebene Anzahl von Schnittstellen erbt, und gewährt Unterstützung für die angegebene Windows-Runtime, klassisches COM und schwache Verweise.|  
|[SimpleActivationFactory-Klasse](../windows/simpleactivationfactory-class.md)|Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.|  
|[SimpleClassFactory-Klasse](../windows/simpleclassfactory-class.md)|Stellt einen grundlegenden Mechanismus zum Erstellen einer Basisklasse bereit.|  
|[WeakRef-Klasse](../windows/weakref-class.md)|Stellt einen *schwachen Verweis* dar, der nur durch die Windows-Runtime und nicht durch die klassische COM verwendet werden kann. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|  
  
### <a name="structures"></a>Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)|Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.|  
|[CloakedIid-Struktur](../windows/cloakediid-structure.md)|Zeigt „RuntimeClass“-, „Implements“- und „ChainInterfaces“-Vorlagen an, dass auf die angegebene Schnittstelle in der IID-Liste nicht zugegriffen werden kann.|  
|[Implements-Struktur](../windows/implements-structure.md)|Implementiert „QueryInterface“ und „GetIid“ für die angegebene Schnittstelle.|  
|[MixIn-Struktur](../windows/mixin-structure.md)|Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.|  
|[RuntimeClassFlags-Struktur](../windows/runtimeclassflags-structure.md)|Enthält den Typ für eine Instanz von einem [RuntimeClass](../windows/runtimeclass-class.md).|  
  
### <a name="enumerations"></a>Enumerationen  
  
|name|Beschreibung|  
|----------|-----------------|  
|[AsyncResultType-Enumeration](../windows/asyncresulttype-enumeration.md)|Gibt den Typ des durch die Methode „GetResults()“ zurückgegebenen Ergebnisses zurück.|  
|[ModuleType-Enumeration](../windows/moduletype-enumeration.md)|Gibt an, ob ein Modul einen In-Process-Server oder einen Out-of-Process-Server unterstützen sollte. |  
|[RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md)|Gibt den Typ des [RuntimeClass](../windows/runtimeclass-class.md) -Instanz, die unterstützt wird.|  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AsWeak-Funktion](../windows/asweak-function.md)|Ruft einen schwachen Verweis zur angegebenen Instanz ab.|  
|[Rückruffunktion](../windows/callback-function-windows-runtime-cpp-template-library.md)|Erstellt ein Objekt, dessen Memberfunktion eine Rückrufmethode ist.|  
|[CreateActivationFactory-Funktion](../windows/createactivationfactory-function.md)|Erstellt eine Instanzen der angegebenen Klasse erstellende Factory, die durch die Windows-Runtime aktiviert werden kann.|  
|[CreateClassFactory-Funktion](../windows/createclassfactory-function.md)|Erstellt eine Factory, die Instanzen der angegebenen Klasse erstellt.|  
|[Make-Funktion](../windows/make-function.md)|Initialisiert die angegebene Windows-Runtime-Klasse.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)