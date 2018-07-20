---
title: 'Vorgehensweise: Behandeln von Ereignissen mit WRL | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3c1666d1c79414beddc5b5e3ccc03953c92e902
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881152"
---
# <a name="how-to-handle-events-using-wrl"></a>Gewusst wie: Behandeln von Ereignissen mit WRL
Dieses Dokument zeigt, wie die Windows Runtime C++ Template Library (WRL) zu abonnieren und Behandeln der Ereignisse von einem Windows-Runtime-Objekt.  
  
 Eine weitere grundlegende Beispiel erstellt eine Instanz dieser Komponente, und ruft einen Eigenschaftswert ab, finden Sie unter [Vorgehensweise: Aktivieren und verwenden Sie eine Windows-Runtime-Komponente](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## <a name="subscribing-to-and-handling-events"></a>Abonnieren und Behandeln von Ereignissen  
 Mit den folgenden Schritten starten Sie ein `ABI::Windows::System::Threading::IDeviceWatcher`-Objekt und überwachen den Fortschritt mit Ereignishandlern. Die `IDeviceWatcher`-Schnittstelle ermöglicht es Ihnen, Geräte asynchron oder im Hintergrund aufzulisten und benachrichtigt zu werden, wenn Geräte hinzugefügt, entfernt oder geändert werden. Die [Rückruf](../windows/callback-function-windows-runtime-cpp-template-library.md) Funktion ist ein wichtiger Teil dieses Beispiels, da es bei der Angabe von Ereignishandlern, die die Ergebnisse des Hintergrundvorgangs verarbeiten können. Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!WARNING]
>  Obwohl Sie die Windows Runtime C++ Template Library in einer universellen Windows-Plattform-app in der Regel verwenden, wird in diesem Beispiel eine Konsolen-app zur Veranschaulichung verwendet. Funktionen wie `wprintf_s` stehen nicht aus einer Uwp-app. Weitere Informationen zu den Typen und Funktionen, die Sie in einer universellen Windows-Plattform-app verwenden können, finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) und [Win32 und COM für uwp-apps](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
1.  Einschließen (`#include`) alle erforderlichen Windows-Runtime, C++-Vorlagenbibliothek für Windows-Runtime oder C++-Standardbibliothek-Header.  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     Windows.Devices.Enumeration.h deklariert die Typen, die zur Auflistung von Geräten erforderlich sind.  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`-Direktive in der CPP-Datei verständlicher zu gestalten.  
  
2.  Deklarieren Sie die lokalen Variablen für die App. In diesem Beispiel wird die Anzahl der aufgelisteten Geräte und Registrierungstoken abgelegt; dadurch kann später das Abonnement von Ereignissen gekündigt werden.  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  Windows-Runtime zu initialisieren.  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  Erstellen einer [Ereignis](../windows/event-class-windows-runtime-cpp-template-library.md) -Objekt, das den Abschluss des Enumerationsprozesses mit der Haupt-app synchronisiert.  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Dieses Ereignis dient lediglich zur Veranschaulichung im Rahmen der Konsolen-App. In diesem Beispiel sorgt das Ereignis dafür, dass ein asynchroner Vorgang abgeschlossen wird, bevor die App beendet wird. In den meisten Apps warten Sie in der Regel nicht auf den Abschluss asynchroner Vorgänge.  
  
5.  Erstellen Sie eine Aktivierungsfactory für die `IDeviceWatcher`-Schnittstelle.  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     Windows-Runtime verwendet den vollqualifizierten Namen zum Identifizieren von Typen. Die `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` Parameter ist eine Zeichenfolge, die vom Windows-Runtime bereitgestellt wird und den erforderlichen ablaufklassennamen enthält.  
  
6.  Erstellen Sie das `IDeviceWatcher`-Objekt.  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  Abonnieren Sie mit der `Callback`-Funktion die Ereignisse `Added`, `EnumerationCompleted` und `Stopped`.  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     Der Ereignishandler `Added` erhöht die Anzahl der aufgelisteten Geräte. Er beendet den Enumerationsprozess, nachdem zehn Geräte gefunden wurden.  
  
     Der Ereignishandler `Stopped` entfernt die Ereignishandler und legt das Abschlussereignis fest.  
  
     Der Ereignishandler `EnumerationCompleted` beendet den Enumerationsprozess. Dieses Ereignis wird behandelt, falls es einmal weniger als zehn Geräte gibt.  
  
    > [!TIP]
    >  Dieses Beispiel definiert die Rückrufe mithilfe eines Lambdaausdrucks. Außerdem können Sie Funktionsobjekte (Funktionselemente), Funktionszeiger oder [Std:: Function](../standard-library/function-class.md) Objekte. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../cpp/lambda-expressions-in-cpp.md).  
  
8.  Starten Sie den Enumerationsprozess.  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. Warten Sie, bis der Enumerationsprozess abgeschlossen ist, und drucken Sie dann eine Meldung aus. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-events.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe Wrl-consume-events.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Vorlagenbibliothek für Windows-Runtime (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)