---
title: Ausnahmen (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2018
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: "22"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e36360279adf22857cfdb5b2f79ffdd7486ca008
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="exceptions-ccx"></a>Ausnahmen (C++/CX)

Fehlerbehandlung in C + c++ / CX basiert auf Ausnahmen. Auf der untersten Ebene werden Fehler von Windows-Runtime-Komponenten als HRESULT-Werte gemeldet. In C + c++ / CX werden diese Werte zu stark typisierten Ausnahmen, die einen HRESULT-Wert und einer Beschreibung, die Sie programmgesteuert erreichen können enthalten konvertiert.  Ausnahmen werden als `ref class` implementiert, die von `Platform::Exception`abgeleitet ist.  Der Namespace `Platform` definiert verschiedene Ausnahmeklassen für die häufigsten HRESULT-Werte. Alle anderen Werte werden über die Klasse `Platform::COMException` gemeldet. Alle Ausnahmeklassen haben ein Feld [Exception::HResult](platform-exception-class.md#hresult) , das Sie verwenden können, um den ursprünglichen HRESULT-Wert abzurufen. Sie können auch die Aufruflisteninformationen für Benutzercode im Debugger überprüfen, mit deren Hilfe kann die ursprüngliche Quelle der Ausnahme zu ermitteln, selbst wenn sie aus Code stammt, die in einer anderen Sprache als C++ geschrieben wurde.

## <a name="exceptions"></a>Ausnahmen

In C++-Programm können Sie auslösen und abfangen, eine Ausnahme, die aus einer Windows-Runtime-Vorgang stammen, wird eine Ausnahme, die abgeleitet ist `std::exception`, oder einen benutzerdefinierten Typ. Sie müssen ein Windows-Runtime-Ausnahme nur, wenn sie die Anwendungsgrenze anwendungsbinärschnittstelle (ABI), z. B. anwendungsbinärschnittstelle wird, wenn der Code, der die Ausnahme abfängt, in JavaScript geschrieben ist. Wenn eine nicht - Windows-Runtime C++-Ausnahme die ABI-Grenze erreicht, wird die Ausnahme in übersetzt eine `Platform::FailureException` Ausnahme aus, die ein E_FAIL HRESULT darstellt. Weitere Informationen zur ABI finden Sie unter [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Sie können eine [Platform::Exception](platform-exception-class.md) deklarieren, indem Sie einen von zwei Konstruktoren verwenden, die entweder einen HRESULT-Parameter akzeptieren oder einen HRESULT-Parameter und einen [Platform::String](platform-string-class.md)^-Parameter verwenden, der über die ABI an eine beliebige Windows Store-App übergeben werden kann, die ihn verarbeitet. Alternativ dazu können Sie eine Ausnahme deklarieren, indem Sie eine von zwei [Exception::CreateException](platform-exception-class.md#createexception) -Methodenüberladungen verwenden, die entweder einen HRESULT-Parameter oder einen HRESULT-Parameter und einen `Platform::String^` -Parameter akzeptieren.

## <a name="standard-exceptions"></a>Standardausnahmen

C + c++ / CX unterstützt eine Reihe von Standardausnahmen, die typische HRESULT-Fehler darstellen. Jede Standardausnahme wird von [Platform::COMException](platform-comexception-class.md)abgeleitet, die wiederum von `Platform::Exception`abgeleitet wird. Wenn Sie eine Ausnahme über die ABI-Grenze hinweg auslösen, müssen Sie eine der Standardausnahmen auslösen.

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

In diesem Beispiel wird gezeigt, wie eine Windows-Runtime-Ausnahme für synchrone Operationen ausgelöst wird:

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

Im nächsten Beispiel wird gezeigt, wie die Ausnahme abgefangen wird.

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

Verwenden Sie zum Abfangen von Ausnahmen, die während einer asynchronen Operation ausgelöst werden, die Aufgabenklasse, und fügen Sie eine Fehlerbehandlungsfortsetzung hinzu. Die Fehlerbehandlungsfortsetzung marshallt Ausnahmen, die für andere Threads ausgelöst und zurück an den aufrufenden Thread gegeben werden, damit Sie alle potenziellen Ausnahmen an nur einem Punkt im Code behandeln können. Weitere Informationen finden Sie unter [asynchrone Programmierung in C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps).

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected-Ereignis

In Windows 8.1 können Sie zum Abonnieren der [:: unhandlederrordetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror#Windows_ApplicationModel_Core_ICoreApplicationUnhandledError_UnhandledErrorDetected) statische Ereignis, das Zugriff auf nicht behandelte Fehler, die sind im Begriff bietet, den Prozess beenden. Unabhängig davon, wo der Fehler verursacht wurde, erreicht er diesen Handler als eine [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) -Objekt, das mit den Ereignisargumenten übergeben wird. Wenn Sie `Propagate` für das Objekt aufrufen, wird eine `Platform::*Exception` des Typs, der dem Fehlercode entspricht, erstellt und ausgelöst. In catch-Blöcken können Sie bei Bedarf den Benutzerzustand speichern und dann zulassen, dass der Prozess beendet wird, indem Sie `throw`aufrufen. Sie können auch etwas unternehmen, um das Programm in einen bekannten Zustand zurückzuführen. Das grundlegende Muster wird im folgenden Beispiel veranschaulicht:

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

C + c++ / CX verwendet nicht die `finally` Klausel.

## <a name="see-also"></a>Siehe auch

[Visual C++-Sprachreferenz](visual-c-language-reference-c-cx.md)  
[Namespaceverweis](namespaces-reference-c-cx.md)  
