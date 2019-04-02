---
title: 'Vorgehensweise: Abschließen Sie asynchroner Vorgänge mit WRL'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
ms.openlocfilehash: 321bb273f661ec16fe85443c449b425ae56b99e3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785415"
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>Vorgehensweise: Abschließen Sie asynchroner Vorgänge mit WRL

Dieses Dokument veranschaulicht, wie die Windows Runtime C++ Template Library (WRL) verwenden, um asynchrone Vorgänge starten und Arbeiten ausführen, wenn die Vorgänge abgeschlossen.

Dieses Dokument enthält zwei Beispiele. Im ersten Beispiel wird ein asynchroner Timer gestartet und gewartet, bis der Timer abläuft. In diesem Beispiel geben Sie die asynchrone Aktion an, wenn Sie das Timer-Objekt erstellen. Im zweiten Beispiel wird ein Hintergrundarbeitsthread ausgeführt. Dieses Beispiel veranschaulicht die Arbeit mit einer Windows-Runtime-Methode, die gibt ein `IAsyncInfo` Schnittstelle. Die [Rückruf](callback-function-wrl.md) Funktion ist ein wichtiger Teil der Beispiele aus, da sie einen Ereignishandler zur Verarbeitung der Ergebnisse der asynchronen Vorgänge angeben können.

Ein einfacheres Beispiel, das eine Instanz einer Komponente erstellt, und ein Eigenschaftswert abgerufen werden, finden Sie unter [Vorgehensweise: Aktivieren und Verwenden einer Windows-Runtime-Komponente](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

> [!TIP]
> In diesem Beispiele werden die Rückrufe mithilfe von Lambdaausdrücken definiert. Sie können auch die Funktionsobjekte (Funktionselemente), Funktionszeiger, oder [Std:: Function](../../standard-library/function-class.md) Objekte. Weitere Informationen zu C++-Lambdaausdrücken finden Sie unter [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md).

## <a name="example-working-with-a-timer"></a>Beispiel: Arbeiten mit einem Timer

Mit den folgenden Schritten wird ein asynchroner Timer und gestartet und gewartet, bis der Timer abläuft. Im Folgenden finden Sie das vollständige Beispiel.

> [!WARNING]
> Obwohl Sie in der Regel über die Windows Runtime C++ Template Library in einer app für die universelle Windows-Plattform (UWP) verwenden, wird in diesem Beispiel eine Konsolen-app zur Veranschaulichung verwendet. Funktionen wie `wprintf_s` sind bei einer UWP-app nicht verfügbar. Weitere Informationen über die Typen und Funktionen, die Sie in einer UWP-app verwenden können, finden Sie unter [in apps der universellen Windows-Plattform nicht unterstützte CRT-Funktionen](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) und [Win32 und COM für UWP-apps](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

1. Enthalten (`#include`) alle erforderlichen Windows-Runtime, die Windows Runtime C++ Template Library und die Header der C++-Standardbibliothek.

   [!code-cpp[wrl-consume-async#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]

   `Windows.System.Threading.h` deklariert die Typen, die für die Verwendung eines asynchronen Timers erforderlich sind.

   Es wird empfohlen, den Code mithilfe der `using namespace`-Direktive in der CPP-Datei verständlicher zu gestalten.

2. Initialisieren Sie die Windows-Runtime.

   [!code-cpp[wrl-consume-async#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]

3. Erstellen Sie eine Aktivierungsfactory für die `ABI::Windows::System::Threading::IThreadPoolTimer`-Schnittstelle.

   [!code-cpp[wrl-consume-async#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]

   Die Windows-Runtime verwendet den vollqualifizierten Namen, um Typen zu identifizieren. Die `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` Parameter ist eine Zeichenfolge, die von der Windows-Runtime bereitgestellt wird und den erforderlichen ablaufklassennamen enthält.

4. Erstellen Sie eine [Ereignis](event-class-wrl.md) , das den timerrückruf zur Haupt-app synchronisiert.

   [!code-cpp[wrl-consume-async#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]

   > [!NOTE]
   > Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen-App. In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird. In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.

5. Erstellen Sie ein `IThreadPoolTimer`-Objekt, das nach zwei Sekunden abläuft. Erstellen Sie mit der `Callback`-Funktion den Ereignishandler (ein `ABI::Windows::System::Threading::ITimerElapsedHandler`-Objekt).

   [!code-cpp[wrl-consume-async#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]

6. Drucken Sie eine Meldung an die Konsole, und warten Sie, bis der Timerrückruf abgeschlossen ist. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.

   [!code-cpp[wrl-consume-async#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]

Im Folgenden sehen Sie das vollständige Beispiel:

[!code-cpp[wrl-consume-async#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]

### <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-async.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

`cl.exe wrl-consume-async.cpp runtimeobject.lib`

## <a name="example-working-with-a-background-thread"></a>Beispiel: Arbeiten mit einem Hintergrundthread

Mit den folgenden Schritten starten Sie einen Arbeitsthread und definieren die Aktion, die von diesem Thread ausgeführt wird. Im Folgenden finden Sie das vollständige Beispiel.

> [!TIP]
> In diesem Beispiel wird gezeigt, wie Sie mit der `ABI::Windows::Foundation::IAsyncAction`-Schnittstelle arbeiten. Sie können dieses Muster für jede Schnittstelle anwenden, die `IAsyncInfo` implementiert: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation` und `IAsyncOperationWithProgress`.

1. Enthalten (`#include`) alle erforderlichen Windows-Runtime, die Windows Runtime C++ Template Library und die Header der C++-Standardbibliothek.

   [!code-cpp[wrl-consume-asyncOp#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]

   Windows.System.Threading.h deklariert die Typen, die zur Verwendung eines Arbeitsthreads benötigt werden.

   Es wird empfohlen, den Code mithilfe der `using namespace`-Anweisung in der CPP-Datei verständlicher zu gestalten.

2. Initialisieren Sie die Windows-Runtime.

   [!code-cpp[wrl-consume-asyncOp#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]

3. Erstellen Sie eine Aktivierungsfactory für die `ABI::Windows::System::Threading::IThreadPoolStatics`-Schnittstelle.

   [!code-cpp[wrl-consume-asyncOp#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]

4. Erstellen Sie eine [Ereignis](event-class-wrl.md) -Objekt, das Abschluss des Arbeitsthreads zur Haupt-app synchronisiert.

   [!code-cpp[wrl-consume-asyncOp#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]

   > [!NOTE]
   > Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen-App. In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird. In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.

5. Rufen Sie die `IThreadPoolStatics::RunAsync`-Methode auf, um einen Arbeitsthread zu erstellen. Definieren Sie mit der `Callback`-Funktion die Aktion.

   [!code-cpp[wrl-consume-asyncOp#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]

   Die `IsPrime`-Funktion wird im folgenden vollständigen Beispiel definiert.

6. Drucken Sie eine Meldung an die Konsole, und warten Sie, bis der Thread abgeschlossen ist. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.

   [!code-cpp[wrl-consume-asyncOp#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]

Im Folgenden sehen Sie das vollständige Beispiel:

[!code-cpp[wrl-consume-asyncOp#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]

### <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-asyncOp.cpp` und führen Sie dann den folgenden Befehl in einem **Visual Studio-Eingabeaufforderung** Fenster.

`cl.exe wrl-consume-asyncOp.cpp runtimeobject.lib`

## <a name="see-also"></a>Siehe auch

[C++-Vorlagenbibliothek für Windows-Runtime (WRL)](windows-runtime-cpp-template-library-wrl.md)