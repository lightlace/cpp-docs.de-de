---
title: "Ausnahmen (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: 22
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 22
---
# Ausnahmen (C++/CX)
Fehlerbehandlung in [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) basiert auf Ausnahmen. Auf der untersten Ebene werden [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] Fehler von Komponenten als HRESULT\-Werte gemeldet. In [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] werden diese Werte zu stark typisierten Ausnahmen konvertiert, die einen HRESULT\-Wert und in [!INCLUDE[win81](../cppcx/includes/win81-md.md)] eine Zeichenfolgenbeschreibung enthalten, die Sie programmgesteuert erreichen können.  Ausnahmen werden als `ref class` implementiert, die von `Platform::Exception` abgeleitet ist.  Der Namespace `Platform` definiert verschiedene Ausnahmeklassen für die häufigsten HRESULT\-Werte. Alle anderen Werte werden über die Klasse `Platform::COMException` gemeldet. Alle Ausnahmeklassen haben ein Feld [Exception::HResult Property](../cppcx/exception-hresult-property.md), das Sie verwenden können, um den ursprünglichen HRESULT\-Wert abzurufen. In [!INCLUDE[win81](../cppcx/includes/win81-md.md)] können Sie Aufruflisteninformationen für Benutzercode auch im Debugger überprüfen. Damit kann die ursprüngliche Quelle der Ausnahme festgelegt werden, selbst wenn sie aus Code stammt, der in einer anderen Sprache als C\+\+ geschrieben wurde.  
  
