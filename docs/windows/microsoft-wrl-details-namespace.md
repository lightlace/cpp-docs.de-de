---
title: Microsoft::wrl::Details-Namespace | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 095d355ae26faf447b54a99437c843322efe5cb9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611747"
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details-Namespace

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>Member

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[ComPtrRef-Klasse](../windows/comptrref-class.md)|Stellt einen Verweis auf ein Objekt des Typs ComPtr\<T >.|
|[ComPtrRefBase-Klasse](../windows/comptrrefbase-class.md)|Stellt die Basisklasse für die [ComPtrRef](../windows/comptrref-class.md) Klasse.|
|[DontUseNewUseMake-Klasse](../windows/dontusenewusemake-class.md)|Verhindert die Verwendung von Operator **neue** in `RuntimeClass`. Folglich müssen Sie verwenden die [Funktion](../windows/make-function.md) stattdessen.|
|[EventTargetArray-Klasse](../windows/eventtargetarray-class.md)|Stellt ein Array von Ereignishandlern.|
|[MakeAllocator-Klasse](../windows/makeallocator-class.md)|Belegt Speicher für eine aktivierbare Klasse, mit oder ohne Unterstützung von schwachen Verweis.|
|[ModuleBase-Klasse](../windows/modulebase-class.md)|Stellt die Basisklasse der [Modul](../windows/module-class.md) Klassen.|
|[RemoveIUnknown-Klasse](../windows/removeiunknown-class.md)|Ist einen Typ, der entspricht einer `IUnknown`-Basis-Typ, weist jedoch nicht virtuell `QueryInterface`, `AddRef`, und `Release` Methoden.|
|[WeakReference-Klasse](../windows/weakreference-class1.md)|Stellt eine *schwachen Verweis* , die verwendet werden kann, mit der Windows-Runtime oder ein klassisches COM verwenden. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|

### <a name="structures"></a>Strukturen

|Name|Beschreibung|
|----------|-----------------|
|[ArgTraits-Struktur](../windows/argtraits-structure.md)|Deklariert einen angegebenen Delegaten, Benutzeroberfläche und eine anonyme Memberfunktion, die eine angegebene Anzahl von Parametern.|
|[ArgTraitsHelper-Struktur](../windows/argtraitshelper-structure.md)|Hilft, die gemeinsamen Merkmale der Argumente des Delegaten definieren.|
|[BoolStruct-Struktur](../windows/boolstruct-structure.md)|Definiert, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet. `BoolStruct` wird intern von verwendet die [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) Operator.|
|[CreatorMap-Struktur](../windows/creatormap-structure.md)|Enthält Informationen zum Initialisieren, registrieren und Aufheben der Registrierung Objekten.|
|[DerefHelper-Struktur](../windows/derefhelper-structure.md)|Einen dereferenzierter Zeiger zum Darstellen der `T*` Template-Parameter.|
|[EnableIf-Struktur](../windows/enableif-structure.md)|Definiert einen Datenmember des Typs durch den zweiten Vorlagenparameter angegeben wird, wenn der erste Vorlagenparameter ergibt **"true"**.|
|[FactoryCache-Struktur](../windows/factorycache-structure.md)|Enthält den Speicherort einer Klassenfactory und einem Wert, der ein registriertes Windows-Runtime oder COM-Klasse-Objekt identifiziert.|
|[ImplementsBase-Struktur](../windows/implementsbase-structure.md)|Zum Überprüfen der Vorlage Parametertypen in verwendet [Implements-Struktur](../windows/implements-structure.md).|
|[ImplementsHelper-Struktur](../windows/implementshelper-structure.md)|Hilft, implementieren die [implementiert](../windows/implements-structure.md) Struktur.|
|[InterfaceList-Struktur](../windows/interfacelist-structure.md)|Verwendet, um eine rekursive Liste von Schnittstellen erstellen.|
|[InterfaceListHelper-Struktur](../windows/interfacelisthelper-structure.md)|Erstellt eine `InterfaceList` Typs rekursiv die angegebenen Parameter Vorlagenargumente angewendet.|
|[InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)|Implementiert die allgemeinen Merkmale einer Schnittstelle.|
|[InvokeHelper-Struktur](../windows/invokehelper-structure.md)|Stellt eine Implementierung der `Invoke()` -Methode basierend auf der angegebenen Nummer und Typ der Argumente.|
|[IsBaseOfStrict-Struktur](../windows/isbaseofstrict-structure.md)|Testet, ob ein Typ die Basis eines anderen ist.|
|[IsSame-Struktur](../windows/issame-structure.md)|Überprüft, ob es sich bei einem Typ angegeben ist identisch mit einer anderen angegebenen Typ.|
|[Nil-Struktur](../windows/nil-structure.md)|Wird verwendet, um einen Vorlagenparameter nicht angegeben, optional eine anzugeben.|
|[RemoveReference-Struktur](../windows/removereference-structure.md)|Entfernt das Merkmal "Verweis" oder "Rvalue-Verweis" aus der angegebenen Klasse Template-Parameter.|
|[RuntimeClassBase-Struktur](../windows/runtimeclassbase-structure.md)|Ermittelt, `RuntimeClass` in die [stellen](../windows/make-function.md) Funktion.|
|[RuntimeClassBaseT-Struktur](../windows/runtimeclassbaset-structure.md)|Stellt Hilfsmethoden für `QueryInterface` Vorgänge und die erste Schnittstellen-IDs.|
|[VerifyInheritanceHelper-Struktur](../windows/verifyinheritancehelper-structure.md)|Testet, ob eine Schnittstelle, die von einer anderen Schnittstelle abgeleitet wird.|
|[VerifyInterfaceHelper-Struktur](../windows/verifyinterfacehelper-structure.md)|Überprüft, ob die die Template-Parameter angegebene Schnittstelle bestimmte Anforderungen erfüllt.|

### <a name="enumerations"></a>Enumerationen

|name|Beschreibung|
|----------|-----------------|
|[AsyncStatusInternal-Enumeration](../windows/asyncstatusinternal-enumeration.md)|Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die `Windows::Foundation::AsyncStatus` Enumeration.|

### <a name="functions"></a>Funktionen

|Name|Beschreibung|
|----------|-----------------|
|[ActivationFactoryCallback-Funktion](../windows/activationfactorycallback-function.md)|Ruft die aktivierungsfactory für die Aktivierung der angegebenen ID.|
|[Move-Funktion](../windows/move-function.md)|Verschiebt das angegebene Argument von einem Speicherort.|
|[RaiseException-Funktion](../windows/raiseexception-function.md)|Löst eine Ausnahme aus, in dem aufrufenden Thread aus.|
|[Swap-Funktion (C++-Vorlagenbibliothek der Windows-Runtime)](../windows/swap-function-windows-runtime-cpp-template-library.md)|Tauscht die Werte der beiden angegebenen Argumente.|
|[TerminateMap-Funktion](../windows/terminatemap-function.md)|Klassenfactorys im angegebenen Modul wird heruntergefahren.|

## <a name="requirements"></a>Anforderungen

**Header:** async.h client.h corewrappers.h event.h ftm.h implements.h internal.h, module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)  
[Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)