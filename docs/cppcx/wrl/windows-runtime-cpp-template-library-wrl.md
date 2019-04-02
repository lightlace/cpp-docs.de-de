---
title: Windows Runtime C++ Template Library (WRL)
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
ms.openlocfilehash: 5c1a4e7df424499f400dbd70d675956deef6bc5d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784350"
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows Runtime C++ Template Library (WRL)

Die C++-Vorlagenbibliothek für Windows-Runtime(WRL) ist eine Vorlagenbibliothek, die eine niederschwelligen Zugang zur Erstellung und Verwendung von Windows-Runtime-Komponenten bietet.

> [!NOTE]
> WRL das jetzt abgelöst von C++ / WinRT, ein C ++ 17-standardsprachprojektion für Windows-Runtime-APIs. C++ / WinRT finden Sie in das Windows 10 SDK Version 1803 gerechnet. C++ / WinRT ist nur in Headerdateien implementiert und bietet Ihnen mit erstklassigen Zugriff auf die moderne Windows-API.
>
> Mit C++ / WinRT, können Sie sowohl nutzen und Erstellen von Windows-Runtime-APIs mit einem beliebigen standardkonformen C ++ 17-Compiler. C++ / WinRT in der Regel eine bessere Leistung und erzeugt kleinere Binärdateien als jede andere Sprachoption für die Windows-Runtime. Wir weiterhin zur Unterstützung von C++ / CX- und WRL, jedoch dringend empfohlen, neue Anwendungen C++ mithilfe / WinRT. Weitere Informationen finden Sie unter [C++ / WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).

## <a name="benefits"></a>Vorteile

Die Windows Runtime C++ Template Library können Sie leichter zu implementieren und Komponenten von Component Object Model (COM) nutzen. Sie stellt Verwaltungstechniken wie die verweiszählung, um die Lebensdauer der Objekte zu verwalten und Testen von HRESULT-Werte, um festzustellen, ob ein Vorgang erfolgreich war oder fehlgeschlagen ist. Um die Windows Runtime C++ Template Library erfolgreich verwenden zu können, müssen Sie die folgenden Regeln und Techniken sorgfältig befolgen.

C++ / CX können Sie ganz auf hoher Ebene, Sprache basierende Windows-Runtime-Komponenten verwenden. Sowohl die Windows Runtime C++ Template Library und C++ / CX vereinfachen das Schreiben von Code für die Windows-Runtime, indem Sie automatisch für Sie da Verwaltungsaufgaben in Ihrem Namen ausgeführt.

Die Windows Runtime C++ Template Library und C++ / CX bieten unterschiedliche Vorteile. Hier sind einige Gründe, möglicherweise möchten verwenden die Windows Runtime C++ Template Library anstelle von C++ / CX:

- Windows Runtime C++ Template Library fügt nur wenig Abstraktion über die Windows Runtime Application Binary Interface (ABI), sodass Sie die Möglichkeit, den zugrunde liegenden Code besser steuern erstellen oder nutzen Sie die Windows-Runtime-APIs.

- C++ / CX stellt COM-HRESULT-Werte als Ausnahmen dar. Wenn Sie eine CodeBase geerbt haben, die verwendet wird, COM, oder eine, die keine Ausnahmen verwendet, finden Sie vielleicht, dass die Windows Runtime C++ Template Library eine natürlichere Weise mit der Windows-Runtime arbeiten ist, da Sie keine Ausnahmen verwendet werden.

   > [!NOTE]
   > Die Windows Runtime C++ Template Library HRESULT-Werte verwendet, und löst keine Ausnahmen. Darüber hinaus verwendet die Windows Runtime C++ Template Library intelligente Zeiger und das RAII-Muster, um dafür zu sorgen, dass Objekte ordnungsgemäß zerstört werden, wenn Ihr Anwendungscode eine Ausnahme auslöst. Weitere Informationen zu intelligenten Zeigern und RAII finden Sie unter [intelligente Zeiger](../../cpp/smart-pointers-modern-cpp.md) und [Objekte eigenen Ressourcen (RAII)](../../cpp/objects-own-resources-raii.md).

- Der Zweck und Entwurf von der Windows Runtime C++ Template Library ist inspiriert durch die Active Template Library (ATL), ist eine Gruppe von Template-basierten C++-Klassen, die das Programmieren von COM-Objekte vereinfachen. Da Windows Runtime C++ Template Library Standard-c++ verwendet, um die Windows-Runtime zu umschließen, können Sie leichter port und die Interaktion mit vielen vorhandenen COM-Komponenten, die in die Windows-Runtime in ATL geschriebenen. Wenn Sie ATL bereits kennen, können Sie feststellen, dass es sich bei Windows Runtime C++ Template Library-Programmierung einfacher ist.

## <a name="getting-started"></a>Erste Schritte

