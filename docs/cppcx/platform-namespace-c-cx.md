---
title: Plattformnamespace (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- Platform/Platform
dev_langs:
- C++
helpviewer_keywords:
- Platform Namespace (C++/CX)
ms.assetid: b160e822-d424-43d2-ba60-57b0e81f259c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d88b40d53dbae737822ca31e6fa9cf15c947970
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755813"
---
# <a name="platform-namespace-ccx"></a>Plattformnamespace (C++/CX)
Enthält integrierte Typen, die mit Windows Runtime kompatibel sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
using namespace Platform;  
```  
  
### <a name="members"></a>Member  
 **Attribute**  
  
 Der Namespace "Platform" enthält Attribute, Klassen, Enumerationen, Schnittstellen und Strukturen. "Platform" enthält auch geschachtelte Namespaces.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Flags|Gibt an, dass eine Enumeration als Bitfeld, d. h. als Gruppe von Flags, behandelt werden kann.|  
|MTAThread|Legt Multithreaded Apartment (MTA) als Threadingmodell für Anwendungen fest.|  
|STAThread|Legt Singlethreaded Apartment (STA) als Threadingmodell für Anwendungen fest.|  
  
 **Klassen**  
  
 Der Namespace "Platform" hat die folgenden Klassen.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[Platform::AccessDeniedException-Klasse](../cppcx/platform-accessdeniedexception-class.md)|Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.|  
|[Platform::Agile-Klasse](../cppcx/platform-agile-class.md)|Stellt ein nicht agiles Objekt als agiles Objekt dar.|  
|[Platform::Array-Klasse](../cppcx/platform-array-class.md)|Stellt ein eindimensionales, änderbares Array dar.|  
|[Platform::ArrayReference-Klasse](../cppcx/platform-arrayreference-class.md)|Stellt ein Array dar, dessen Initialisierung zur Minimierung von Kopiervorgängen optimiert wird.|  
|[Platform::Box-Klasse](../cppcx/platform-box-class.md)|Wird zum Deklarieren eines geschachtelten Typs verwendet, der einen Werttyp wie Windows::Foundation::DateTime oder einen int64-Wert kapselt, wenn dieser über die Anwendungsbinärdateischnittstelle (ABI) übergeben oder in einer Variablen des Typs [Platform::Object^](../cppcx/platform-object-class.md)gespeichert wird.|  
|[Platform::ChangedStateException-Klasse](../cppcx/platform-changedstateexception-class.md)|Wird ausgelöst, wenn Methoden eines Auflistungsiterators oder einer Auflistungsansicht aufgerufen werden, nachdem die übergeordnete Auflistung geändert wurde. Hierdurch werden die Ergebnisse der Methode ungültig.|  
|[Platform::ClassNotRegisteredException-Klasse](../cppcx/platform-classnotregisteredexception-class.md)|Wird ausgelöst, wenn eine COM-Klasse nicht registriert wurde.|  
|[Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)|Stellt die Ausnahme dar, die ausgelöst wird, wenn ein COM-Methodenaufruf einen unbekannten Wert zurückgibt.|  
|[Platform::Delegate-Klasse](../cppcx/platform-delegate-class.md)|Repräsentiert die Signatur einer Rückruffunktion.|  
|[Platform::DisconnectedException-Klasse](../cppcx/platform-disconnectedexception-class.md)|Die Verbindung zwischen dem Objekt und seinen Clients wurde getrennt.|  
|[Platform::Exception-Klasse](../cppcx/platform-exception-class.md)|Stellt Fehler dar, die beim Ausführen einer Anwendung auftreten. Die Basisklasse für Ausnahmen.|  
|[Platform::FailureException-Klasse](../cppcx/platform-failureexception-class.md)|Wird ausgelöst, wenn bei dem Vorgang ein Fehler aufgetreten ist. Dies entspricht dem E_FAIL HRESULT.|  
|[Platform::Guid-Wertklasse](../cppcx/platform-guid-value-class.md)|Stellt eine GUID im Windows Runtime-Typsystem dar.|  
|[Platform::InvalidArgumentException-Klasse](../cppcx/platform-invalidargumentexception-class.md)|Wird ausgelöst, wenn eines der Argumente für eine Methode ungültig ist.|  
|[Platform::InvalidCastException-Klasse](../cppcx/platform-invalidcastexception-class.md)|Wird bei ungültiger Umwandlung oder expliziter Konvertierung ausgelöst.|  
|[Platform::MTAThreadAttribute-Klasse](../cppcx/platform-mtathreadattribute-class.md)|Legt Multithreaded Apartment (MTA) als Threadingmodell für Anwendungen fest.|  
|[Platform::NotImplementedException-Klasse](../cppcx/platform-notimplementedexception-class.md)|Wird ausgelöst, wenn eine Schnittstellenmethode nicht bei der Klasse implementiert wurde.|  
|[Platform::NullReferenceException-Klasse](../cppcx/platform-nullreferenceexception-class.md)|Wird ausgelöst, wenn der Versuch gemacht wird, einen Verweis auf ein NULL-Objekt zu dereferenzieren.|  
|[Platform::Object-Klasse](../cppcx/platform-object-class.md)|Eine Basisklasse, die gemeinsames Verhalten bereitstellt.|  
|[Platform::ObjectDisposedException-Klasse](../cppcx/platform-objectdisposedexception-class.md)|Wird ausgelöst, wenn ein Vorgang für ein verworfenes Objekt ausgeführt wird.|  
|[Platform::OperationCanceledException-Klasse](../cppcx/platform-operationcanceledexception-class.md)|Wird nach dem Abbrechen eines Vorgangs ausgelöst.|  
|[Platform::OutOfBoundsException-Klasse](../cppcx/platform-outofboundsexception-class.md)|Wird ausgelöst, wenn ein Vorgang versucht, auf Daten außerhalb des gültigen Bereichs zuzugreifen.|  
|[Platform::OutOfMemoryException-Klasse](../cppcx/platform-outofmemoryexception-class.md)|Wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist, um den Vorgang abzuschließen.|  
|[Platform::STAThreadAttribute-Klasse](../cppcx/platform-stathreadattribute-class.md)|Legt Singlethreaded Apartment (STA) als Threadingmodell für Anwendungen fest.|  
|[Platform::String-Klasse](../cppcx/platform-string-class.md)|Eine sequenzielle Auflistung von Unicode-Zeichen, die zum Darstellen von Text verwendet werden.|  
|[Platform::StringReference-Klasse](../cppcx/platform-stringreference-class.md)|Ermöglicht den Zugriff auf Zeichenfolgepuffer mit minimalem Kopieraufwand.|  
|[Platform::Type-Klasse](../cppcx/platform-type-class.md)|Identifiziert einen integrierten Typ durch eine Kategorie-Enumeration.|  
|[Platform::ValueType-Klasse](../cppcx/platform-valuetype-class.md)|Die Basisklasse für Instanzen von Werttypen.|  
|[Platform::WeakReference-Klasse](../cppcx/platform-weakreference-class.md)|Stellt einen schwachen Verweis auf Verweisklassenobjekte bereit, bei dem der Verweiszähler nicht hochgezählt wird.|  
|[Platform::WriteOnlyArray-Klasse](../cppcx/platform-writeonlyarray-class.md)|Stellt ein eindimensionales, lesegeschütztes Array dar, das als Eingabeparameter für Methoden verwendet wird, die das FillArray-Muster implementieren.|  
|[Platform::WrongThreadException-Klasse](../cppcx/platform-wrongthreadexception-class.md)|Wird ausgelöst, wenn ein Thread über einen Schnittstellenzeiger aufruft, der für ein Proxyobjekt ist, das nicht zum Apartment des Threads gehört.|  
  
 **Schnittstellenimplementierungen**  
  
 Der Namespace "Platform" definiert die folgenden Schnittstellen.  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|[Platform::IBox-Schnittstelle](../cppcx/platform-ibox-interface.md)|Wird zum Übergeben von Werttypen verwendet, deren Parameter als Platform::Object^ typisiert werden.|  
|[Platform::IBoxArray-Schnittstelle](../cppcx/platform-iboxarray-interface.md)|Die Schnittstelle, die verwendet wird, um Funktionen, deren Parameter als Platform::Array typisiert werden, Werttypen-Arrays zu übergeben.|  
|[Platform::IDisposable-Schnittstelle](../cppcx/platform-idisposable-interface.md)|Wird verwendet, um nicht verwaltete Ressourcen freizugeben.|  
  
 **Enumerationen**  
  
 Der Namespace "Platform" hat die folgenden Enumerationen.  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|[Platform::CallbackContext-Enumeration](../cppcx/platform-callbackcontext-enumeration.md)|Eine Enumeration, die als Parameter des Delegatkonstruktors verwendet wird. Sie bestimmt, ob der Rückruf zum Ausgangsthread oder zum Aufruferthread gemarshallt werden soll.|  
|[Platform::TypeCode-Enumeration](../cppcx/platform-typecode-enumeration.md)|Gibt eine numerische Kategorie an, die einen integrierten Typ darstellt.|  
  
 **Strukturen**  
  
 Der Namespace "Platform" hat die folgenden Strukturen.  
  
|Struktur|Beschreibung|  
|---------------|-----------------|  
|[Platform::Enum-Klasse](../cppcx/platform-enum-class.md)|Stellt eine benannte Konstante dar.|  
|[Platform::Guid-Wertklasse](../cppcx/platform-guid-value-class.md)|Stellt einen Guid dar.|  
|[Platform::IntPtr-Wertklasse](../cppcx/platform-intptr-value-class.md)|Ein Zeiger mit Vorzeichen, dessen Größe für die Plattform (32-Bit oder 64-Bit) geeignet ist.|  
|[Platform::SizeT-Wertklasse](../cppcx/platform-sizet-value-class.md)|Ein Datentyp ohne Vorzeichen, der verwendet wird, um die Größe eines Objekts darzustellen.|  
|[Platform::UIntPtr-Wertklasse](../cppcx/platform-uintptr-value-class.md)|Ein Zeiger ohne Vorzeichen, dessen Größe für die Plattform (32-Bit oder 64-Bit) geeignet ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Platform:: Collections-Namespace](../cppcx/platform-collections-namespace.md)   
 [Platform::Runtime::CompilerServices-Namespace](../cppcx/platform-runtime-compilerservices-namespace.md)   
 [Platform::Runtime::InteropServices-Namespace](../cppcx/platform-runtime-interopservices-namespace.md)   
 [Platform::Metadata-Namespace](../cppcx/platform-metadata-namespace.md)