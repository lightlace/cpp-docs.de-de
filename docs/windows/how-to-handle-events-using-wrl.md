---
title: "Gewusst wie: Behandeln von Ereignissen mit WRL"
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
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Behandeln von Ereignissen mit WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird gezeigt, wie Sie mit [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) die Ereignisse eines [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Objekts abonnieren und behandeln.  
  
 Ein einfacheres Beispiel, in dem eine Instanz der Komponente erstellt und ein Eigenschaftswert abgerufen wird, finden Sie unter [Gewusst wie: Aktivieren und Verwenden einer Windows\-Runtime\-Komponente](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## Abonnieren und Behandeln von Ereignissen  
 Mit den folgenden Schritten starten Sie ein `ABI::Windows::System::Threading::IDeviceWatcher`\-Objekt und überwachen den Fortschritt mit Ereignishandlern.  Die `IDeviceWatcher`\-Schnittstelle ermöglicht es Ihnen, Geräte asynchron oder im Hintergrund aufzulisten und benachrichtigt zu werden, wenn Geräte hinzugefügt, entfernt oder geändert werden.  Die [Callback](../windows/callback-function-windows-runtime-cpp-template-library.md)\-Funktion ist ein wichtiger Bestandteil dieses Beispiels, da sie die Angabe von Ereignishandlern ermöglicht, die die Ergebnisse des Hintergrundvorgangs verarbeiten.  Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!WARNING]
>  In der Regel verwenden Sie [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App; in diesem Beispiel wird jedoch zur Veranschaulichung eine Konsolen\-App verwendet.  Funktionen wie `wprintf_s` sind von einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App aus nicht verfügbar.  Weitere Informationen über die Typen und Funktionen, die Sie in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App verwenden können, finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) und im Thema zu [Win32 und COM für Windows Store\-Apps](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  Schließen Sie \(mit `#include`\) alle erforderlichen [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\- oder Standard\-C\+\+\-Bibliotheksheader ein.  
  
     [!CODE [wrl-consume-event#2](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#2)]  
  
     Windows.Devices.Enumeration.h deklariert die Typen, die zur Auflistung von Geräten erforderlich sind.  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`\-Direktive in der CPP\-Datei verständlicher zu gestalten.  
  
2.  Deklarieren Sie die lokalen Variablen für die App.  In diesem Beispiel wird die Anzahl der aufgelisteten Geräte und Registrierungstoken abgelegt; dadurch kann später das Abonnement von Ereignissen gekündigt werden.  
  
     [!CODE [wrl-consume-event#7](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#7)]  
  
3.  Initialisieren Sie die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!CODE [wrl-consume-event#3](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#3)]  
  
4.  Erstellen Sie ein [Event](../windows/event-class-windows-runtime-cpp-template-library.md)\-Objekt, das den Abschluss des Enumerationsprozesses mit der Haupt\-App synchronisiert.  
  
     [!CODE [wrl-consume-event#4](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#4)]  
  
    > [!NOTE]
    >  Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen\-App.  In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird.  In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.  
  
5.  Erstellen Sie eine Aktivierungsfactory für die `IDeviceWatcher`\-Schnittstelle.  
  
     [!CODE [wrl-consume-event#5](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#5)]  
  
     Die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] identifiziert Typen anhand von voll qualifizierten Namen.  Der Parameter `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` ist eine Zeichenfolge, die von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] bereitgestellt wird und den erforderlichen Ablaufklassennamen enthält.  
  
6.  Erstellen Sie das `IDeviceWatcher`\-Objekt.  
  
     [!CODE [wrl-consume-event#6](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#6)]  
  
7.  Abonnieren Sie mit der `Callback`\-Funktion die Ereignisse `Added`, `EnumerationCompleted` und `Stopped`.  
  
     [!CODE [wrl-consume-event#8](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#8)]  
  
     Der Ereignishandler `Added` erhöht die Anzahl der aufgelisteten Geräte.  Er beendet den Enumerationsprozess, nachdem zehn Geräte gefunden wurden.  
  
     Der Ereignishandler `Stopped` entfernt die Ereignishandler und legt das Abschlussereignis fest.  
  
     Der Ereignishandler `EnumerationCompleted` beendet den Enumerationsprozess.  Dieses Ereignis wird behandelt, falls es einmal weniger als zehn Geräte gibt.  
  
    > [!TIP]
    >  Dieses Beispiel definiert die Rückrufe mithilfe eines Lambda\-Ausdrucks.  Außerdem können Sie Funktionsobjekte \(Funktionselemente\), Funktionszeiger oder [std::function](../standard-library/function-class.md)\-Objekte verwenden.  Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md).  
  
8.  Starten Sie den Enumerationsprozess.  
  
     [!CODE [wrl-consume-event#9](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#9)]  
  
9. Warten Sie, bis der Enumerationsprozess abgeschlossen ist, und drucken Sie dann eine Meldung aus.  Alle `ComPtr`\- und RAII\-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!CODE [wrl-consume-event#10](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#10)]  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!CODE [wrl-consume-event#1](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#1)]  
  
## Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-events.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe wrl\-consume\-events.cpp runtimeobject.lib**  
  
## Siehe auch  
 [Windows Runtime C\+\+ Template Library \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)