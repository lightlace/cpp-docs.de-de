---
title: Microsoft::WRL::Details-Namespace
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: fce6e620600164e73d3708d98d8a7fa979e8ab42
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027474"
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
|[ComPtrRef-Klasse](comptrref-class.md)|Stellt einen Verweis auf ein Objekt des Typs ComPtr\<T >.|
|[ComPtrRefBase-Klasse](comptrrefbase-class.md)|Stellt die Basisklasse für die [ComPtrRef](comptrref-class.md) Klasse.|
|[DontUseNewUseMake-Klasse](dontusenewusemake-class.md)|Verhindert die Verwendung von Operator `new` in `RuntimeClass`. Folglich müssen Sie verwenden die [Funktion](make-function.md) stattdessen.|
|[EventTargetArray-Klasse](eventtargetarray-class.md)|Stellt ein Array von Ereignishandlern.|
|[MakeAllocator-Klasse](makeallocator-class.md)|Belegt Speicher für eine aktivierbare Klasse, mit oder ohne Unterstützung von schwachen Verweis.|
|[ModuleBase-Klasse](modulebase-class.md)|Stellt die Basisklasse der [Modul](module-class.md) Klassen.|
|[RemoveIUnknown-Klasse](removeiunknown-class.md)|Ist einen Typ, der entspricht einer `IUnknown`-Basis-Typ, weist jedoch nicht virtuell `QueryInterface`, `AddRef`, und `Release` Methoden.|
|[WeakReference-Klasse](weakreference-class.md)|Stellt eine *schwachen Verweis* , die verwendet werden kann, mit der Windows-Runtime oder ein klassisches COM verwenden. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.|

### <a name="structures"></a>Strukturen

|Name|Beschreibung|
|----------|-----------------|
|[ArgTraits-Struktur](argtraits-structure.md)|Deklariert einen angegebenen Delegaten, Benutzeroberfläche und eine anonyme Memberfunktion, die eine angegebene Anzahl von Parametern.|
|[ArgTraitsHelper-Struktur](argtraitshelper-structure.md)|Hilft, die gemeinsamen Merkmale der Argumente des Delegaten definieren.|
|[BoolStruct-Struktur](boolstruct-structure.md)|Definiert, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet. `BoolStruct` wird intern von verwendet die [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) Operator.|
|[CreatorMap-Struktur](creatormap-structure.md)|Enthält Informationen zum Initialisieren, registrieren und Aufheben der Registrierung Objekten.|
|[DerefHelper-Struktur](derefhelper-structure.md)|Einen dereferenzierter Zeiger zum Darstellen der `T*` Template-Parameter.|
|[EnableIf-Struktur](enableif-structure.md)|Definiert einen Datenmember des Typs durch den zweiten Vorlagenparameter angegeben wird, wenn der erste Vorlagenparameter ergibt `true`.|
|[FactoryCache-Struktur](factorycache-structure.md)|Enthält den Speicherort einer Klassenfactory und einem Wert, der ein registriertes Windows-Runtime oder COM-Klasse-Objekt identifiziert.|
|[ImplementsBase-Struktur](implementsbase-structure.md)|Zum Überprüfen der Vorlage Parametertypen in verwendet [Implements-Struktur](implements-structure.md).|
|[ImplementsHelper-Struktur](implementshelper-structure.md)|Hilft, implementieren die [implementiert](implements-structure.md) Struktur.|
|[InterfaceList-Struktur](interfacelist-structure.md)|Verwendet, um eine rekursive Liste von Schnittstellen erstellen.|
|[InterfaceListHelper-Struktur](interfacelisthelper-structure.md)|Erstellt eine `InterfaceList` Typs rekursiv die angegebenen Parameter Vorlagenargumente angewendet.|
|[InterfaceTraits-Struktur](interfacetraits-structure.md)|Implementiert die allgemeinen Merkmale einer Schnittstelle.|
|[InvokeHelper-Struktur](invokehelper-structure.md)|Stellt eine Implementierung der `Invoke()` -Methode basierend auf der angegebenen Nummer und Typ der Argumente.|
|[IsBaseOfStrict-Struktur](isbaseofstrict-structure.md)|Testet, ob ein Typ die Basis eines anderen ist.|
|[IsSame-Struktur](issame-structure.md)|Überprüft, ob es sich bei einem Typ angegeben ist identisch mit einer anderen angegebenen Typ.|
|[Nil-Struktur](nil-structure.md)|Wird verwendet, um einen Vorlagenparameter nicht angegeben, optional eine anzugeben.|
|[RemoveReference-Struktur](removereference-structure.md)|Entfernt das Merkmal "Verweis" oder "Rvalue-Verweis" aus der angegebenen Klasse Template-Parameter.|
|[RuntimeClassBase-Struktur](runtimeclassbase-structure.md)|Ermittelt, `RuntimeClass` in die [stellen](make-function.md) Funktion.|
|[RuntimeClassBaseT-Struktur](runtimeclassbaset-structure.md)|Stellt Hilfsmethoden für `QueryInterface` Vorgänge und die erste Schnittstellen-IDs.|
|[VerifyInheritanceHelper-Struktur](verifyinheritancehelper-structure.md)|Testet, ob eine Schnittstelle, die von einer anderen Schnittstelle abgeleitet wird.|
|[VerifyInterfaceHelper-Struktur](verifyinterfacehelper-structure.md)|Überprüft, ob die die Template-Parameter angegebene Schnittstelle bestimmte Anforderungen erfüllt.|

### <a name="enumerations"></a>Enumerationen

|Name|Beschreibung|
|----------|-----------------|
|[AsyncStatusInternal-Enumeration](asyncstatusinternal-enumeration.md)|Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die `Windows::Foundation::AsyncStatus` Enumeration.|

### <a name="functions"></a>Funktionen

|Name|Beschreibung|
|----------|-----------------|
|[ActivationFactoryCallback-Funktion](activationfactorycallback-function.md)|Ruft die aktivierungsfactory für die Aktivierung der angegebenen ID.|
|[Move-Funktion](move-function.md)|Verschiebt das angegebene Argument von einem Speicherort.|
|[RaiseException-Funktion](raiseexception-function.md)|Löst eine Ausnahme aus, in dem aufrufenden Thread aus.|
|[Swap-Funktion (WRL)](swap-function-wrl.md)|Tauscht die Werte der beiden angegebenen Argumente.|
|[TerminateMap-Funktion](terminatemap-function.md)|Klassenfactorys im angegebenen Modul wird heruntergefahren.|

## <a name="requirements"></a>Anforderungen

**Header:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::Wrappers-Namespace](microsoft-wrl-wrappers-namespace.md)