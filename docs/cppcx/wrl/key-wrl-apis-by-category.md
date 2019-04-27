---
title: Schlüssel-WRL-APIs nach Kategorie
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: f3065323c567c944dab12fc1ebbcbd6bb57127e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223145"
---
# <a name="key-wrl-apis-by-category"></a>Schlüssel-WRL-APIs nach Kategorie

Die folgenden Tabellen enthalten die primären Windows Runtime C++ Template Library-Klassen, Strukturen, Funktionen und Makros. Konstrukte im Hilfsprogramm-Namespaces und Klassen werden ausgelassen. Diese Listen erweitern die API-Dokumentation, die vom Namespace angeordnet ist.

## <a name="classes"></a>Klassen

|Titel|Beschreibung|
|-----------|-----------------|
|[ActivationFactory-Klasse](activationfactory-class.md)|Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.|
|[AsyncBase-Klasse](asyncbase-class.md)|Implementiert den asynchronen Zustandsautomat der Windows-Runtime.|
|[ClassFactory-Klasse](classfactory-class.md)|Implementiert die grundlegende Funktion der `IClassFactory`-Schnittstelle.|
|[ComPtr-Klasse](comptr-class.md)|Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. ComPtr verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf 0 geht.|
|[Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)](event-class-wrl.md)|Stellt ein Ereignis dar.|
|[EventSource-Klasse](eventsource-class.md)|Stellt ein Ereignis dar. `EventSource`-Memberfunktionen fügen Ereignishandler hinzu, entfernen sie und rufen sie auf.|
|[FtmBase-Klasse](ftmbase-class.md)|Stellt ein Freethread-Marshaller-Objekt dar.|
|[HandleT-Klasse](handlet-class.md)|Stellt ein Handle für ein Objekt dar.|
|[HString-Klasse](hstring-class.md)|Bietet Unterstützung für die Bearbeitung von HSTRING-Handles.|
|[HStringReference-Klasse](hstringreference-class.md)|Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.|
|[Module-Klasse](module-class.md)|Stellt eine Auflistung von zugehörigen Objekten dar.|
|[Module::GenericReleaseNotifier-Klasse](module-genericreleasenotifier-class.md)|Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler ist durch ein Lambda, Funktionselement oder Zeiger auf Funktion angegeben.|
|[Module::MethodReleaseNotifier-Klasse](module-methodreleasenotifier-class.md)|Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler wird von einem Objekt und seine Member Zeiger-zu-Methode angegeben.|
|[Module::ReleaseNotifier-Klasse](module-releasenotifier-class.md)|Ruft einen Ereignishandler an, wenn das letzte Objekt in einem Modul veröffentlicht wird.|
|[RoInitializeWrapper-Klasse](roinitializewrapper-class.md)|Initialisiert die Windows-Runtime.|
|[RuntimeClass-Klasse](runtimeclass-class.md)|Stellt eine instanziierte Klasse dar, die die angegebene Anzahl von Schnittstellen erbt, und gewährt Unterstützung für die angegebene Windows-Runtime, klassisches COM und schwache Verweise.|
|[SimpleActivationFactory-Klasse](simpleactivationfactory-class.md)|Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.|
|[SimpleClassFactory-Klasse](simpleclassfactory-class.md)|Stellt einen grundlegenden Mechanismus zum Erstellen einer Basisklasse bereit.|
|[WeakRef-Klasse](weakref-class.md)|Stellt einen *schwachen Verweis* dar, der nur durch die Windows-Runtime und nicht durch die klassische COM verwendet werden kann. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|

## <a name="structures"></a>Strukturen

|Titel|Beschreibung|
|-----------|-----------------|
|[ChainInterfaces-Struktur](chaininterfaces-structure.md)|Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.|
|[CloakedIid-Struktur](cloakediid-structure.md)|Gibt an, um die `RuntimeClass`, `Implements` und `ChainInterfaces` Vorlagen, dass die angegebene Schnittstelle nicht zugegriffen werden kann, in der IID-Liste ist.|
|[Implements-Struktur](implements-structure.md)|Implementiert `QueryInterface` und `GetIid` für die angegebene Schnittstelle.|
|[MixIn-Struktur](mixin-structure.md)|Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.|

## <a name="functions"></a>Funktionen

|Titel|Beschreibung|
|-----------|-----------------|
|[ActivateInstance-Funktion](activateinstance-function.md)|Registriert, und ruft eine Instanz eines angegebenen Typs, der definiert, die in einer angegebenen Klasse-ID ab|
|[AsWeak-Funktion](asweak-function.md)|Ruft einen schwachen Verweis zur angegebenen Instanz ab.|
|[Callback-Funktion](callback-function-wrl.md)|Erstellt ein Objekt, dessen Memberfunktion eine Rückrufmethode ist.|
|[CreateActivationFactory-Funktion](createactivationfactory-function.md)|Erstellt eine Instanzen der angegebenen Klasse erstellende Factory, die durch die Windows-Runtime aktiviert werden kann.|
|[CreateClassFactory-Funktion](createclassfactory-function.md)|Erstellt eine Factory, die Instanzen der angegebenen Klasse erstellt.|
|[GetActivationFactory-Funktion](getactivationfactory-function.md)|Ruft eine aktivierungsfactory für den durch die Template-Parameter angegebenen Typ ab.|
|[Make-Funktion](make-function.md)|Initialisiert die angegebene Windows-Runtime-Klasse.|

## <a name="macros"></a>Makros

|Titel|Beschreibung|
|-----------|-----------------|
|[ActivatableClass-Makros](activatableclass-macros.md)|Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können.|
|[InspectableClass-Makro](inspectableclass-macro.md)|Legt den Ablaufklassennamen und die Vertrauensebene fest.|

## <a name="see-also"></a>Siehe auch

[C++-Vorlagenbibliothek für Windows-Runtime (WRL)](windows-runtime-cpp-template-library-wrl.md)