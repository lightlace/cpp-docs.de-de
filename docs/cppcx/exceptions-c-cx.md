---
title: Ausnahmen (C++/CX)
ms.date: 07/02/2019
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
ms.openlocfilehash: ade406dc5db6022978f83715555c425caef4375b
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740173"
---
# <a name="exceptions-ccx"></a>Ausnahmen (C++/CX)

Die Fehlerbehandlung C++in/CX basiert auf Ausnahmen. Auf der grundlegendsten Ebene melden Windows-Runtime Komponenten Fehler als HRESULT-Werte. In C++/CX werden diese Werte in stark typisierte Ausnahmen konvertiert, die einen HRESULT-Wert und eine Zeichen folgen Beschreibung enthalten, auf die Sie Programm gesteuert zugreifen können.  Ausnahmen werden als `ref class` implementiert, die von `Platform::Exception`abgeleitet ist.  Der Namespace `Platform` definiert verschiedene Ausnahmeklassen für die häufigsten HRESULT-Werte. Alle anderen Werte werden über die Klasse `Platform::COMException` gemeldet. Alle Ausnahmeklassen haben ein Feld [Exception::HResult](platform-exception-class.md#hresult) , das Sie verwenden können, um den ursprünglichen HRESULT-Wert abzurufen. Sie können auch die aufrufstackinformationen für Benutzercode im Debugger überprüfen, um die ursprüngliche Quelle der Ausnahme zu ermitteln, auch wenn Sie aus Code stammt, der in einer anderen Sprache als C++geschrieben wurde.

## <a name="exceptions"></a>Ausnahmen

In Ihrem C++ Programm können Sie eine Ausnahme auslösen und abfangen, die von einem Windows-Runtime-Vorgang stammt, eine Ausnahme, die `std::exception`von abgeleitet ist, oder einen benutzerdefinierten Typ. Sie müssen eine Windows-Runtime Ausnahme nur auslösen, wenn Sie die Schnittstelle der Anwendungs Binärschnittstelle (ABI) überschreitet, z. b. wenn der Code, der die Ausnahme abfängt, in JavaScript geschrieben wird. Wenn eine nicht Windows-Runtime C++ Ausnahme die ABI-Grenze erreicht, wird die Ausnahme in eine `Platform::FailureException` -Ausnahme übersetzt, die ein E_FAIL HRESULT darstellt. Weitere Informationen zur ABI finden Sie unter [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Sie können eine [Platform:: Exception](platform-exception-class.md) deklarieren, indem Sie einen von zwei Konstruktoren verwenden, die entweder einen HRESULT-Parameter oder einen HRESULT-Parameter und einen [Platform:: String](platform-string-class.md)^-Parameter verwenden, der über die ABI an eine beliebige Windows-Runtime App übergeben werden kann, die ihn verarbeitet. Alternativ dazu können Sie eine Ausnahme deklarieren, indem Sie eine von zwei [Exception::CreateException](platform-exception-class.md#createexception) -Methodenüberladungen verwenden, die entweder einen HRESULT-Parameter oder einen HRESULT-Parameter und einen `Platform::String^` -Parameter akzeptieren.

## <a name="standard-exceptions"></a>Standardausnahmen

C++/CX unterstützt eine Reihe von Standard Ausnahmen, die typische HRESULT-Fehler darstellen. Jede Standardausnahme wird von [Platform::COMException](platform-comexception-class.md)abgeleitet, die wiederum von `Platform::Exception`abgeleitet wird. Wenn Sie eine Ausnahme über die ABI-Grenze hinweg auslösen, müssen Sie eine der Standardausnahmen auslösen.

Sie können keinen eigenen Ausnahmetyp von `Platform::Exception`ableiten. Verwenden Sie zum Auslösen einer benutzerdefinierten Ausnahme ein benutzerdefiniertes HRESULT, um ein `COMException` -Objekt zu erstellen.

In der folgenden Tabelle sind die Standardausnahmen aufgelistet.

|Name|Zugrunde liegendes HRESULT|Beschreibung|
|----------|------------------------|-----------------|
|COMException|*Benutzerdefiniertes HRESULT*|Wird ausgelöst, wenn ein COM-Methodenaufruf ein unbekanntes HRESULT zurückgibt.|
|AccessDeniedException|E\_ACCESSDENIED|Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.|
|ChangedStateException|E\_STATUS\_GEÄNDERT|Wird ausgelöst, wenn Methoden eines Auflistungsiterators oder einer Auflistungsansicht aufgerufen werden, nachdem die übergeordnete Auflistung geändert wurde, wodurch die Ergebnisse der Methode ungültig wurden.|
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Wird ausgelöst, wenn eine COM-Klasse nicht registriert wurde.|
|DisconnectedException|RPC\_-\_E GETRENNT|Wird ausgelöst, wenn ein Objekt von den Clients getrennt wurde.|
|FailureException|E\_FEHLSCHLAGEN|Wird ausgelöst, wenn ein Vorgang fehlschlägt.|
|InvalidArgumentException|E\_INVALIDARG|Wird ausgelöst, wenn eines der Argumente für eine Methode ungültig ist.|
|InvalidCastException|E\_NOINTERFACE|Wird ausgelöst, wenn ein Typ nicht in einen anderen Typ umgewandelt werden kann.|
|NotImplementedException|E\_NOTIMPL|Wird ausgelöst, wenn eine Schnittstellenmethode nicht bei der Klasse implementiert wurde.|
|NullReferenceException|E\_-ZEIGER|Wird ausgelöst, wenn der Versuch gemacht wird, einen Verweis auf ein NULL-Objekt zu dereferenzieren.|
|ObjectDisposedException|RO\_E\_GESCHLOSSEN|Wird ausgelöst, wenn ein Vorgang für ein verworfenes Objekt ausgeführt wird.|
|OperationCanceledException|E\_ABBRECHEN|Wird nach dem Abbrechen eines Vorgangs ausgelöst.|
|OutOfBoundsException|E\_-BEGRENZUNGEN|Wird ausgelöst, wenn ein Vorgang versucht, auf Daten außerhalb des gültigen Bereichs zuzugreifen.|
|OutOfMemoryException|E\_OUTO-MEMORY|Wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist, um den Vorgang abzuschließen.|
|WrongThreadException|FALSCHER RPC-\_THREAD\_\_|Wird ausgelöst, wenn ein Thread über einen Schnittstellenzeiger aufruft, der für ein Proxyobjekt ist, das nicht zum Apartment des Threads gehört.|

## <a name="hresult-and-message-properties"></a>HResult- und Meldungseigenschaften

Alle Ausnahmen verfügen über eine [-HResult](platform-comexception-class.md#hresult) -Eigenschaft und eine [-Meldungseigenschaft](platform-comexception-class.md#message) . Die [Exception::HResult](platform-exception-class.md#hresult) -Eigenschaft ruft den der Ausnahme zugrunde liegenden numerischen HRESULT-Wert ab. Die [Exception::Message](platform-exception-class.md#message) -Eigenschaft ruft die vom System bereitgestellte Zeichenfolge ab, die die Ausnahme beschreibt. In Windows 8 ist die Meldung nur im Debugger verfügbar und ist schreibgeschützt. Dies bedeutet, dass Sie sie nicht ändern können, wenn Sie die Ausnahme erneut auslösen. In Windows 8.1 können Sie auf die Meldungszeichenfolge programmgesteuert zugreifen und eine neue Nachricht bereitstellen, wenn Sie die Ausnahme erneut auslösen. Bessere Aufruflisteninformationen einschließlich Aufruflisten für asynchrone Methodenaufrufe sind auch im Debugger verfügbar.

### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie eine Windows-Runtime Ausnahme für synchrone Operationen ausgelöst wird:

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

Im nächsten Beispiel wird gezeigt, wie die Ausnahme abgefangen wird.

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

Verwenden Sie zum Abfangen von Ausnahmen, die während eines asynchronen Vorgangs ausgelöst werden, die Aufgaben Klasse, und fügen Sie eine Fehler Behandlungs Fortsetzung hinzu. Die Fehlerbehandlungsfortsetzung marshallt Ausnahmen, die für andere Threads ausgelöst und zurück an den aufrufenden Thread gegeben werden, damit Sie alle potenziellen Ausnahmen an nur einem Punkt im Code behandeln können. Weitere Informationen finden Sie unter [Asynchrone Programmierung in C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps).

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected-Ereignis

In Windows 8.1 Sie das statische Ereignis [Windows:: applicationmodel:: Core:: coreapplication:: unhandlederrorerkannte](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror.unhandlederrordetected) abonnieren, das den Zugriff auf nicht behandelte Fehler ermöglicht, die den Prozess beenden. Unabhängig davon, wodurch der Fehler verursacht wurde, erreicht er diesen Handler als [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) -Objekt, das mit den Ereignisargumenten übergeben wird. Wenn Sie `Propagate` für das Objekt aufrufen, wird eine `Platform::*Exception` des Typs, der dem Fehlercode entspricht, erstellt und ausgelöst. In catch-Blöcken können Sie bei Bedarf den Benutzerzustand speichern und dann zulassen, dass der Prozess beendet wird, indem Sie `throw`aufrufen. Sie können auch etwas unternehmen, um das Programm in einen bekannten Zustand zurückzuführen. Das grundlegende Muster wird im folgenden Beispiel veranschaulicht:

In "App. XAML. h":

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

In "App. XAML. cpp":

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

C++/CX verwendet nicht die `finally` -Klausel.

## <a name="see-also"></a>Siehe auch

[C++-/CX-Programmiersprachenreferenz](visual-c-language-reference-c-cx.md)<br/>
[Referenz zu Namespaces](namespaces-reference-c-cx.md)