Hier sind einige Ressourcen, mit die Sie mit der Windows Runtime C++ Template Library sofort loslegen können.

[Die Windows-Runtime-Bibliothek (WRL)](https://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)<br/>
Erfahren Sie in diesem Channel 9-Video mehr darüber, wie die Windows Runtime C++ Template Library hilft, dass Sie die apps der universellen Windows-Plattform (UWP) und Informationen zum Erstellen und nutzen die Windows-Runtime-Komponenten schreiben.

[Vorgehensweise: Aktivieren und Verwenden einer Windows-Runtime-Komponente](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)<br/>
Zeigt, wie Sie mit der Windows-Runtime zu initialisieren und zu aktivieren und verwenden eine Windows-Runtime-Komponente der Windows Runtime C++ Template Library.

[Vorgehensweise: Abschließen asynchroner Vorgänge](how-to-complete-asynchronous-operations-using-wrl.md)<br/>
Zeigt, wie Sie mit der Windows Runtime C++ Template Library asynchrone Vorgänge starten und Arbeiten ausführen, wenn die Vorgänge abgeschlossen.

[Vorgehensweise: Behandeln von Ereignissen](how-to-handle-events-using-wrl.md)<br/>
Zeigt, wie Sie mit der Windows Runtime C++ Template Library abonnieren und Behandeln der Ereignisse von einem Windows-Runtime-Objekt.

[Exemplarische Vorgehensweise: Erstellen einer UWP-App mithilfe von WRL und Media Foundation](walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)<br/>
Erfahren Sie, wie Sie eine UWP-app zu erstellen, verwendet [Microsoft Media Foundation](/windows/desktop/medfound/microsoft-media-foundation-sdk).

[Vorgehensweise: Erstellen einer klassischen COM-Komponente](how-to-create-a-classic-com-component-using-wrl.md)<br/>
Zeigt, wie die Windows Runtime C++ Template Library verwenden, um eine grundlegende COM-Komponente und eine einfache Möglichkeit zur Registrierung und Nutzung der COM-Komponente aus einer desktop-app zu erstellen.

[Vorgehensweise: Direktes Instanziieren von WRL-Komponenten](how-to-instantiate-wrl-components-directly.md)<br/>
Erfahren Sie, wie Sie mit den Funktionen [Microsoft::WRL::Make](make-function.md) und [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md) eine Komponente aus dem Modul instanziieren, das sie definiert.

[Vorgehensweise: Verwenden von „winmdidl.exe“ und „midlrt.exe“ zum Erstellen von .h-Dateien aus Windows-Metadaten](use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)<br/>
Zeigt, wie benutzerdefinierte Komponenten für Windows-Runtime von WRL durch Erstellen einer IDL-Datei von den WINMD-Metadaten verarbeitet werden.

[Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
Zeigt, wie die [IXMLHTTPRequest2](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2) und [IXMLHTTPRequest2Callback](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2callback) Schnittstellen zusammen mit Aufgaben für HTTP-GET und POST-Anforderungen an einen Webdienst in einer UWP-app zu senden.

[Beispiel des Reise-Optimierer von Bing Maps](https://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)<br/>
Verwendet die `HttpRequest` -Klasse, die in definierten [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) im Rahmen einer vollständigen UWP-app.

[Beispiel zum Erstellen einer Windows Runtime DLL-Komponente mit C++](https://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)<br/>
Zeigt, wie die Windows Runtime C++ Template Library eine prozessinterne DLL-Komponente zu erstellen und nutzen es in C++ / CX, JavaScript und c#.

[DirectX marble Maze-Beispiel](https://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)<br/>
Veranschaulicht, wie die Windows Runtime C++ Template Library verwenden, um die Lebensdauer von COM-Komponenten wie DirectX und Media Foundation im Rahmen eines vollständigen 3D-Spiels verwalten.

[Senden von toastbenachrichtigungen aus desktop-apps-Beispiel](https://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)<br/>
Veranschaulicht, wie Sie die Windows Runtime C++ Template Library mit toastbenachrichtigungen aus einer desktop-app verwenden.

## <a name="windows-runtime-c-template-library-compared-to-atl"></a>Windows Runtime C++ Template Library, die im Vergleich mit ATL

Windows Runtime C++ Template Library ähnelt der Active Template Library (ATL) aus, da Sie ihn verwenden können, um kleine, schnelle COM-Objekte erstellen. Windows Runtime C++ Template Library und ATL auch andere Konzepte wie die Definition von Objekten in Modulen, die explizite Registrierung von Schnittstellen, gemeinsam, und die offene Erstellung von Objekten durch Factorys. Sie können mit Windows Runtime C++ Template Library vertraut sein, wenn Sie mit ATL vertraut sind.

Windows Runtime C++ Template Library unterstützt die COM-Funktionalität, die für UWP-apps erforderlich ist. Daher unterscheidet sie sich von ATL, da die direkte Unterstützung für COM-Funktionen wie Folgende fehlt:

- Aggregation

- vordefinierte Implementierungen

- duale Schnittstellen (`IDispatch`)

- Standardenumeratorschnittstellen

- Verbindungspunkte

- abtrennbare Schnittstellen

- OLE-Einbettung

- ActiveX-Steuerelemente

- COM+

## <a name="concepts"></a>Konzepte

Windows Runtime C++ Template Library enthält Typen, die einige grundlegende Konzepte darstellen. Im folgenden Abschnitt werden diese Typen beschrieben.

### <a name="comptr"></a>ComPtr

[ComPtr](comptr-class.md) ist ein Typ des *intelligenten Zeigermechanismus* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. Mit `ComPtr` deklarieren Sie eine Variable, die auf die Member eines Objekts zugreifen kann, das von der Schnittstelle abgeleitet wird. `ComPtr` verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf null geht.

### <a name="runtimeclass"></a>RuntimeClass

[RuntimeClass](runtimeclass-class.md) stellt eine instanziierte Klasse dar, die einen Satz angegebener Schnittstellen erbt. Ein `RuntimeClass` Objekt kann eine Kombination von Unterstützung für eine oder mehrere Windows-Runtime-COM-Schnittstellen oder einen schwachen Verweis auf eine Komponente bereitstellen.

### <a name="module"></a>Modul

[Module](module-class.md) stellt eine Auflistung von zugehörigen Objekten dar. Ein `Module` -Objekt verwaltet Klassenfactorys, die Objekte erstellen, und die Registrierung, die anderen Anwendungen die Verwendung eines Objekts ermöglicht.

### <a name="callback"></a>Rückruf

Die [Rückruf](callback-function-wrl.md) -Funktion erstellt ein Objekt, dessen Memberfunktion ein Ereignishandler ist (eine Rückrufmethode). Mit der `Callback` -Funktion schreiben Sie asynchrone Operationen.

### <a name="eventsource"></a>EventSource

Mit[EventSource](eventsource-class.md) verwalten Sie *Delegat* -Ereignishandler. Verwenden von Windows Runtime C++ Template Library, implementieren Sie einen Delegaten, und verwenden `EventSource` hinzufügen, entfernen und Aufrufen von Delegaten.

### <a name="asyncbase"></a>AsyncBase

[AsyncBase](asyncbase-class.md) stellt virtuelle Methoden, die das asynchrone Programmiermodell von Windows-Runtime darstellen. Überschreiben Sie die Member in dieser Klasse, um eine benutzerdefinierte Klasse zu erstellen, die einen asynchronen Vorgang starten, beenden oder seinen Fortschritt überprüfen kann.

### <a name="ftmbase"></a>FtmBase

[FtmBase](ftmbase-class.md) stellt ein Freethread-Marshaller-Objekt dar. `FtmBase` erstellt eine globale Schnittstellentabelle (GIT) und hilft bei der Verwaltung von Marshalling- und Proxyobjekten.

### <a name="weakref"></a>WeakRef

[WeakRef](weakref-class.md) ist ein Typ des intelligenten Zeigermechanismus, der einen *schwachen Verweis*auf ein Objekt darstellt, das möglicherweise zugänglich ist. Ein `WeakRef` -Objekt kann verwendet werden, indem nur die Windows-Runtime und nicht von klassischem com geschieht.

Ein `WeakRef` -Objekt stellt in der Regel ein Objekt dar, dessen Vorhandensein von einem externen Thread oder einer externen Anwendung gesteuert wird. Beispielsweise kann ein `WeakRef` -Objekt auf ein Dateiobjekt verweisen. Wenn die Datei geöffnet ist, so ist `WeakRef` gültig, und die referenzierte Datei ist zugänglich. Wenn die Datei hingegen geschlossen ist, so ist `WeakRef` ungültig, und die Datei ist nicht zugänglich.

## <a name="related-topics"></a>Verwandte Themen

|||
|-|-|
|[Schlüssel-APIs nach Kategorie](key-wrl-apis-by-category.md)|Hebt die primären Windows Runtime C++ Template Library-Typen, Funktionen und Makros.|
|[Verweis](wrl-reference.md)|Enthält Referenzinformationen für die Windows Runtime C++ Template Library.|
|[Kurzreferenz (Windows-Runtime und Visual C++)](../../cppcx/quick-reference-c-cx.md)|Beschreibt C++ / CX-Features, die die Windows-Runtime unterstützen.|
|[Verwenden von Windows-Runtime-Komponenten in Visual C++](/windows/uwp/winrt-components/walkthrough-creating-a-basic-windows-runtime-component-in-cpp-and-calling-it-from-javascript-or-csharp)|Zeigt, wie C++ / CX verwenden, um das Erstellen einer grundlegenden Komponente für Windows-Runtime.|
