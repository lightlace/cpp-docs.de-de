---
title: 'Vorgehensweise: Behandeln von Ereignissen mit WRL'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: 959a85d6cf6de666ae56d09035acefe9a3828ae8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033176"
---
# <a name="how-to-handle-events-using-wrl"></a>Vorgehensweise: Behandeln von Ereignissen mit WRL

Dieses Dokument veranschaulicht, wie die Windows Runtime C++ Template Library (WRL) abonnieren und Behandeln der Ereignisse von einem Windows-Runtime-Objekt.

Ein einfacheres Beispiel, das eine Instanz dieser Komponente erstellt, und ein Eigenschaftswert abgerufen werden, finden Sie unter [Vorgehensweise: Aktivieren und Verwenden einer Windows-Runtime-Komponente](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

## <a name="subscribing-to-and-handling-events"></a>Abonnieren und Behandeln von Ereignissen

Mit den folgenden Schritten starten Sie ein `ABI::Windows::System::Threading::IDeviceWatcher`-Objekt und überwachen den Fortschritt mit Ereignishandlern. Die `IDeviceWatcher`-Schnittstelle ermöglicht es Ihnen, Geräte asynchron oder im Hintergrund aufzulisten und benachrichtigt zu werden, wenn Geräte hinzugefügt, entfernt oder geändert werden. Die [Rückruf](callback-function-wrl.md) Funktion ist ein wichtiger Teil dieses Beispiels aus, da sie Ereignishandler an, die die Ergebnisse des Hintergrundvorgangs verarbeiten können. Im Folgenden finden Sie das vollständige Beispiel.

> [!WARNING]
> Obwohl Sie in der Regel über die Windows Runtime C++ Template Library in einer universellen Windows-Plattform-app verwenden, wird von diesem Beispiel zur Veranschaulichung eine Konsolen-app verwendet. Funktionen wie `wprintf_s` sind nicht von einer universellen Windows-Plattform-app verfügbar. Weitere Informationen über die Typen und Funktionen, die Sie in einer universellen Windows-Plattform-app verwenden können, finden Sie unter [in apps der universellen Windows-Plattform nicht unterstützte CRT-Funktionen](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) und [Win32 und COM für UWP-apps](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

1. Enthalten (`#include`) alle erforderlichen Windows-Runtime, die Windows Runtime C++ Template Library und die Header der C++-Standardbibliothek.

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` deklariert die Typen, die zum Aufzählen von Geräten erforderlich sind.

   Es wird empfohlen, den Code mithilfe der `using namespace`-Direktive in der CPP-Datei verständlicher zu gestalten.

2. Deklarieren Sie die lokalen Variablen für die App. In diesem Beispiel wird die Anzahl der aufgelisteten Geräte und Registrierungstoken abgelegt; dadurch kann später das Abonnement von Ereignissen gekündigt werden.

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Initialisieren Sie die Windows-Runtime.

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. Erstellen Sie eine [Ereignis](event-class-wrl.md) -Objekt, das den Abschluss des Enumerationsprozesses mit der Haupt-app synchronisiert.

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen-App. In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird. In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.

5. Erstellen Sie eine Aktivierungsfactory für die `IDeviceWatcher`-Schnittstelle.

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Die Windows-Runtime verwendet den vollqualifizierten Namen, um Typen zu identifizieren. Die `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` Parameter ist eine Zeichenfolge, die von der Windows-Runtime bereitgestellt wird und den erforderlichen ablaufklassennamen enthält.

6. Erstellen Sie das `IDeviceWatcher`-Objekt.

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. Abonnieren Sie mit der `Callback`-Funktion die Ereignisse `Added`, `EnumerationCompleted` und `Stopped`.

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   Der Ereignishandler `Added` erhöht die Anzahl der aufgelisteten Geräte. Er beendet den Enumerationsprozess, nachdem zehn Geräte gefunden wurden.

   Der Ereignishandler `Stopped` entfernt die Ereignishandler und legt das Abschlussereignis fest.

   Der Ereignishandler `EnumerationCompleted` beendet den Enumerationsprozess. Dieses Ereignis wird behandelt, falls es einmal weniger als zehn Geräte gibt.

   > [!TIP]
   > Dieses Beispiel definiert die Rückrufe mithilfe eines Lambdaausdrucks. Sie können auch die Funktionsobjekte (Funktionselemente), Funktionszeiger, oder [Std:: Function](../../standard-library/function-class.md) Objekte. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../cpp/lambda-expressions-in-cpp.md).

8. Starten Sie den Enumerationsprozess.

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. Warten Sie, bis der Enumerationsprozess abgeschlossen ist, und drucken Sie dann eine Meldung aus. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

Im Folgenden sehen Sie das vollständige Beispiel:

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-events.cpp` und führen Sie dann den folgenden Befehl in einem **Visual Studio-Eingabeaufforderung** Fenster.

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>Siehe auch

[C++-Vorlagenbibliothek für Windows-Runtime (WRL)](windows-runtime-cpp-template-library-wrl.md)