## Ausnahmen  
 Im C\+\+\-Programm können Sie eine Ausnahme auslösen und abfangen, die von einer [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Operation stammt, sowie eine Ausnahme, die von `std::exception` oder von einem benutzerdefinierten Typ abgeleitet ist, auslösen und abfangen. Sie müssen eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Ausnahme nur dann auslösen, wenn sie die Grenze der Anwendungsbinärschnittstelle \(ABI\) überschreitet, z. B. wenn der Code, der die Ausnahme abfängt, in JavaScript geschrieben ist. Wenn eine Nicht\-[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]C\+\+\-Ausnahme die ABI\-Grenze erreicht, wird die Ausnahme in eine `Platform::FailureException`\-Ausnahme übersetzt, die ein E\_FAIL HRESULT darstellt. Weitere Informationen zur ABI finden Sie unter [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
 Sie können eine [Platform::Exception](../cppcx/platform-exception-class.md) deklarieren, indem Sie einen von zwei Konstruktoren verwenden, die entweder einen HRESULT\-Parameter akzeptieren oder einen HRESULT\-Parameter und einen [Platform::String](../cppcx/platform-string-class.md)^\-Parameter verwenden, der über die ABI an eine beliebige Windows Store\-App übergeben werden kann, die ihn verarbeitet. Alternativ dazu können Sie eine Ausnahme deklarieren, indem Sie eine von zwei [Exception::CreateException](../cppcx/exception-createexception-method.md)\-Methodenüberladungen verwenden, die entweder einen HRESULT\-Parameter oder einen HRESULT\-Parameter und einen `Platform::String^`\-Parameter akzeptieren.  
  
## Standardausnahmen  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] unterstützt eine Reihe von Standardausnahmen, die typische HRESULT\-Fehler darstellen. Jede Standardausnahme wird von [Platform::COMException](../cppcx/platform-comexception-class.md) abgeleitet, die wiederum von `Platform::Exception` abgeleitet wird. Wenn Sie eine Ausnahme über die ABI\-Grenze hinweg auslösen, müssen Sie eine der Standardausnahmen auslösen.  
  
 Sie können keinen eigenen Ausnahmetyp von `Platform::Exception` ableiten. Verwenden Sie zum Auslösen einer benutzerdefinierten Ausnahme ein benutzerdefiniertes HRESULT, um ein `COMException`\-Objekt zu erstellen.  
  
 In der folgenden Tabelle sind die Standardausnahmen aufgelistet.  
  
|Name|Zugrunde liegendes HRESULT|Beschreibung|  
|----------|--------------------------------|------------------|  
|COMException|*Benutzerdefiniertes HRESULT*|Wird ausgelöst, wenn ein COM\-Methodenaufruf ein unbekanntes HRESULT zurückgibt.|  
|AccessDeniedException|E\_ACCESSDENIED|Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.|  
|ChangedStateException|E\_CHANGED\_STATE|Wird ausgelöst, wenn Methoden eines Auflistungsiterators oder einer Auflistungsansicht aufgerufen werden, nachdem die übergeordnete Auflistung geändert wurde, wodurch die Ergebnisse der Methode ungültig wurden.|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Wird ausgelöst, wenn eine COM\-Klasse nicht registriert wurde.|  
|DisconnectedException|RPC\_E\_DISCONNECTED|Wird ausgelöst, wenn ein Objekt von den Clients getrennt wurde.|  
|FailureException|E\_FAIL|Wird ausgelöst, wenn ein Vorgang fehlschlägt.|  
|InvalidArgumentException|E\_INVALIDARG|Wird ausgelöst, wenn eines der Argumente für eine Methode ungültig ist.|  
|InvalidCastException|E\_NOINTERFACE|Wird ausgelöst, wenn ein Typ nicht in einen anderen Typ umgewandelt werden kann.|  
|NotImplementedException|E\_NOTIMPL|Wird ausgelöst, wenn eine Schnittstellenmethode nicht bei der Klasse implementiert wurde.|  
|NullReferenceException|E\_POINTER|Wird ausgelöst, wenn der Versuch gemacht wird, einen Verweis auf ein NULL\-Objekt zu dereferenzieren.|  
|ObjectDisposedException|RO\_E\_CLOSED|Wird ausgelöst, wenn ein Vorgang für ein verworfenes Objekt ausgeführt wird.|  
|OperationCanceledException|E\_ABORT|Wird nach dem Abbrechen eines Vorgangs ausgelöst.|  
|OutOfBoundsException|E\_BOUNDS|Wird ausgelöst, wenn ein Vorgang versucht, auf Daten außerhalb des gültigen Bereichs zuzugreifen.|  
|OutOfMemoryException|E\_OUTOFMEMORY|Wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist, um den Vorgang abzuschließen.|  
|WrongThreadException|RPC\_E\_WRONG\_THREAD|Wird ausgelöst, wenn ein Thread über einen Schnittstellenzeiger aufruft, der für ein Proxyobjekt ist, das nicht zum Apartment des Threads gehört.|  
  
## HResult\- und Meldungseigenschaften  
 Alle Ausnahmen verfügen über eine [\-HResult](../cppcx/comexception-hresult-property.md)\-Eigenschaft und eine [\-Meldungseigenschaft](../cppcx/comexception-message-property.md). Die [Exception::HResult](../cppcx/exception-hresult-property.md)\-Eigenschaft ruft den der Ausnahme zugrunde liegenden numerischen HRESULT\-Wert ab. Die [Exception::Message](../cppcx/exception-message-property.md)\-Eigenschaft ruft die vom System bereitgestellte Zeichenfolge ab, die die Ausnahme beschreibt. In [!INCLUDE[win8](../cppcx/includes/win8-md.md)] ist die Meldung nur im Debugger verfügbar und ist schreibgeschützt. Dies bedeutet, dass Sie sie nicht ändern können, wenn Sie die Ausnahme erneut auslösen. In [!INCLUDE[win81](../cppcx/includes/win81-md.md)] können Sie auf die Meldungszeichenfolge programmgesteuert zugreifen und eine neue Nachricht bereitstellen, wenn Sie die Ausnahme erneut auslösen. Bessere Aufruflisteninformationen einschließlich Aufruflisten für asynchrone Methodenaufrufe sind auch im Debugger verfügbar.  
  
## Beispiele  
 Dieses Beispiel zeigt, wie eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Ausnahme für synchrone Operationen ausgelöst wird:  
  
 [!code-cpp[cx_exceptions#01](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#01)]  
  
 Im nächsten Beispiel wird gezeigt, wie die Ausnahme abgefangen wird.  
  
 [!code-cpp[cx_exceptions#02](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#02)]  
  
 Verwenden Sie zum Abfangen von Ausnahmen, die während einer asynchronen Operation ausgelöst werden, die Aufgabenklasse, und fügen Sie eine Fehlerbehandlungsfortsetzung hinzu. Die Fehlerbehandlungsfortsetzung marshallt Ausnahmen, die für andere Threads ausgelöst und zurück an den aufrufenden Thread gegeben werden, damit Sie alle potenziellen Ausnahmen an nur einem Punkt im Code behandeln können. Weitere Informationen finden Sie unter [Asynchrone Programmierung in C\+\+](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx).  
  
## UnhandledErrorDetected\-Ereignis  
 In [!INCLUDE[win81](../cppcx/includes/win81-md.md)] können Sie das statische Ereignis [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx) abonnieren, das Zugriff auf nicht behandelte Fehler bietet, die den Prozess beenden. Unabhängig davon, wodurch der Fehler verursacht wurde, erreicht er diesen Handler als [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx)\-Objekt, das mit den Ereignisargumenten übergeben wird. Wenn Sie `Propagate` für das Objekt aufrufen, wird eine `Platform::*Exception` des Typs, der dem Fehlercode entspricht, erstellt und ausgelöst. In catch\-Blöcken können Sie bei Bedarf den Benutzerzustand speichern und dann zulassen, dass der Prozess beendet wird, indem Sie `throw` aufrufen. Sie können auch etwas unternehmen, um das Programm in einen bekannten Zustand zurückzuführen. Das grundlegende Muster wird im folgenden Beispiel veranschaulicht:  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
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
  
## Hinweise  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] verwendet nicht die `finally`\-Klausel.  
  
## Siehe auch  
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)