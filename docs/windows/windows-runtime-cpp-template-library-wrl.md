---
title: "Windows Runtime C++ Template Library (WRL)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
caps.latest.revision: 32
caps.handback.revision: "32"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Runtime C++ Template Library (WRL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) ist eine Vorlagenbibliothek, die eine Low-Level-Methode für die Erstellung und Verwendung von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Komponenten bereitstellt.  
  
## <a name="benefits"></a>Vorteile  
 Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] erleichtert Ihnen die Implementierung und Nutzung von COM-Komponenten (Component Object Model). Sie stellt Verwaltungstechniken wie die Verweiszählung bereit, mit der die Lebensdauer der Objekte verwaltet wird, oder wie Tests von `HRESULT` -Werten, mit denen festgestellt wird, ob ein Vorgang erfolgreich war oder einen Fehler verursacht hat. Zur erfolgreichen Verwendung der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]müssen die folgenden Regeln und Techniken sorgfältig beachtet werden.  
  
 Die [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]) ist eine sprachbasierte High-Level Methode zur Verwendung von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Komponenten. Sowohl [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] als auch [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] vereinfachen die Verfassung von Code für die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] , da Verwaltungsaufgaben automatisch für Sie ausgeführt werden.  
  
 Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] und die [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] bieten unterschiedliche Vorteile. Nachfolgend sind einige Gründe aufgeführt, warum Sie die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] anstelle der [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] verwenden würden:  
  
-   Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] fügt nur wenig Abstraktion über die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]-ABI (Application Binary Interface) hinzu; so können Sie den zugrunde liegenden Code besser steuern und [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]-APIs besser erstellen oder nutzen.  
  
-   Die [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] stellt COM- `HRESULT`-Werte als Ausnahmen dar. Wenn Sie eine CodeBase geerbt haben, die COM verwendet, oder eine CodeBase, die keine Ausnahmen verwendet, ist die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] möglicherweise besser zur Arbeit mit der [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] geeignet, da keine Ausnahmen verwendet werden müssen.  
  
    > [!NOTE]
    >  Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] verwendet `HRESULT` -Werte und löst keine Ausnahmen aus. Außerdem verwendet die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] intelligente Zeiger und das RAII-Muster, um dafür zu sorgen, dass Objekte ordnungsgemäß zerstört werden, wenn der Anwendungscode eine Ausnahme auslöst. Weitere Informationen zu intelligenten Zeigern und RAII finden Sie unter [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md) und [Objekte eigenen Ressourcen (RAII)](../cpp/objects-own-resources-raii.md).  
  
-   Zweck und Entwurf der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] wurden durch die ATL (Active Template Library) angeregt, eine Gruppe vorlagenbasierter Visual C++-Klassen, die zur Vereinfachung der Programmierung von COM-Objekten dienen. Da die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]mithilfe von Standard-C++ umschließt, wird die Portierung und die Interaktion mit vielen vorhandenen in ATL geschriebenen COM-Komponenten in die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]erleichtert. Wenn Sie ATL bereits kennen, fällt Ihnen die Programmierung in der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] möglicherweise leichter.  
  
