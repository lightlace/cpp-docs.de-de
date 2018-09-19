---
title: Ausnahmen (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/18/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e7514fdfc07fcbb4a1fff42d80fd138ab7d6043
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100247"
---
# <a name="exceptions-ccx"></a>Ausnahmen (C++/CX)

Fehlerbehandlung in C++ / CX basiert auf Ausnahmen. Klicken Sie auf der untersten Ebene werden Fehlermeldungen angezeigt werden Windows-Runtime-Komponenten als HRESULT-Werte. In C++ / CX werden diese Werte zu stark typisierten Ausnahmen, die einen HRESULT-Wert und einer Beschreibung, die Sie programmgesteuert erreichen können enthalten konvertiert.  Ausnahmen werden als `ref class` implementiert, die von `Platform::Exception`abgeleitet ist.  Der Namespace `Platform` definiert verschiedene Ausnahmeklassen für die häufigsten HRESULT-Werte. Alle anderen Werte werden über die Klasse `Platform::COMException` gemeldet. Alle Ausnahmeklassen haben ein Feld [Exception::HResult](platform-exception-class.md#hresult) , das Sie verwenden können, um den ursprünglichen HRESULT-Wert abzurufen. Sie können auch die Aufruflisteninformationen für Benutzercode im Debugger überprüfen, mit deren Hilfe kann die ursprüngliche Quelle der Ausnahme zu ermitteln, selbst wenn sie aus Code stammt, die in einer anderen Sprache als C++ geschrieben wurde.

## <a name="exceptions"></a>Ausnahmen

In C++-Programm können Sie auslösen und Abfangen einer Ausnahme, die von einem Windows-Runtime-Vorgang ist, wird eine Ausnahme, die von abgeleitet ist `std::exception`, oder einen benutzerdefinierten Typ. Sie müssen eine Windows-Runtime-Ausnahme auslösen, nur, wenn sie die Anwendungsgrenze anwendungsbinärschnittstelle (ABI), z. B. anwendungsbinärschnittstelle, wenn der Code, der die Ausnahme abfängt, die in JavaScript geschrieben ist. Wenn eine nicht - Windows-Runtime C++-Ausnahme die ABI-Grenze erreicht, wird die Ausnahme in übersetzt eine `Platform::FailureException` Ausnahme aus, die ein E_FAIL HRESULT darstellt. Weitere Informationen zur ABI finden Sie unter [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Sie können deklarieren, ein [Platform:: Exception](platform-exception-class.md) mithilfe einer von zwei Konstruktoren verwenden, die entweder einen HRESULT-Parameter oder einen HRESULT-Parameter und ein [Platform:: String](platform-string-class.md)^-Parameter, der über übergeben werden kann die Die ABI an eine beliebige Windows-Runtime-app, die ihn verarbeitet. Alternativ dazu können Sie eine Ausnahme deklarieren, indem Sie eine von zwei [Exception::CreateException](platform-exception-class.md#createexception) -Methodenüberladungen verwenden, die entweder einen HRESULT-Parameter oder einen HRESULT-Parameter und einen `Platform::String^` -Parameter akzeptieren.

## <a name="standard-exceptions"></a>Standardausnahmen

C++ / CX unterstützt eine Reihe von Standardausnahmen, die typische HRESULT-Fehler darstellen. Jede Standardausnahme wird von [Platform::COMException](platform-comexception-class.md)abgeleitet, die wiederum von `Platform::Exception`abgeleitet wird. Wenn Sie eine Ausnahme über die ABI-Grenze hinweg auslösen, müssen Sie eine der Standardausnahmen auslösen.

Sie können keinen eigenen Ausnahmetyp von `Platform::Exception`ableiten. Verwenden Sie zum Auslösen einer benutzerdefinierten Ausnahme ein benutzerdefiniertes HRESULT, um ein `COMException` -Objekt zu erstellen.

In der folgenden Tabelle sind die Standardausnahmen aufgelistet.

|name|Zugrunde liegendes HRESULT|Beschreibung|
|----------|------------------------|-----------------|
|COMException|*Benutzerdefiniertes HRESULT*|Wird ausgelöst, wenn ein COM-Methodenaufruf ein unbekanntes HRESULT zurückgibt.|
|AccessDeniedException|E\_ACCESSDENIED|Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.|
|ChangedStateException|E\_CHANGED\_ZUSTAND|Wird ausgelöst, wenn Methoden eines Auflistungsiterators oder einer Auflistungsansicht aufgerufen werden, nachdem die übergeordnete Auflistung geändert wurde, wodurch die Ergebnisse der Methode ungültig wurden.|
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Wird ausgelöst, wenn eine COM-Klasse nicht registriert wurde.|
|DisconnectedException|RPC\_E\_GETRENNT|Wird ausgelöst, wenn ein Objekt von den Clients getrennt wurde.|
|FailureException|E\_FEHL|Wird ausgelöst, wenn ein Vorgang fehlschlägt.|
|InvalidArgumentException|E\_INVALIDARG|Wird ausgelöst, wenn eines der Argumente für eine Methode ungültig ist.|
|InvalidCastException|E\_NOINTERFACE|Wird ausgelöst, wenn ein Typ nicht in einen anderen Typ umgewandelt werden kann.|
|NotImplementedException|E\_NOTIMPL|Wird ausgelöst, wenn eine Schnittstellenmethode nicht bei der Klasse implementiert wurde.|
|NullReferenceException|E\_ZEIGER|Wird ausgelöst, wenn der Versuch gemacht wird, einen Verweis auf ein NULL-Objekt zu dereferenzieren.|
|ObjectDisposedException|RO\_E\_GESCHLOSSEN|Wird ausgelöst, wenn ein Vorgang für ein verworfenes Objekt ausgeführt wird.|
|OperationCanceledException|E\_ABBRECHEN|Wird nach dem Abbrechen eines Vorgangs ausgelöst.|
|OutOfBoundsException|E\_GRENZEN|Wird ausgelöst, wenn ein Vorgang versucht, auf Daten außerhalb des gültigen Bereichs zuzugreifen.|
|OutOfMemoryException|E\_OUTOFMEMORY|Wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist, um den Vorgang abzuschließen.|
|WrongThreadException|RPC\_E\_FALSCHE\_THREAD|Wird ausgelöst, wenn ein Thread über einen Schnittstellenzeiger aufruft, der für ein Proxyobjekt ist, das nicht zum Apartment des Threads gehört.|

## <a name="hresult-and-message-properties"></a>HResult- und Meldungseigenschaften

Alle Ausnahmen verfügen über eine [-HResult](platform-comexception-class.md#hresult) -Eigenschaft und eine [-Meldungseigenschaft](platform-comexception-class.md#message) . Die [Exception::HResult](platform-exception-class.md#hresult) -Eigenschaft ruft den der Ausnahme zugrunde liegenden numerischen HRESULT-Wert ab. Die [Exception::Message](platform-exception-class.md#message) -Eigenschaft ruft die vom System bereitgestellte Zeichenfolge ab, die die Ausnahme beschreibt. In Windows 8 wird die Nachricht wird nur im Debugger verfügbar und ist schreibgeschützt. Dies bedeutet, dass Sie sie nicht ändern können, wenn Sie die Ausnahme erneut auslösen. In Windows 8.1 können Sie auf die Meldungszeichenfolge programmgesteuert zugreifen und eine neue Nachricht bereitstellen, wenn Sie die Ausnahme erneut auslösen. Bessere Aufruflisteninformationen einschließlich Aufruflisten für asynchrone Methodenaufrufe sind auch im Debugger verfügbar.

### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie Sie eine Windows-Runtime--Ausnahme für synchrone Operationen ausgelöst wird:

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

Im nächsten Beispiel wird gezeigt, wie die Ausnahme abgefangen wird.

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

Klicken Sie zum Abfangen von Ausnahmen, die während einer asynchronen Operation ausgelöst werden, die Aufgabenklasse, und fügen Sie eine fehlerbehandlungsfortsetzung hinzu. Die Fehlerbehandlungsfortsetzung marshallt Ausnahmen, die für andere Threads ausgelöst und zurück an den aufrufenden Thread gegeben werden, damit Sie alle potenziellen Ausnahmen an nur einem Punkt im Code behandeln können. Weitere Informationen finden Sie unter [asynchrone Programmierung in C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps).

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected-Ereignis

In Windows 8.1 können Sie abonnieren das [:: unhandlederrordetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror#Windows_ApplicationModel_Core_ICoreApplicationUnhandledError_UnhandledErrorDetected) statisches Ereignis, das Zugriff auf nicht behandelte Fehler, die sind im Begriff bietet, den Prozess beenden. Unabhängig davon, wo der Fehler verursacht wurde, erreicht er diesen Handler als ein [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) -Objekt, das mit den Ereignis-Args übergeben wird. Wenn Sie `Propagate` für das Objekt aufrufen, wird eine `Platform::*Exception` des Typs, der dem Fehlercode entspricht, erstellt und ausgelöst. In catch-Blöcken können Sie bei Bedarf den Benutzerzustand speichern und dann zulassen, dass der Prozess beendet wird, indem Sie `throw`aufrufen. Sie können auch etwas unternehmen, um das Programm in einen bekannten Zustand zurückzuführen. Das grundlegende Muster wird im folgenden Beispiel veranschaulicht:

In app.xaml.h:

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

In app.xaml.cpp:

```cpp
// Subscribe to the event, for example in the app class constructor:
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);

// Event handler implementation:
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)
{
    auto err = e->UnhandledError;

    if (!err->Handled) //Propagate has not been called on it yet.
{
    try
    {
        err->Propagate();
    }
    // Catch any specific exception types if you know how to handle them
    catch (AccessDeniedException^ ex)
    {
        // TODO: Log error and either take action to recover
        // or else re-throw exception to continue fail-fast
    }
}
```

### <a name="remarks"></a>Hinweise

C++ / CX verwendet nicht die `finally` Klausel.

## <a name="see-also"></a>Siehe auch

[Sprachreferenz zu Visual C++](visual-c-language-reference-c-cx.md)<br/>
[Namespaceverweis](namespaces-reference-c-cx.md)
