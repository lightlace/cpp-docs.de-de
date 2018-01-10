---
title: Windows Runtime C++-Vorlagenbibliothek (WRL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e742b5509fd9a7889321e5e8c576e4fa3c8401cd
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows Runtime C++ Template Library (WRL)
Die Windows Runtime C++ Template Library (WRL) ist eine Vorlagenbibliothek, die eine Low-Level Methode zum Erstellen und Verwenden von Windows-Runtime-Komponenten bereitstellt.  
  
## <a name="benefits"></a>Vorteile  
 Der Windows Runtime C++ Template Library können Sie leichter zu implementieren und die Nutzung von Component Object Model (COM)-Komponenten. Sie stellt Verwaltungstechniken wie die Verweiszählung bereit, mit der die Lebensdauer der Objekte verwaltet wird, oder wie Tests von `HRESULT` -Werten, mit denen festgestellt wird, ob ein Vorgang erfolgreich war oder einen Fehler verursacht hat. Um die Windows Runtime C++ Template Library erfolgreich verwenden zu können, müssen Sie die folgenden Regeln und Techniken sorgfältig befolgen.  
  
 Die C + c++ / CX ist eine sprachbasierte Sprache basierende Methode zur Windows-Runtime-Komponenten verwenden. Windows Runtime C++ Template Library sowohl die C + c++ / CX vereinfachen die Verfassung von Code für die Windows-Runtime durch Ausführen von Wartungsaufgaben automatisch in Ihrem Namen.  
  
 Die Windows Runtime C++ Template Library und C + c++ / CX bieten unterschiedliche Vorteile. Hier sind einige Gründe aufgeführt, die möglicherweise möchten die Windows Runtime C++ Template Library anstelle von C# verwenden c++ / CX:  
  
-   Windows Runtime C++ Template Library fügt nur wenig Abstraktion über die Windows Runtime Anwendung binären Schnittstelle (ABI), und Sie haben die Möglichkeit, den zugrunde liegenden Code besser steuern erstellen oder nutzen von Windows-Runtime-APIs.  
  
-   C + c++ / CX stellt COM `HRESULT` -Werte als Ausnahmen. Wenn Sie eine CodeBase, die COM verwendet geerbt haben, oder eine, die keine Ausnahmen verwendet, stellen Sie möglicherweise fest, dass der Windows Runtime C++ Template Library eine natürliche Möglichkeit ist, mit der Windows-Runtime arbeiten, da Sie keine Ausnahmen verwendet.  
  
    > [!NOTE]
    >  Verwendet die Windows Runtime C++ Template Library `HRESULT` -Werte und löst keine Ausnahmen. Außerdem verwendet die Windows Runtime C++ Template Library intelligente Zeiger und das RAII-Muster, um dafür zu sorgen, dass Objekte ordnungsgemäß zerstört werden, wenn der Anwendungscode eine Ausnahme auslöst. Weitere Informationen zu intelligenten Zeigern und RAII finden Sie unter [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md) und [Objekte eigenen Ressourcen (RAII)](../cpp/objects-own-resources-raii.md).  
  
-   Der Zweck und Entwurf der Windows Runtime C++ Template Library wird inspiriert durch die ATL Active Template Library (), ist eine Gruppe vorlagenbasierter C++-Klassen, die die Programmierung von COM-Objekten vereinfachen. Da Windows Runtime C++ Template Library Standard-c++ verwendet, um die Windows-Runtime zu umschließen, können Sie leichter Portierung und die Interaktion mit vielen vorhandenen COM-Komponenten, die in der Windows-Runtime in ATL geschriebenen. Wenn Sie ATL bereits kennen, können Sie feststellen, dass Windows Runtime C++ Template Library-Programmierung vereinfacht.  
  
## <a name="getting-started"></a>Erste Schritte  
 Hier sind einige Ressourcen, mit denen Sie sofort mit der Windows Runtime C++ Template Library arbeiten abrufen können.  
  
 [Die Windows-Runtime-Bibliothek (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
 Erfahren Sie in diesem Channel 9-Video mehr darüber, wie die Windows Runtime C++ Template Library hilft, dass Sie Schreibberechtigungen universelle Windows-Plattform-apps und das Erstellen und Nutzen von Windows-Runtime-Komponenten.  
  
 [Vorgehensweise: Aktivieren und verwenden Sie eine Windows-Runtime-Komponente](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
 Zeigt, wie die Windows Runtime C++ Template Library verwenden, um Windows-Runtime zu initialisieren und zu aktivieren und verwenden Sie eine Windows-Runtime-Komponente.  
  
 [Vorgehensweise: Abschließen asynchroner Vorgänge](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
 Zeigt, wie die Windows Runtime C++ Template Library verwenden, um asynchrone Vorgänge starten und Arbeiten ausführen, wenn die Vorgänge abgeschlossen.  
  
 [Vorgehensweise: Behandeln von Ereignissen](../windows/how-to-handle-events-using-wrl.md)  
 Zeigt, wie die Windows Runtime C++ Template Library zu abonnieren und Behandeln der Ereignisse von einem Windows-Runtime-Objekt.  
  
 [Exemplarische Vorgehensweise: Erstellen einer grundlegenden Windows-Runtime-Komponente](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)  
 Zeigt, wie die Windows Runtime C++ Template Library verwenden, um einer grundlegenden Komponente für Windows-Runtime zu erstellen, die zwei Zahlen addiert. Außerdem veranschaulicht, wie Ereignisse auslösen und mithilfe der Komponente aus einer Uwp-app, die JavaScript nutzt.  
  
 [Exemplarische Vorgehensweise: Erstellen einer Windows Store-App mithilfe von WRL und Media Foundation](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
 Erfahren Sie, wie Sie eine universelle Windows-Plattform-app erstellen, verwendet [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 [Vorgehensweise: Erstellen einer klassischen COM-Komponente](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
 Zeigt, wie die Windows Runtime C++ Template Library verwenden, um eine grundlegende COM-Komponente und eine einfache Methode zur Registrierung und Nutzung der COM-Komponente aus einer desktop-app zu erstellen.  
  
 [Vorgehensweise: Direktes Instanziieren von WRL-Komponenten](../windows/how-to-instantiate-wrl-components-directly.md)  
 Informationen zum Verwenden der [Microsoft::WRL::Make](../windows/make-function.md) und [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) Funktionen, um eine Komponente aus dem Modul instanziieren, das sie definiert.  
  
 [Vorgehensweise: Verwenden von winmdidl.exe und midlrt.exe zum Erstellen von .h-Dateien aus Windows-Metadaten](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
 Zeigt, wie benutzerdefinierte Komponenten für Windows-Runtime von WRL durch Erstellen einer IDL-Datei von den WINMD-Metadaten verarbeitet werden.  
  
 [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 Zeigt, wie die [IXMLHTTPRequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908) und [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) Schnittstellen zusammen mit Aufgaben für HTTP GET und POST-Anforderungen an einen Webdienst in einer universellen Windows-Plattform-app zu senden.  
  
 [Beispiel des Reise-Optimierer von Bing Maps](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
 Verwendet die `HttpRequest` in definierten Klasse [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) im Rahmen einer vollständigen universelle Windows-Plattform-app.  
  
 [Erstellen eine Windows-Runtime-DLL-Komponente mit C++-Beispiel](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
 Zeigt, wie die Windows Runtime C++ Template Library eine prozessinterne DLL-Komponente erstellen und nutzen ihn von C + c++ / CX, JavaScript und c#.  
  
 [DirectX-Beispiel eines murmellabyrinthspiels](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
 Veranschaulicht, wie die Windows Runtime C++ Template Library zu verwenden, um die Lebensdauer von COM-Komponenten wie DirectX und Media Foundation im Rahmen eines vollständigen 3D-Spiels verwalten.  
  
 [Senden von toastbenachrichtigungen aus desktop-apps-Beispiel](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
 Veranschaulicht, wie die Windows Runtime C++ Template Library, die zum Arbeiten mit toastbenachrichtigungen aus einer desktop-app verwenden.  
  
## <a name="windows-runtime-c-template-library-compared-to-atl"></a>Windows Runtime C++ Template Library, die im Vergleich mit ATL  
 Windows Runtime C++ Template Library ähnelt der Active Template Library (ATL), da es verwenden zu können, um kleine, schnelle COM-Objekte erstellen. Windows Runtime C++ Template Library und ATL-Konzepte, wie die Definition von Objekten in Modulen, die explizite Registrierung von Schnittstellen, freigeben und offene Erstellung von Objekten durch Factorys. Sie können in den mit Windows Runtime C++ Template Library vertraut sein, wenn Sie mit ATL vertraut sind.  
  
 Windows Runtime C++ Template Library unterstützt die COM-Funktionalität, die für die universelle Windows-Plattform-apps erforderlich ist. Daher unterscheidet sie sich von ATL, da die direkte Unterstützung für COM-Funktionen wie Folgende fehlt:  
  
-   Aggregation  
  
-   vordefinierte Implementierungen  
  
-   duale Schnittstellen (`IDispatch`)  
  
-   Standardenumeratorschnittstellen  
  
-   Verbindungspunkte  
  
-   abtrennbare Schnittstellen  
  
-   OLE-Einbettung  
  
-   ActiveX-Steuerelemente  
  
-   COM+  
  
## <a name="concepts"></a>Konzepte  
 Windows Runtime C++ Template Library enthält Typen, die einige grundlegende Konzepte darstellen. Im folgenden Abschnitt werden diese Typen beschrieben.  
  
### <a name="comptr"></a>ComPtr  
 [ComPtr](../windows/comptr-class.md) ist ein *intelligenten Zeiger* Typ, der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. Mit `ComPtr` deklarieren Sie eine Variable, die auf die Member eines Objekts zugreifen kann, das von der Schnittstelle abgeleitet wird. `ComPtr` verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf null geht.  
  
### <a name="runtimeclass"></a>RuntimeClass  
 [RuntimeClass](../windows/runtimeclass-class.md) stellt eine instanziierte Klasse, die einen Satz angegebener Schnittstellen erbt. Ein `RuntimeClass` Objekt kann eine Kombination von Unterstützung für eine oder mehrere Windows-Runtime-COM-Schnittstellen oder einen schwachen Verweis auf eine Komponente bereitstellen.  
  
### <a name="module"></a>Modul  
 [Modul](../windows/module-class.md) stellt eine Auflistung von zugehörigen Objekten dar. Ein `Module` -Objekt verwaltet Klassenfactorys, die Objekte erstellen, und die Registrierung, die anderen Anwendungen die Verwendung eines Objekts ermöglicht.  
  
### <a name="callback"></a>Rückruf  
 Die [Rückruf](../windows/callback-function-windows-runtime-cpp-template-library.md) -Funktion erstellt ein Objekt, dessen Memberfunktion ein Ereignishandler (eine Rückrufmethode). Mit der `Callback` -Funktion schreiben Sie asynchrone Operationen.  
  
### <a name="eventsource"></a>EventSource  
 [EventSource](../windows/eventsource-class.md) dient zum Verwalten von *Delegieren* Ereignishandler. Windows Runtime C++ Template Library verwenden, um einen Delegaten implementieren, und mit `EventSource` hinzufügen, entfernen und Aufrufen von Delegaten.  
  
### <a name="asyncbase"></a>AsyncBase  
 [AsyncBase](../windows/asyncbase-class.md) stellt virtuelle Methoden, die das asynchrone Programmiermodell für Windows-Runtime darstellen. Überschreiben Sie die Member in dieser Klasse, um eine benutzerdefinierte Klasse zu erstellen, die einen asynchronen Vorgang starten, beenden oder seinen Fortschritt überprüfen kann.  
  
### <a name="ftmbase"></a>FtmBase  
 [FtmBase](../windows/ftmbase-class.md) stellt ein Freethread-Marshaller-Objekt dar. `FtmBase` erstellt eine globale Schnittstellentabelle (GIT) und hilft bei der Verwaltung von Marshalling- und Proxyobjekten.  
  
### <a name="weakref"></a>WeakRef  
 [WeakRef](../windows/weakref-class.md) ist ein Typ von intelligenten Zeigers, darstellt eine *schwachen Verweis*, dem verweist auf ein Objekt, die möglicherweise nicht verfügbar. Ein `WeakRef` Objekt kann verwendet werden, durch die Windows-Runtime und nicht von klassischem COM.  
  
 Ein `WeakRef` -Objekt stellt in der Regel ein Objekt dar, dessen Vorhandensein von einem externen Thread oder einer externen Anwendung gesteuert wird. Beispielsweise kann ein `WeakRef` -Objekt auf ein Dateiobjekt verweisen. Wenn die Datei geöffnet ist, so ist `WeakRef` gültig, und die referenzierte Datei ist zugänglich. Wenn die Datei hingegen geschlossen ist, so ist `WeakRef` ungültig, und die Datei ist nicht zugänglich.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|||  
|-|-|  
|[Projektvorlage für Klassenbibliothek](../windows/wrl-class-library-project-template.md)|Beschreibt, wie auf die WRL-Klassenbibliotheksprojektvorlage zugegriffen wird. Mit dieser Vorlage können mit Visual Studio zum Erstellen von Windows-Runtime-Komponenten vereinfacht.|  
|[Schlüssel-APIs nach Kategorie](../windows/key-wrl-apis-by-category.md)|Hebt die primären Windows Runtime C++ Template Library-Typen, Funktionen und Makros.|  
|[Referenz](../windows/wrl-reference.md)|Enthält Referenzinformationen für die Windows Runtime C++ Template Library.|  
|[Kurzreferenz (Windows-Runtime und Visual C++)](http://go.microsoft.com/fwlink/p/?linkid=229180)|Beschreibt kurz die C + c++ / CX-Funktionen, die die Windows-Runtime unterstützt.|  
|[Verwenden von Windows-Runtime-Komponenten in Visual C++](http://go.microsoft.com/fwlink/p/?linkid=229155)|Zeigt, wie C + c++ / CX zum Erstellen einer grundlegenden Windows-Runtime-Komponente.|