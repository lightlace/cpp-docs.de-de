---
title: "Vorgehensweise: Abschließen asynchroner Vorgänge mit WRL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3b5ff1f5bd36c2cf834375ac0999db835b731284
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>Gewusst wie: Abschließen asynchroner Vorgänge mit WRL
Dieses Dokument wird gezeigt, wie der Windows Runtime C++ Template Library (WRL) verwenden, um asynchrone Vorgänge starten und Arbeiten ausführen, wenn die Vorgänge abgeschlossen werden.  
  
 Dieses Dokument enthält zwei Beispiele. Im ersten Beispiel wird ein asynchroner Timer gestartet und gewartet, bis der Timer abläuft. In diesem Beispiel geben Sie die asynchrone Aktion an, wenn Sie das timer-Objekt erstellen. Im zweiten Beispiel wird ein Hintergrundarbeitsthread ausgeführt. In diesem Beispiel wird gezeigt, wie zum Arbeiten mit einer Windows-Runtime-Methode, die gibt eine `IAsyncInfo` Schnittstelle. Die [Rückruf](../windows/callback-function-windows-runtime-cpp-template-library.md) Funktion ist ein wichtiger Bestandteil der Beispiele, da sie einen Ereignishandler zur Verarbeitung der Ergebnisse der asynchronen Vorgänge angeben können.  
  
 Eine weitere grundlegende Beispiel erstellt eine Instanz einer Komponente und ruft einen Eigenschaftswert ab, finden Sie unter [Vorgehensweise: Aktivieren und verwenden Sie eine Windows-Runtime-Komponente](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
> [!TIP]
>  In diesem Beispiele werden die Rückrufe mithilfe von Lambdaausdrücken definiert. Außerdem können Sie Funktionsobjekte (Funktionselemente), Funktionszeiger oder [Std:: Function](../standard-library/function-class.md) Objekte. Weitere Informationen zu C++-Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke](../cpp/lambda-expressions-in-cpp.md).  
  
## <a name="example-working-with-a-timer"></a>Beispiel: Arbeiten mit einem Timer  
 Mit den folgenden Schritten wird ein asynchroner Timer und gestartet und gewartet, bis der Timer abläuft. Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!WARNING]
>  Obwohl Sie in der Regel die Windows Runtime C++ Template Library in einer app (Universelle Windows Plattform) verwenden, wird in diesem Beispiel eine Konsolen-app zur Veranschaulichung verwendet. Funktionen wie `wprintf_s` stehen nicht aus einer uwp-app. Weitere Informationen zu den Typen und Funktionen, die Sie in einer uwp-app verwenden können, finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) und [Win32 und COM für uwp-apps](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
1.  Einschließen (`#include`) alle erforderlichen Windows-Runtime, C++-Vorlagenbibliothek für Windows-Runtime oder C++-Standardbibliothek-Header.  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     Windows.System.Threading.h deklariert die Typen, die zur Verwendung eines asynchronen Timers benötigt werden.  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`-Direktive in der CPP-Datei verständlicher zu gestalten.  
  
2.  Windows-Runtime zu initialisieren.  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  Erstellen Sie eine Aktivierungsfactory für die `ABI::Windows::System::Threading::IThreadPoolTimer`-Schnittstelle.  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     Windows-Runtime verwendet den vollqualifizierten Namen zum Identifizieren von Typen. Die `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` Parameter ist eine Zeichenfolge, die vom Windows-Runtime bereitgestellt wird und den erforderlichen ablaufklassennamen enthält.  
  
4.  Erstellen einer [Ereignis](../windows/event-class-windows-runtime-cpp-template-library.md) -Objekt, das den Zeitgeberrückruf zur Haupt-app synchronisiert.  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen-App. In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird. In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.  
  
5.  Erstellen Sie ein `IThreadPoolTimer`-Objekt, das nach zwei Sekunden abläuft. Erstellen Sie mit der `Callback`-Funktion den Ereignishandler (ein `ABI::Windows::System::Threading::ITimerElapsedHandler`-Objekt).  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  Drucken Sie eine Meldung an die Konsole, und warten Sie, bis der Timerrückruf abgeschlossen ist. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-async.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe wrl-consume-async.cpp runtimeobject.lib**  
  
## <a name="example-working-with-a-background-thread"></a>Beispiel: Arbeiten mit einem Hintergrundthread  
 Mit den folgenden Schritten starten Sie einen Arbeitsthread und definieren die Aktion, die von diesem Thread ausgeführt wird. Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!TIP]
>  In diesem Beispiel wird gezeigt, wie Sie mit der `ABI::Windows::Foundation::IAsyncAction`-Schnittstelle arbeiten. Sie können dieses Muster für jede Schnittstelle anwenden, die `IAsyncInfo` implementiert: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation` und `IAsyncOperationWithProgress`.  
  
1.  Einschließen (`#include`) alle erforderlichen Windows-Runtime, C++-Vorlagenbibliothek für Windows-Runtime oder C++-Standardbibliothek-Header.  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     Windows.System.Threading.h deklariert die Typen, die zur Verwendung eines Arbeitsthreads benötigt werden.  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`-Direktive in der CPP-Datei verständlicher zu gestalten.  
  
2.  Windows-Runtime zu initialisieren.  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  Erstellen Sie eine Aktivierungsfactory für die `ABI::Windows::System::Threading::IThreadPoolStatics`-Schnittstelle.  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  Erstellen einer [Ereignis](../windows/event-class-windows-runtime-cpp-template-library.md) , Abschluss des Arbeitsthreads zur Haupt-app synchronisiert.  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen-App. In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird. In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.  
  
5.  Rufen Sie die `IThreadPoolStatics::RunAsync`-Methode auf, um einen Arbeitsthread zu erstellen. Definieren Sie mit der `Callback`-Funktion die Aktion.  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     Die `IsPrime`-Funktion wird im folgenden vollständigen Beispiel definiert.  
  
6.  Drucken Sie eine Meldung an die Konsole, und warten Sie, bis der Thread abgeschlossen ist. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-asyncOp.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe wrl-consume-asyncOp.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Vorlagenbibliothek für Windows-Runtime (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)
