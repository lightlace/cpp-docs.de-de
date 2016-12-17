---
title: "Microsoft::WRL::Details-Namespace"
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
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Microsoft::WRL::Details-Namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRef-Klasse](../windows/comptrref-class.md)|Stellt einen Verweis auf ein Objekt vom Typ ComPtr \< T>.|  
|[ComPtrRefBase-Klasse](../windows/comptrrefbase-class.md)|Stellt die Basisklasse für die [ComPtrRef](../windows/comptrref-class.md) Klasse.|  
|[DontUseNewUseMake-Klasse](../windows/dontusenewusemake-class.md)|Verhindert die Verwendung von Operator `new` in `RuntimeClass`. Folglich müssen Sie verwenden die [Make-Funktion](../windows/make-function.md) stattdessen.|  
|[EventTargetArray-Klasse](../windows/eventtargetarray-class.md)|Stellt ein Array der Ereignishandler.|  
|[MakeAllocator-Klasse](../windows/makeallocator-class.md)|Belegt Speicher für eine aktivierbare Klasse, mit oder ohne Unterstützung von schwachen Verweis.|  
|[ModuleBase-Klasse](../windows/modulebase-class.md)|Stellt die Basisklasse für die [Modul](../windows/module-class.md) Klassen.|  
|[RemoveIUnknown-Klasse](../windows/removeiunknown-class.md)|Wandelt einen Typ, der entspricht einer `IUnknown`-Basis Typ hat jedoch nicht virtuell `QueryInterface`, `AddRef`, und `Release` Methoden.|  
|[WeakReference-Klasse](../windows/weakreference-class1.md)|Stellt eine *schwachen Verweis* die verwendet werden kann, mit dem Windows-Runtime oder ein klassisches COM verwenden. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|  
  
### <a name="structures"></a>Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ArgTraits-Struktur](../windows/argtraits-structure.md)|Deklariert einen angegebenen Delegaten, Schnittstelle und eine anonyme-Memberfunktion, die eine angegebene Anzahl von Parametern.|  
|[ArgTraitsHelper-Struktur](../windows/argtraitshelper-structure.md)|Unterstützt definiert allgemeine Merkmale Argumente des Delegaten.|  
|[BoolStruct-Struktur](../windows/boolstruct-structure.md)|Definiert, ob ein ComPtr die Lebensdauer von einer Schnittstelle verwaltet. BoolStruct wird intern von verwendet, die [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) Operator.|  
|[CreatorMap-Struktur](../windows/creatormap-structure.md)|Enthält Informationen zum Initialisieren, registrieren und Aufheben der Registrierung Objekten.|  
|[DerefHelper-Struktur](../windows/derefhelper-structure.md)|Einen dereferenzierten Zeiger zum Darstellen der `T*` Template-Parameter.|  
|[EnableIf-Struktur](../windows/enableif-structure.md)|Definiert einen Datenmember des Typs mit dem zweiten Vorlagenparameter angegeben wird, wenn der erste Vorlagenparameter ergibt `true`.|  
|[FactoryCache-Struktur](../windows/factorycache-structure.md)|Enthält den Speicherort einer Klassenfactory und einem Wert, der eine registrierte identifiziert [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] oder COM-Klassenobjekt.|  
|[ImplementsBase-Struktur](../windows/implementsbase-structure.md)|Zum Überprüfen der Vorlage Parametertypen [Implements-Struktur](../windows/implements-structure.md).|  
|[ImplementsHelper-Struktur](../windows/implementshelper-structure.md)|Implementiert die [implementiert](../windows/implements-structure.md) Struktur.|  
|[InterfaceList-Struktur](../windows/interfacelist-structure.md)|Verwendet, um eine rekursive Liste von Schnittstellen zu erstellen.|  
|[InterfaceListHelper-Struktur](../windows/interfacelisthelper-structure.md)|Erstellt ein `InterfaceList` Typ durch Anwenden der angegebenen Parameter Vorlagenargumente rekursiv.|  
|[InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)|Implementiert Allgemeine Merkmale einer Schnittstelle.|  
|[InvokeHelper-Struktur](../windows/invokehelper-structure.md)|Stellt eine Implementierung für die Invoke()-Methode, die basierend auf der angegebenen Anzahl und Typ der Argumente.|  
|[IsBaseOfStrict-Struktur](../windows/isbaseofstrict-structure.md)|Testet, ob ein Typ die Basis eines anderen ist.|  
|[IsSame-Struktur](../windows/issame-structure.md)|Überprüft, ob ein Typ angegebenes ist identisch mit einem anderen angegebenen Typ.|  
|[Nil-Struktur](../windows/nil-structure.md)|Wird verwendet, um einen Vorlagenparameter nicht angegeben, optionale anzugeben.|  
|[RemoveReference-Struktur](../windows/removereference-structure.md)|Entfernt den Verweis oder Rvalue-Verweis Merkmal aus der angegebenen Klassenvorlagenparameter.|  
|[RuntimeClassBase-Struktur](../windows/runtimeclassbase-structure.md)|Zum Erkennen von `RuntimeClass` in die [stellen](../windows/make-function.md) Funktion.|  
|[RuntimeClassBaseT-Struktur](../windows/runtimeclassbaset-structure.md)|Stellt Hilfsmethoden für `QueryInterface` Vorgänge und die erste Schnittstellen-IDs.|  
|[VerifyInheritanceHelper-Struktur](../windows/verifyinheritancehelper-structure.md)|Testet, ob eine Schnittstelle von einer anderen Schnittstelle abgeleitet wird.|  
|[VerifyInterfaceHelper-Struktur](../windows/verifyinterfacehelper-structure.md)|Überprüft, ob die vom Vorlagenparameter angegebene Schnittstelle bestimmte Anforderungen erfüllt.|  
  
### <a name="enumerations"></a>Enumerationen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AsyncStatusInternal-Enumeration](../windows/asyncstatusinternal-enumeration.md)|Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die **Windows::Foundation::AsyncStatus** Enumeration.|  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ActivationFactoryCallback-Funktion](../windows/activationfactorycallback-function.md)|Ruft die aktivierungsfactory für die angegebene Aktivierung-ID.|  
|[Move-Funktion](../windows/move-function.md)|Verschiebt das angegebene Argument von einem Speicherort an einen anderen.|  
|[RaiseException-Funktion](../windows/raiseexception-function.md)|Löst eine Ausnahme im aufrufenden Thread.|  
|[Swap-Funktion (Windows Runtime C++-Vorlagenbibliothek)](../windows/swap-function-windows-runtime-cpp-template-library.md)|Vertauscht die Werte der beiden angegebenen Argumente.|  
|[TerminateMap-Funktion](../windows/terminatemap-function.md)|Fährt den Klassenfactorys im angegebenen Modul.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h client.h corewrappers.h event.h ftm.h implements.h internal.h, module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::wrl::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)