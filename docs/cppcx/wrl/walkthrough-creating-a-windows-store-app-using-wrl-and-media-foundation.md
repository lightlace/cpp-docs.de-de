---
title: 'Exemplarische Vorgehensweise: Erstellen einer UWP-App mithilfe von WRL und Media Foundation'
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: ac2c16fb94646af7445d41010253967be126636a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498303"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>Exemplarische Vorgehensweise: Erstellen einer UWP-App mithilfe von WRL und Media Foundation

> [!NOTE]
> Für neue UWP-apps und-Komponenten empfiehlt sich die Verwendung [ C++von/WinRT](/windows/uwp/cpp-and-winrt-apis/), einer neuen standardmäßigen c++ 17-sprach Projektion für Windows-Runtime-APIs. C++/WinRT ist im Windows 10 SDK ab Version 1803 verfügbar. C++/WinRT wird vollständig in Header Dateien implementiert und wurde entwickelt, um Ihnen erstklassigen Zugriff auf die moderne Windows-API zu ermöglichen.

In diesem Tutorial erfahren Sie, wie Sie die Windows-Runtime C++ Template Library (WRL) verwenden, um eine universelle Windows-Plattform-app (UWP) zu erstellen, die [Microsoft Media Foundation](/windows/win32/medfound/microsoft-media-foundation-sdk)verwendet.

In diesem Beispiel wird eine benutzerdefinierte Media Foundation-Transformation erstellt, in der ein Graustufeneffekt auf Bilder angewendet wird, die über eine Webcam erfasst werden. Die App verwendet C++ zum Definieren der benutzerdefinierten Transformation und C# zum Verwenden der Komponente für das Transformieren der erfassten Bilder.

> [!NOTE]
> Anstelle von C# können Sie auch JavaScript, Visual Basic oder C++ verwenden, um die benutzerdefinierte Transformierenkomponente zu verwenden.

In den meisten Fällen können Sie/CX C++verwenden, um Windows-Runtime zu erstellen. Manchmal müssen Sie jedoch die WRL verwenden. Wenn Sie z. b. eine medienerweiterung für Microsoft Media Foundation erstellen, müssen Sie eine Komponente erstellen, die sowohl com-als auch Windows-Runtime Schnittstellen implementiert. Da C++/CX nur Windows-Runtime Objekte erstellen kann, müssen Sie zum Erstellen einer medienerweiterung das WRL verwenden, da es die Implementierung von com-und Windows-Runtime-Schnittstellen ermöglicht.

> [!NOTE]
> Auch wenn dieses Codebeispiel lang ist, stellt es das erforderliche Minimum dar, um eine nützliche Media Foundation-Transformation zu erstellen. Sie können es als Ausgangspunkt für Ihre eigene benutzerdefinierte Transformation verwenden. Dieses Beispiel wird aus dem Beispiel für [Medien Erweiterungen](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)angepasst, das Medien Erweiterungen zum Anwenden von Effekten auf Videos, zum Decodieren von Videos und zum Erstellen von Schema Handlern verwendet, die Mediendaten Ströme erzeugen.

## <a name="prerequisites"></a>Vorraussetzungen

- In Visual Studio 2017 und höher ist die UWP-Unterstützung eine optionale Komponente. Öffnen Sie die Visual Studio-Installer über das Windows-Startmenü, und suchen Sie nach ihrer Version von Visual Studio, um Sie zu installieren. Wählen Sie **ändern** aus, und vergewissern Sie sich, dass die Kachel **universelle Windows-Plattform Entwicklung** aktiviert ist. Über prüfen Sie  **C++ unter Optionale Komponenten die Tools für UWP (v141)** für Visual Studio 2017 oder  **C++ Tools für UWP (v142)** für Visual Studio 2019. Überprüfen Sie dann die Version der Windows SDK, die Sie verwenden möchten. 

- Die [Windows-Runtime](/uwp/api/).

- Erfahrungen mit COM.

- Eine Webcam.

## <a name="key-points"></a>Wesentliche Punkte

- Verwenden Sie zum Erstellen einer benutzerdefinierten Media Foundation-Komponente eine MIDL-Definitionsdatei (Microsoft Interface Definition Language) zum Definieren einer Schnittstelle, Implementieren dieser Schnittstelle und zum Einstellen derselben, dass sie aus anderen Komponenten aktiviert werden kann.

- Die `namespace` Attribute `runtimeclass` und und der `NTDDI_WIN8`Wert des [Versions](/windows/win32/Midl/version) Attributs sind wichtige Teile der Mittell-Definition für eine Media Foundation Komponente, die WRL verwendet.

- [Microsoft:: WRL:: runtimeclass](runtimeclass-class.md) ist die Basisklasse für die benutzerdefinierte Media Foundation Komponente. Der [Microsoft:: WRL:: runtimeclasstype:: winrtclassiccommix](runtimeclasstype-enumeration.md) -Enumerationswert, der als Vorlagen Argument bereitgestellt wird, kennzeichnet die-Klasse für die Verwendung als Windows-Runtime-Klasse und als klassische com-Lauf Zeit Klasse.

