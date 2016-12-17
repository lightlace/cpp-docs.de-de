---
title: "Gewusst wie: Abschlie&#223;en asynchroner Vorg&#228;nge mit WRL"
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
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abschlie&#223;en asynchroner Vorg&#228;nge mit WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird gezeigt, wie Sie mit [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) asynchrone Vorgänge starten und Arbeiten ausführen, wenn die Vorgänge abgeschlossen sind.  
  
 Dieses Dokument enthält zwei Beispiele.  Im ersten Beispiel wird ein asynchroner Zeitgeber gestartet und gewartet, bis der Zeitgeber abläuft.  In diesem Beispiel geben Sie die asynchrone Aktion an, wenn Sie das timer\-Objekt erstellen.  Im zweiten Beispiel wird ein Hintergrundarbeitsthread ausgeführt.  In diesem Beispiel wird gezeigt, wie Sie mit einer [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Methode arbeiten, die eine `IAsyncInfo`\-Schnittstelle zurückgibt.  Die [Rückruffunktion](../windows/callback-function-windows-runtime-cpp-template-library.md) ist ein wichtiger Bestandteil der Beispiele, da damit ein Ereignishandler angegeben werden kann, mit dem die Ergebnisse der asynchronen Operation verarbeitet werden.  
  
 Ein einfacheres Beispiel, in dem eine Instanz der Komponente erstellt und ein Eigenschaftswert abgerufen wird, finden Sie unter [Gewusst wie: Aktivieren und Verwenden einer Windows\-Runtime\-Komponente](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
> [!TIP]
>  In diesem Beispiele werden die Rückrufe mithilfe von Lambda\-Ausdrücken definiert.  Außerdem können Sie Funktionsobjekte \(Funktionselemente\), Funktionszeiger oder [std::function](../standard-library/function-class.md)\-Objekte verwenden.  Weitere Informationen zu C\+\+\-Lambdaausdrücken finden Sie unter [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md).  
  
## Beispiel: Arbeiten mit einem Zeitgeber  
 Mit den folgenden Schritten wird ein asynchroner Zeitgeber und gestartet und gewartet, bis der Zeitgeber abläuft.  Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!WARNING]
>  In der Regel verwenden Sie [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App; in diesem Beispiel wird jedoch zur Veranschaulichung eine Konsolen\-App verwendet.  Funktionen wie `wprintf_s` sind von einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App aus nicht verfügbar.  Weitere Informationen über die Typen und Funktionen, die Sie in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App verwenden können, finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) und im Thema zu [Win32 und COM für Windows Store\-Apps](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  Schließen Sie \(mit `#include`\) alle erforderlichen [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\- oder Standard\-C\+\+\-Bibliotheksheader ein.  
  
     [!CODE [wrl-consume-async#2](../CodeSnippet/VS_Snippets_Misc/wrl-consume-async#2)]  
  
     Windows.System.Threading.h deklariert die Typen, die zur Verwendung eines asynchronen Zeitgebers benötigt werden.  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`\-Direktive in der CPP\-Datei verständlicher zu gestalten.  
  
2.  Initialisieren Sie die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!CODE [wrl-consume-async#3](../CodeSnippet/VS_Snippets_Misc/wrl-consume-async#3)]  
  
3.  Erstellen Sie eine Aktivierungsfactory für die `ABI::Windows::System::Threading::IThreadPoolTimer`\-Schnittstelle.  
  
     [!CODE [wrl-consume-async#4](../CodeSnippet/VS_Snippets_Misc/wrl-consume-async#4)]  
  
     Die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] identifiziert Typen anhand von voll qualifizierten Namen.  Der Parameter `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` ist eine Zeichenfolge, die von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] bereitgestellt wird und den erforderlichen Ablaufklassennamen enthält.  
  
4.  Erstellen Sie ein [Ereignisobjekt](../windows/event-class-windows-runtime-cpp-template-library.md), das den Zeitgeberrückruf zur Haupt\-App synchronisiert.  
  
     [!CODE [wrl-consume-async#5](../CodeSnippet/VS_Snippets_Misc/wrl-consume-async#5)]  
  
    > [!NOTE]
    >  Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen\-App.  In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird.  In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.  
  
5.  Erstellen Sie ein `IThreadPoolTimer`\-Objekt, das nach zwei Sekunden abläuft.  Erstellen Sie mit der `Callback`\-Funktion den Ereignishandler \(ein `ABI::Windows::System::Threading::ITimerElapsedHandler`\-Objekt\).  
  
     [!CODE [wrl-consume-async#6](../CodeSnippet/VS_Snippets_Misc/wrl-consume-async#6)]  
  
6.  Drucken Sie eine Meldung an die Konsole, und warten Sie, bis der Zeitgeberrückruf abgeschlossen ist.  Alle `ComPtr`\- und RAII\-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!CODE [wrl-consume-async#7](../CodeSnippet/VS_Snippets_Misc/wrl-consume-async#7)]  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!CODE [wrl-consume-async#1](../CodeSnippet/VS_Snippets_Misc/wrl-consume-async#1)]  
  
### Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-async.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe wrl\-consume\-async.cpp runtimeobject.lib**  
  
## Beispiel: Arbeiten mit einem Hintergrundthread  
 Mit den folgenden Schritten starten Sie einen Arbeitsthread und definieren die Aktion, die von diesem Thread ausgeführt wird.  Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!TIP]
>  In diesem Beispiel wird gezeigt, wie Sie mit der `ABI::Windows::Foundation::IAsyncAction`\-Schnittstelle arbeiten.  Sie können dieses Muster für jede Schnittstelle anwenden, die `IAsyncInfo` implementiert: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation` und `IAsyncOperationWithProgress`.  
  
1.  Schließen Sie \(mit `#include`\) alle erforderlichen [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\- oder Standard\-C\+\+\-Bibliotheksheader ein.  
  
     [!CODE [wrl-consume-asyncOp#2](../CodeSnippet/VS_Snippets_Misc/wrl-consume-asyncop#2)]  
  
     Windows.System.Threading.h deklariert die Typen, die zur Verwendung eines Arbeitsthreads benötigt werden.  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`\-Direktive in der CPP\-Datei verständlicher zu gestalten.  
  
2.  Initialisieren Sie die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!CODE [wrl-consume-asyncOp#3](../CodeSnippet/VS_Snippets_Misc/wrl-consume-asyncop#3)]  
  
3.  Erstellen Sie eine Aktivierungsfactory für die `ABI::Windows::System::Threading::IThreadPoolStatics`\-Schnittstelle.  
  
     [!CODE [wrl-consume-asyncOp#4](../CodeSnippet/VS_Snippets_Misc/wrl-consume-asyncop#4)]  
  
4.  Erstellen Sie ein [Ereignisobjekt](../windows/event-class-windows-runtime-cpp-template-library.md), das den Abschluss des Arbeitsthreads zur Haupt\-App synchronisiert.  
  
     [!CODE [wrl-consume-asyncOp#5](../CodeSnippet/VS_Snippets_Misc/wrl-consume-asyncop#5)]  
  
    > [!NOTE]
    >  Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen\-App.  In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird.  In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.  
  
5.  Rufen Sie die `IThreadPoolStatics::RunAsync`\-Methode auf, um einen Arbeitsthread zu erstellen.  Definieren Sie mit der `Callback`\-Funktion die Aktion.  
  
     [!CODE [wrl-consume-asyncOp#6](../CodeSnippet/VS_Snippets_Misc/wrl-consume-asyncop#6)]  
  
     Die `IsPrime`\-Funktion wird im folgenden vollständigen Beispiel definiert.  
  
6.  Drucken Sie eine Meldung an die Konsole, und warten Sie, bis der Thread abgeschlossen ist.  Alle `ComPtr`\- und RAII\-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!CODE [wrl-consume-asyncOp#7](../CodeSnippet/VS_Snippets_Misc/wrl-consume-asyncop#7)]  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!CODE [wrl-consume-asyncOp#1](../CodeSnippet/VS_Snippets_Misc/wrl-consume-asyncop#1)]  
  
### Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-asyncOp.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe wrl\-consume\-asyncOp.cpp runtimeobject.lib**  
  
## Siehe auch  
 [Windows Runtime C\+\+ Template Library \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)