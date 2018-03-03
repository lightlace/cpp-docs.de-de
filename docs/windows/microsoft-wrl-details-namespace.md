---
title: Microsoft::wrl::Details Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f005969908252602cb2fb4bdd73d3b55ae342a99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details-Namespace
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>Member  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRef-Klasse](../windows/comptrref-class.md)|Repräsentiert einen Verweis auf ein Objekt des Typs ComPtr\<T >.|  
|[ComPtrRefBase-Klasse](../windows/comptrrefbase-class.md)|Stellt die Basisklasse für die [ComPtrRef](../windows/comptrref-class.md) Klasse.|  
|[DontUseNewUseMake-Klasse](../windows/dontusenewusemake-class.md)|Verhindert die Verwendung von Operator `new` in `RuntimeClass`. Folglich müssen Sie verwenden die [Make-Funktion](../windows/make-function.md) stattdessen.|  
|[EventTargetArray-Klasse](../windows/eventtargetarray-class.md)|Stellt ein Array von Ereignishandlern.|  
|[MakeAllocator-Klasse](../windows/makeallocator-class.md)|Belegt Speicher für eine aktivierbare Klasse, mit oder ohne Unterstützung der schwache Verweis.|  
|[ModuleBase-Klasse](../windows/modulebase-class.md)|Stellt die Basisklasse der [Modul](../windows/module-class.md) Klassen.|  
|[RemoveIUnknown-Klasse](../windows/removeiunknown-class.md)|Stellt einen Typ, der entspricht einer `IUnknown`-Basis Typ verfügt jedoch nicht virtuell `QueryInterface`, `AddRef`, und `Release` Methoden.|  
|[WeakReference-Klasse](../windows/weakreference-class1.md)|Stellt eine *schwachen Verweis* , mit dem Windows-Runtime oder eine klassische COM verwendet werden kann Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|  
  
### <a name="structures"></a>Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ArgTraits-Struktur](../windows/argtraits-structure.md)|Deklariert einen angegebenen Delegaten, Benutzeroberfläche und eine anonyme Memberfunktion, die eine angegebene Anzahl von Parametern verfügt.|  
|[ArgTraitsHelper-Struktur](../windows/argtraitshelper-structure.md)|Unterstützt definiert allgemeine Merkmale Delegatargumente.|  
|[BoolStruct-Struktur](../windows/boolstruct-structure.md)|Definiert, ob ein comptr-Objekt die Objektlebensdauer einer Schnittstelle verwaltet. BoolStruct wird intern von verwendet die [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) Operator.|  
|[CreatorMap-Struktur](../windows/creatormap-structure.md)|Enthält Informationen zum Initialisieren, registrieren und Aufheben der Registrierung Objekten.|  
|[DerefHelper-Struktur](../windows/derefhelper-structure.md)|In einem Funktionszeiger darstellen der `T*` Template-Parameter.|  
|[EnableIf-Struktur](../windows/enableif-structure.md)|Definiert einen Datenmember des Typs, der durch den zweiten Vorlagenparameter angegeben wird, wenn der erste Vorlagenparameter ergibt `true`.|  
|[FactoryCache-Struktur](../windows/factorycache-structure.md)|Enthält den Speicherort einer Klassenfactory und einem Wert, der ein registriertes Windows-Runtime oder COM-Klasse-Objekt identifiziert.|  
|[ImplementsBase-Struktur](../windows/implementsbase-structure.md)|Zum Überprüfen der Vorlage Parametertypen in [Implements-Struktur](../windows/implements-structure.md).|  
|[ImplementsHelper-Struktur](../windows/implementshelper-structure.md)|Implementiert die [implementiert](../windows/implements-structure.md) Struktur.|  
|[InterfaceList-Struktur](../windows/interfacelist-structure.md)|So erstellen eine rekursive Liste von Schnittstellen verwendet.|  
|[InterfaceListHelper-Struktur](../windows/interfacelisthelper-structure.md)|Erstellt ein `InterfaceList` Typ durch Anwenden der angegebenen Parameter Vorlagenargumente rekursiv.|  
|[InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)|Implementiert Allgemeine Merkmale einer Schnittstelle.|  
|[InvokeHelper-Struktur](../windows/invokehelper-structure.md)|Stellt eine Implementierung der Methode Invoke() basierend auf der angegebenen Nummer und Typ der Argumente.|  
|[IsBaseOfStrict-Struktur](../windows/isbaseofstrict-structure.md)|Testet, ob ein Typ die Basis eines anderen ist.|  
|[IsSame-Struktur](../windows/issame-structure.md)|Überprüft, ob ein Typ angegebener ist identisch mit einem anderen angegebenen Typ.|  
|[Nil-Struktur](../windows/nil-structure.md)|Wird verwendet, um einen Vorlagenparameter nicht angegeben, optional eine anzugeben.|  
|[RemoveReference-Struktur](../windows/removereference-structure.md)|Entfernt das Merkmal "Verweis" oder "Rvalue-Verweis" aus der angegebenen Klassenvorlagenparameter.|  
|[RuntimeClassBase-Struktur](../windows/runtimeclassbase-structure.md)|Ermittelt, `RuntimeClass` in der [stellen](../windows/make-function.md) Funktion.|  
|[RuntimeClassBaseT-Struktur](../windows/runtimeclassbaset-structure.md)|Stellt Hilfsmethoden für `QueryInterface` Vorgänge und die erste Schnittstellen-IDs.|  
|[VerifyInheritanceHelper-Struktur](../windows/verifyinheritancehelper-structure.md)|Testet, ob eine Schnittstelle, die von einer anderen Schnittstelle abgeleitet wird.|  
|[VerifyInterfaceHelper-Struktur](../windows/verifyinterfacehelper-structure.md)|Überprüft, ob die Schnittstelle mit dem Vorlagenparameter angegebene bestimmte Anforderungen erfüllt.|  
  
### <a name="enumerations"></a>Enumerationen  
  
|name|Beschreibung|  
|----------|-----------------|  
|[AsyncStatusInternal-Enumeration](../windows/asyncstatusinternal-enumeration.md)|Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die **Windows::Foundation::AsyncStatus** Enumeration.|  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ActivationFactoryCallback-Funktion](../windows/activationfactorycallback-function.md)|Ruft die aktivierungsfactory für die angegebene Aktivierung-ID.|  
|[Move-Funktion](../windows/move-function.md)|Verschiebt das angegebene Argument zwischen Speicherorten.|  
|[RaiseException-Funktion](../windows/raiseexception-function.md)|Löst eine Ausnahme in den aufrufenden Thread aus.|  
|[Swap-Funktion (C++-Vorlagenbibliothek der Windows-Runtime)](../windows/swap-function-windows-runtime-cpp-template-library.md)|Vertauscht die Werte der beiden angegebenen Argumente.|  
|[TerminateMap-Funktion](../windows/terminatemap-function.md)|Fährt den Klassenfactorys im angegebenen Modul.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)