## <a name="getting-started"></a>Erste Schritte  
 Im Folgenden sind einige Ressourcen aufgeführt, die Ihnen beim schnellen Einstieg in die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] helfen.  
  
 [Die Windows-Runtime-Bibliothek (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
 In diesem Channel 9-Video erfahren Sie, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] leichter [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] -Apps schreiben und [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Komponenten erstellen und verwenden können.  
  
 [Gewusst wie: Aktivieren und verwenden Sie eine Windows-Runtime-Komponente](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
 Zeigt, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] initialisieren und eine [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Komponente aktivieren und verwenden.  
  
 [Gewusst wie: Abschließen asynchroner Vorgänge](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
 Zeigt, wie Sie mit [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] asynchrone Vorgänge starten und Arbeiten ausführen, wenn die Vorgänge abgeschlossen sind.  
  
 [Gewusst wie: Behandeln von Ereignissen](../windows/how-to-handle-events-using-wrl.md)  
 Zeigt, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] die Ereignisse eines [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Objekts abonnieren und behandeln.  
  
 [Exemplarische Vorgehensweise: Erstellen einer grundlegenden Windows-Runtime-Komponente](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)  
 Zeigt, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] eine grundlegende [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Komponente erstellen, die zwei Zahlen addiert. Veranschaulicht außerdem, wie Sie Ereignisse auslösen und die Komponente aus einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] -App verwenden, die mit JavaScript arbeitet.  
  
 [Exemplarische Vorgehensweise: Erstellen einer Windows Store-Apps mithilfe von WRL und Media Foundation](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
 Erfahren Sie, wie Sie eine [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] -App erstellen, die [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197)verwendet.  
  
 [Gewusst wie: Erstellen einer klassischen COM-Komponente](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
 Zeigt, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] eine einfache COM-Komponente und eine einfache Methode zur Registrierung und Nutzung der COM-Komponente aus einer Desktop-App erstellen.  
  
 [Gewusst wie: Direktes Instanziieren von WRL-Komponenten](../windows/how-to-instantiate-wrl-components-directly.md)  
 Erfahren Sie, wie Sie mit den Funktionen [Microsoft::WRL::Make](../windows/make-function.md) und [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) eine Komponente aus dem Modul instanziieren, das sie definiert.  
  
 [Gewusst wie: Verwenden von winmdidl.exe und midlrt.exe zum Erstellen von .h-Dateien aus Windows-Metadaten](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
 Zeigt, wie benutzerdefinierte Komponenten für Windows-Runtime von WRL durch Erstellen einer IDL-Datei von den WINMD-Metadaten verarbeitet werden.  
  
 [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 Zeigt, wie die [IXMLHTTPRequest2](assetId:///bbc11c4a-aecf-4d6d-8275-3e852e309908) - und [IXMLHTTPRequest2Callback](assetId:///aa4b3f4c-6e28-458b-be25-6cce8865fc71) -Schnittstellen zusammen mit Aufgaben für HTTP-GET- und POST-Anforderungen an einen Webdienst in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] -App verwendet werden.  
  
 [Bing Maps-Reise-Optimierer](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
 Verwendet die `HttpRequest` in definierten [Exemplarische Vorgehensweise: Herstellen einer Verbindung mithilfe von Aufgaben und XML-HTTP-Anforderungen](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) im Rahmen einer vollständigen [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] app.  
  
 [Erstellen eine Windows-Runtime-DLL-Komponente mit C++-Beispiel](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
 Zeigt, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] eine prozessinterne DLL-Komponente erstellen und sie von C++/CX, JavaScript und C# aus nutzen.  
  
 [DirectX-Beispiel eines murmellabyrinthspiels](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
 Veranschaulicht, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] die Lebensdauer von COM-Komponenten wie DirectX und Media Foundation im Rahmen eines vollständigen 3D-Spiels verwalten.  
  
 [Senden von toastbenachrichtigungen aus desktop-apps-Beispiel](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
 Veranschaulicht, wie Sie mithilfe der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] mit Toastbenachrichtigungen aus einer Desktop-App arbeiten.  
  
## <a name="includecppwrlshorttokencppwrlshortmdmd-compared-to-atl"></a>Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] im Vergleich mit ATL  
 Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] ähnelt der Active Template Library (ATL), da Sie mit ihr kleine, schnelle COM-Objekte erstellen können. [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] und ATL haben noch andere Konzepte gemeinsam, wie die Definition von Objekten in Modulen, die explizite Registrierung von Schnittstellen und die offene Erstellung von Objekten durch Factorys. Wenn Sie mit ATL vertraut sind, wird Ihnen auch die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] bekannt vorkommen.  
  
 Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] unterstützt die COM-Funktionalität, die für Apps für [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] erforderlich ist. Daher unterscheidet sie sich von ATL, da die direkte Unterstützung für COM-Funktionen wie Folgende fehlt:  
  
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
 Die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] stellt Typen bereit, die einige grundlegende Konzepte darstellen. Im folgenden Abschnitt werden diese Typen beschrieben.  
  
### <a name="comptr"></a>ComPtr  
 [ComPtr](../windows/comptr-class.md) ist ein Typ des *intelligenten Zeigermechanismus* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. Mit `ComPtr` deklarieren Sie eine Variable, die auf die Member eines Objekts zugreifen kann, das von der Schnittstelle abgeleitet wird. `ComPtr` verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf null geht.  
  
### <a name="runtimeclass"></a>RuntimeClass  
 [RuntimeClass](../windows/runtimeclass-class.md) stellt eine instanziierte Klasse dar, die einen Satz angegebener Schnittstellen erbt. Ein `RuntimeClass` -Objekt kann kombinierte Unterstützung für eine oder mehrere [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -COM-Schnittstellen oder einen schwachen Verweis auf eine Komponente bereitstellen.  
  
### <a name="module"></a>Modul  
 [Module](../windows/module-class.md) stellt eine Auflistung von zugehörigen Objekten dar. Ein `Module` -Objekt verwaltet Klassenfactorys, die Objekte erstellen, und die Registrierung, die anderen Anwendungen die Verwendung eines Objekts ermöglicht.  
  
### <a name="callback"></a>Rückruf  
 Die [Rückruf](../windows/callback-function-windows-runtime-cpp-template-library.md) -Funktion erstellt ein Objekt, dessen Memberfunktion ein Ereignishandler ist (eine Rückrufmethode). Mit der `Callback` -Funktion schreiben Sie asynchrone Operationen.  
  
### <a name="eventsource"></a>EventSource  
 Mit[EventSource](../windows/eventsource-class.md) verwalten Sie *Delegat* -Ereignishandler. Mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] implementieren Sie einen Delegaten, und mit `EventSource` fügen Sie Delegaten hinzu, entfernen sie und rufen sie auf.  
  
### <a name="asyncbase"></a>AsyncBase  
 [AsyncBase](../windows/asyncbase-class.md) stellt virtuelle Methoden bereit, die das asynchrone Programmiermodell in der [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] darstellen. Überschreiben Sie die Member in dieser Klasse, um eine benutzerdefinierte Klasse zu erstellen, die einen asynchronen Vorgang starten, beenden oder seinen Fortschritt überprüfen kann.  
  
### <a name="ftmbase"></a>FtmBase  
 [FtmBase](../windows/ftmbase-class.md) stellt ein Freethread-Marshaller-Objekt dar. `FtmBase` erstellt eine globale Schnittstellentabelle (GIT) und hilft bei der Verwaltung von Marshalling- und Proxyobjekten.  
  
### <a name="weakref"></a>WeakRef  
 [WeakRef](../windows/weakref-class.md) ist ein Typ des intelligenten Zeigermechanismus, der einen *schwachen Verweis*auf ein Objekt darstellt, das möglicherweise zugänglich ist. Ein `WeakRef` -Objekt kann nur von der [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]und nicht von klassischem COM verwendet werden.  
  
 Ein `WeakRef` -Objekt stellt in der Regel ein Objekt dar, dessen Vorhandensein von einem externen Thread oder einer externen Anwendung gesteuert wird. Beispielsweise kann ein `WeakRef` -Objekt auf ein Dateiobjekt verweisen. Wenn die Datei geöffnet ist, so ist `WeakRef` gültig, und die referenzierte Datei ist zugänglich. Wenn die Datei hingegen geschlossen ist, so ist `WeakRef` ungültig, und die Datei ist nicht zugänglich.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|||  
|-|-|  
|[Projektvorlage für Klassenbibliothek](../windows/wrl-class-library-project-template.md)|Beschreibt, wie auf die WRL-Klassenbibliotheksprojektvorlage zugegriffen wird. Mit dieser Vorlage wird die Erstellung von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Komponenten mit Visual Studio vereinfacht.|  
|[Schlüssel-APIs nach Kategorie](../windows/key-wrl-apis-by-category.md)|Hebt die primären [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] -Typen, -Funktionen und -Makros hervor.|  
|[Referenz](../windows/wrl-reference.md)|Enthält Referenzinformationen für die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].|  
|[Kurzreferenz (Windows-Runtime und Visual C++)](http://go.microsoft.com/fwlink/?LinkId=229180)|Beschreibt kurz die [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] -Funktionen, die die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]unterstützen.|  
|[Verwenden von Windows-Runtime-Komponenten in Visual C++](http://go.microsoft.com/fwlink/?LinkId=229155)|Zeigt, wie Sie mit der [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] eine einfache [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Komponente erstellen.|