- Das [inspectableclass](inspectableclass-macro.md) -Makro implementiert grundlegende com-Funktionen wie die Verweis `QueryInterface` Zählung und die-Methode und legt den Lauf Zeit Klassennamen und die Vertrauens Ebene fest.

- Verwenden Sie die Microsoft:: WRL:[: Module-Klasse](module-class.md) , um DLL-Einstiegspunkt Funktionen zu implementieren, wie z. b. [dllgetactivationfactory](/windows/win32/winrt/functions), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)und [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject).

- Verknüpfen Sie die Komponenten-DLL mit „runtimeobject.lib“. Geben Sie auch [/WINMD](../../cppcx/compiler-and-linker-options-c-cx.md) in der Linker-Zeile an, um Windows-Metadaten zu generieren.

- Verwenden Sie Projekt Verweise, um WRL-Komponenten für UWP-apps zugänglich zu machen.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>So verwenden Sie die WRL zum Erstellen der Media Foundation Graustufen-Transformations Komponente

1. Erstellen Sie in Visual Studio ein **leeres** Projektmappenprojekt. Geben Sie dem Projekt einen Namen, z. b. *mediacapture*.

1. Fügen Sie der Projekt Mappe ein DLL-Projekt **(universelle Windows** -Projekt) hinzu. Nennen Sie das Projekt, z. b. *grayscaletransform*.

1. Fügen Sie dem Projekt eine Datei mit **mittlerer l-Datei (. idl)** hinzu. Nennen Sie die Datei, z. b. *grayscaletransform. idl*.

1. Fügen Sie den folgenden Code zu grayscaletransform. idl hinzu:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. Verwenden Sie den folgenden Code, um den Inhalt `pch.h`von zu ersetzen:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Fügen Sie dem Projekt eine neue Header Datei hinzu, benennen `BufferLock.h`Sie Sie, und ersetzen Sie dann den Inhalt durch den folgenden Code:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h`wird in diesem Beispiel nicht verwendet. Sie können ihn bei Bedarf aus dem Projekt entfernen.

1. Verwenden Sie den folgenden Code, um den Inhalt `GrayscaleTransform.cpp`von zu ersetzen:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Fügen Sie dem Projekt eine neue Modul Definitionsdatei hinzu, benennen Sie `GrayscaleTransform.def`Sie, und fügen Sie dann diesen Code hinzu:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. Verwenden Sie den folgenden Code, um den Inhalt `dllmain.cpp`von zu ersetzen:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. Legen Sie im Dialogfeld Eigenschaften **Seiten** des Projekts die folgenden **Linker** -Eigenschaften fest.

   1. Geben`GrayScaleTransform.def`Sie unter **Eingabe**für die **Modul Definitionsdatei**an.

   1. Fügen Sieaußerdem unter Eingabe `runtimeobject.lib`, `mfuuid.lib`und `mfplat.lib` der Eigenschaft **Zusätzliche Abhängigkeiten** hinzu.

   1. Legen Sie unter **Windows-Metadaten**die Einstellung **Windows-Metadaten generieren** auf **Ja (/WINMD)** fest.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>So verwenden Sie die benutzerdefinierte Media Foundation Komponente aus einer C# App

1. Fügen Sie der `MediaCapture` Projekt Mappe ein neues  **C# Projekt für eine leere app (Universal Windows)** hinzu. Geben Sie dem Projekt einen Namen, z. b. *mediacapture*.

1. Fügen Sie im **mediacapture** -Projekt einen Verweis auf das `GrayscaleTransform` Projekt hinzu. Weitere Informationen finden [Sie unter Gewusst wie: Hinzufügen und Entfernen von Verweisen mit dem Verweis-Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. Wählen `Package.appxmanifest`Sie in auf der Registerkarte **Funktionen** die Option **Mikrofon** und **Webcam**aus. Beide Funktionen sind erforderlich, um Fotos von der Webcam zu erfassen.

1. Fügen `MainPage.xaml`Sie in den folgenden Code zum root [Grid](/uwp/api/Windows.UI.Xaml.Controls.Grid) -Element hinzu:

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. Verwenden Sie den folgenden Code, um den Inhalt `MainPage.xaml.cs`von zu ersetzen:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

Die folgende Abbildung zeigt `MediaCapture app`.

![Mediacapture-APP, die ein Foto erfasst](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Nächste Schritte

Im Beispiel wird gezeigt, wie Fotos von der standardmäßigen Webcam nacheinander erfasst werden. Das [Beispiel für Medien Erweiterungen](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) bietet weitere Informationen. Es veranschaulicht die Aufzählung von Webcamgeräten und die Arbeit mit lokalen Schemahandlern, und es veranschaulicht zusätzliche Medieneffekte, die bei einzelnen Fotos und Videostreams funktionieren.

## <a name="see-also"></a>Siehe auch

[C++-Vorlagenbibliothek für Windows-Runtime (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Media Foundation](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[Beispiel für Medien Erweiterungen](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
