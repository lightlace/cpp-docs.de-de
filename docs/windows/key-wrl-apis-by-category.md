---
title: Schlüssel-WRL-APIs nach Kategorie | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9936c85443f893111b3c2b9de17ca80e6fb382b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="key-wrl-apis-by-category"></a>Schlüssel-WRL-APIs nach Kategorie
Die folgenden Tabellen sind die primären Windows Runtime C++ Template Library-Klassen, Strukturen, Funktionen und Makros. Konstrukte im Hilfsprogramm-Namespaces und-Klassen werden ausgelassen. Diese Listen erweitern die API-Dokumentation nach Namespace sortiert ist.  
  
### <a name="classes"></a>Klassen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ActivationFactory-Klasse](../windows/activationfactory-class.md)|Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.|  
|[AsyncBase-Klasse](../windows/asyncbase-class.md)|Implementiert den asynchronen Zustandsautomat der Windows-Runtime.|  
|[ClassFactory-Klasse](../windows/classfactory-class.md)|Implementiert die grundlegende Funktion der `IClassFactory`-Schnittstelle.|  
|[ComPtr-Klasse](../windows/comptr-class.md)|Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. ComPtr verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf 0 geht.|  
|[Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)](../windows/event-class-windows-runtime-cpp-template-library.md)|Stellt ein Ereignis dar.|  
|[EventSource-Klasse](../windows/eventsource-class.md)|Stellt ein Ereignis dar. `EventSource`-Memberfunktionen fügen Ereignishandler hinzu, entfernen sie und rufen sie auf.|  
|[FtmBase-Klasse](../windows/ftmbase-class.md)|Stellt ein Freethread-Marshaller-Objekt dar.|  
|[HandleT-Klasse](../windows/handlet-class.md)|Stellt ein Handle für ein Objekt dar.|  
|[HString-Klasse](../windows/hstring-class.md)|Bietet Unterstützung für die Bearbeitung von HSTRING-Handles.|  
|[HStringReference-Klasse](../windows/hstringreference-class.md)|Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.|  
|[Module-Klasse](../windows/module-class.md)|Stellt eine Auflistung von zugehörigen Objekten dar.|  
|[Module::GenericReleaseNotifier-Klasse](../windows/module-genericreleasenotifier-class.md)|Ruft einen Ereignishandler auf, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird auf ein Lambda, Funktionselement oder Zeiger-auf-Funktion von angegeben.|  
|[Module::MethodReleaseNotifier-Klasse](../windows/module-methodreleasenotifier-class.md)|Ruft einen Ereignishandler auf, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird von einem Objekt und seinem Member Zeiger-zu-Methode angegeben.|  
|[Module::ReleaseNotifier-Klasse](../windows/module-releasenotifier-class.md)|Ruft einen Ereignishandler auf, wenn das letzte Objekt in einem Modul freigegeben wird.|  
|[RoInitializeWrapper-Klasse](../windows/roinitializewrapper-class.md)|Initialisiert die Windows-Runtime.|  
|[RuntimeClass-Klasse](../windows/runtimeclass-class.md)|Stellt eine instanziierte Klasse dar, die die angegebene Anzahl von Schnittstellen erbt, und gewährt Unterstützung für die angegebene Windows-Runtime, klassisches COM und schwache Verweise.|  
|[SimpleActivationFactory-Klasse](../windows/simpleactivationfactory-class.md)|Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.|  
|[SimpleClassFactory-Klasse](../windows/simpleclassfactory-class.md)|Stellt einen grundlegenden Mechanismus zum Erstellen einer Basisklasse bereit.|  
|[WeakRef-Klasse](../windows/weakref-class.md)|Stellt einen *schwachen Verweis* dar, der nur durch die Windows-Runtime und nicht durch die klassische COM verwendet werden kann. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|  
  
### <a name="structures"></a>Strukturen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)|Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.|  
|[CloakedIid-Struktur](../windows/cloakediid-structure.md)|Gibt an, um die `RuntimeClass`, `Implements` und `ChainInterfaces` Vorlagen, dass die angegebene Schnittstelle nicht zugegriffen werden kann, in der IID-Liste ist.|  
|[Implements-Struktur](../windows/implements-structure.md)|Implementiert `QueryInterface` und `GetIid` für die angegebene Schnittstelle.|  
|[MixIn-Struktur](../windows/mixin-structure.md)|Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.|  
  
### <a name="functions"></a>Funktionen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ActivateInstance-Funktion](../windows/activateinstance-function.md)|Registriert, und ruft eine Instanz eines angegebenen Typs, der definiert, die in einer angegebenen Klasse-ID ab|  
|[AsWeak-Funktion](../windows/asweak-function.md)|Ruft einen schwachen Verweis zur angegebenen Instanz ab.|  
|[Rückruffunktion](../windows/callback-function-windows-runtime-cpp-template-library.md)|Erstellt ein Objekt, dessen Memberfunktion eine Rückrufmethode ist.|  
|[CreateActivationFactory-Funktion](../windows/createactivationfactory-function.md)|Erstellt eine Instanzen der angegebenen Klasse erstellende Factory, die durch die Windows-Runtime aktiviert werden kann.|  
|[CreateClassFactory-Funktion](../windows/createclassfactory-function.md)|Erstellt eine Factory, die Instanzen der angegebenen Klasse erstellt.|  
|[GetActivationFactory-Funktion](../windows/getactivationfactory-function.md)|Ruft eine aktivierungsfactory für den durch den Vorlagenparameter angegebenen Typ ab.|  
|[Make-Funktion](../windows/make-function.md)|Initialisiert die angegebene Windows-Runtime-Klasse.|  
  
### <a name="macros"></a>Makros  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ActivatableClass-Makros](../windows/activatableclass-macros.md)|Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können.|  
|[InspectableClass-Makro](../windows/inspectableclass-macro.md)|Legt den Ablaufklassennamen und die Vertrauensebene fest.|  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Vorlagenbibliothek für Windows-Runtime (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)