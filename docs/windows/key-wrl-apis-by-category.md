---
title: "Schl&#252;ssel-WRL-APIs nach Kategorie"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Schl&#252;ssel-WRL-APIs nach Kategorie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Tabellen sind die primären [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] Klassen, Strukturen, Funktionen und Makros. Konstrukte in Helper-Namespaces und Klassen werden ausgelassen. Diese Listen erweitern die API-Dokumentation, die vom Namespace angeordnet ist.  
  
### <a name="classes"></a>Klassen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ActivationFactory-Klasse](../windows/activationfactory-class.md)|Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.|  
|[AsyncBase-Klasse](../windows/asyncbase-class.md)|Implementiert den asynchronen Zustandsautomat der Windows-Runtime.|  
|[ClassFactory-Klasse](../windows/classfactory-class.md)|Implementiert die grundlegende Funktion der `IClassFactory`-Schnittstelle.|  
|[ComPtr-Klasse](../windows/comptr-class.md)|Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. ComPtr verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf 0 geht.|  
|[Event-Klasse (Windows Runtime C++-Vorlagenbibliothek)](../windows/event-class-windows-runtime-cpp-template-library.md)|Stellt ein Ereignis dar.|  
|[EventSource-Klasse](../windows/eventsource-class.md)|Stellt ein Ereignis dar. `EventSource`-Memberfunktionen fügen Ereignishandler hinzu, entfernen sie und rufen sie auf.|  
|[FtmBase-Klasse](../windows/ftmbase-class.md)|Stellt ein Freethread-Marshaller-Objekt dar.|  
|[HandleT-Klasse](../windows/handlet-class.md)|Stellt ein Handle für ein Objekt dar.|  
|[HString-Klasse](../windows/hstring-class.md)|Bietet Unterstützung für die Bearbeitung von HSTRING-Handles.|  
|[HStringReference-Klasse](../windows/hstringreference-class.md)|Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.|  
|[Module-Klasse](../windows/module-class.md)|Stellt eine Auflistung von zugehörigen Objekten dar.|  
|[Genericreleasenotifier-Klasse](../windows/module-genericreleasenotifier-class.md)|Wird einen Ereignishandler aufgerufen, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird durch ein Lambda, ein Funktionselement oder Zeiger auf Funktion angegeben.|  
|[Methodreleasenotifier-Klasse](../windows/module-methodreleasenotifier-class.md)|Wird einen Ereignishandler aufgerufen, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird durch ein Objekt und seine Member Zeiger-zu-Methode angegeben.|  
|[Releasenotifier-Klasse](../windows/module-releasenotifier-class.md)|Wird einen Ereignishandler aufgerufen, wenn das letzte Objekt in einem Modul freigegeben wird.|  
|[RoInitializeWrapper-Klasse](../windows/roinitializewrapper-class.md)|Initialisiert das [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[RuntimeClass-Klasse](../windows/runtimeclass-class.md)|Stellt eine instanziierte Klasse dar, die die angegebene Anzahl von Schnittstellen erbt, und gewährt Unterstützung für die angegebene Windows-Runtime, klassisches COM und schwache Verweise.|  
|[SimpleActivationFactory-Klasse](../windows/simpleactivationfactory-class.md)|Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.|  
|[SimpleClassFactory-Klasse](../windows/simpleclassfactory-class.md)|Stellt einen grundlegenden Mechanismus zum Erstellen einer Basisklasse bereit.|  
|[WeakRef-Klasse](../windows/weakref-class.md)|Stellt eine *schwachen Verweis* die verwendet werden kann, indem nur die Windows-Runtime nicht klassischen COM Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|  
  
### <a name="structures"></a>Strukturen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)|Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.|  
|[CloakedIid-Struktur](../windows/cloakediid-structure.md)|Gibt an, um die `RuntimeClass`, `Implements` und `ChainInterfaces` Vorlagen, dass die angegebene Schnittstelle nicht in der Liste IID zugegriffen werden kann.|  
|[Implements-Struktur](../windows/implements-structure.md)|Implementiert `QueryInterface` und `GetIid` für die angegebene Schnittstelle.|  
|[MixIn-Struktur](../windows/mixin-structure.md)|Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.|  
  
### <a name="functions"></a>Funktionen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ActivateInstance-Funktion](../windows/activateinstance-function.md)|Registriert und ruft eine Instanz eines angegebenen Typs in eine ID für die angegebene Klasse definiert|  
|[AsWeak-Funktion](../windows/asweak-function.md)|Ruft einen schwachen Verweis zur angegebenen Instanz ab.|  
|[Callback-Funktion](../windows/callback-function-windows-runtime-cpp-template-library.md)|Erstellt ein Objekt, dessen Memberfunktion eine Rückrufmethode ist.|  
|[CreateActivationFactory-Funktion](../windows/createactivationfactory-function.md)|Erstellt eine Instanzen der angegebenen Klasse erstellende Factory, die durch die Windows-Runtime aktiviert werden kann.|  
|[CreateClassFactory-Funktion](../windows/createclassfactory-function.md)|Erstellt eine Factory, die Instanzen der angegebenen Klasse erstellt.|  
|[GetActivationFactory-Funktion](../windows/getactivationfactory-function.md)|Ruft eine aktivierungsfactory für die vom Vorlagenparameter angegebenen Typ ab.|  
|[Make-Funktion](../windows/make-function.md)|Initialisiert die angegebene [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]-Klasse.|  
  
### <a name="macros"></a>Makros  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[ActivatableClass-Makros](../windows/activatableclass-macros.md)|Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können.|  
|[InspectableClass-Makro](../windows/inspectableclass-macro.md)|Legt den Ablaufklassennamen und die Vertrauensebene fest.|  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Runtime C++-Vorlagenbibliothek (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)