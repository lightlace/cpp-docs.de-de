---
title: 'Exemplarische Vorgehensweise: Erstellen einer uwp-app mithilfe von WRL und Media Foundation | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c9e3f678a65b3dacfc5bba012656118b6fe2fa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891684"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>Exemplarische Vorgehensweise: Erstellen einer uwp-app mithilfe von WRL und Media Foundation
Erfahren Sie, wie die Windows Runtime C++ Template Library (WRL) zu verwenden, um eine app für die universelle Windows-Plattform (UWP) erstellen, verwendet [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 In diesem Beispiel wird eine benutzerdefinierte Media Foundation-Transformation erstellt, in der ein Graustufeneffekt auf Bilder angewendet wird, die über eine Webcam erfasst werden. Die App verwendet C++ zum Definieren der benutzerdefinierten Transformation und C# zum Verwenden der Komponente für das Transformieren der erfassten Bilder.  
  
> [!NOTE]
>  Anstelle von C# können Sie auch JavaScript, Visual Basic oder C++ verwenden, um die benutzerdefinierte Transformierenkomponente zu verwenden.  
  

 In den meisten Fällen können Sie C + c++ / CX zu Windows-Runtime erstellen). Allerdings müssen manchmal Sie die WRL verwenden. Beim Erstellen einer medienerweiterung für Microsoft Media Foundation müssen Sie z. B. eine Komponente erstellen, die sowohl COM-als auch Windows-Runtime-Schnittstellen implementiert. Da C + c++ / CX kann nur Windows-Runtime-Objekte erstellen, um eine medienerweiterung zu erstellen müssen Sie die WRL verwenden, da die Implementierung der COM- und Windows-Runtime-Schnittstellen können.  

  
> [!NOTE]
>  Auch wenn dieses Codebeispiel lang ist, stellt es das erforderliche Minimum dar, um eine nützliche Media Foundation-Transformation zu erstellen. Sie können es als Ausgangspunkt für Ihre eigene benutzerdefinierte Transformation verwenden. Dieses Beispiel stammt aus dem [medienerweiterungen](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096), medienerweiterungen verwendet anzuwendende Effekte auf Videos, Videos zu decodieren, und, die Medienstreams generieren schemahandler zu erstellen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   Erfahrung mit der [Windows-Runtime](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   Erfahrungen mit COM.  
  
-   Eine Webcam.  
  
## <a name="key-points"></a>Wesentliche Punkte  
  
-   Verwenden Sie zum Erstellen einer benutzerdefinierten Media Foundation-Komponente eine MIDL-Definitionsdatei (Microsoft Interface Definition Language) zum Definieren einer Schnittstelle, Implementieren dieser Schnittstelle und zum Einstellen derselben, dass sie aus anderen Komponenten aktiviert werden kann.  
  
-   Die `namespace` und `runtimeclass` Attribute, und die `NTDDI_WIN8` [Version](http://msdn.microsoft.com/en-us/66ac5cf3-2230-44fd-aaf6-8013e4a4ae81) Attributwert sind wichtige Bestandteile der MIDL-Definition für eine Media Foundation-Komponente, die WRL verwendet.  
  
-   [Microsoft::wrl::RuntimeClass](../windows/runtimeclass-class.md) ist die Basisklasse für die benutzerdefinierte Media Foundation-Komponente. Die [winrtclassiccommix](../windows/runtimeclasstype-enumeration.md) Enum-Wert, der als Vorlagenargument angegeben wird, markiert die Klasse für die Verwendung sowohl als Windows-Runtime-Klasse als eine klassische COM-Runtime-Klasse.  
  
-   Die [InspectableClass](../windows/inspectableclass-macro.md) -Makro implementiert grundlegende COM-Funktionen wie die verweiszählung und die `QueryInterface` -Methode, und legt die Common Language Runtime-Klassennamen und-Vertrauensstufe.  
  
-   Verwenden Sie die Microsoft:: wrl::[Modulklasse](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/b4acf5de-2f4c-4c8b-b5ff-9140d023ecbe/locales/en-US) DLL-Einstiegspunkt-Funktionen wie z. B. implementieren [DllGetActivationFactory](http://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368\(v=vs.85\).aspx), und [ DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/ms680760\(v=vs.85\).aspx).  
  
-   Verknüpfen Sie die Komponenten-DLL mit „runtimeobject.lib“. Geben Sie auch [/WINMD](../cppcx/compiler-and-linker-options-c-cx.md) in der Linkerzeile an Windows-Metadaten zu generieren.  
  
-   Verwenden Sie Projektverweise, auf die WRL-Komponenten uwp-apps zu ermöglichen.  
  
### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Verwendung der WRL zum Erstellen der Media Foundation Graustufen Transformationskomponente  
  
1.  Erstellen Sie in Visual Studio eine **leere Projektmappe** Projekt. Nennen Sie das Projekt, z. B. `MediaCapture`.  
  
2.  Hinzufügen einer **DLL (Uwp)** Projekt der Projektmappe. Nennen Sie das Projekt, z. B. `GrayscaleTransform`.  
  
3.  Hinzufügen einer **Midl-Datei (.idl)** Datei zum Projekt. Nennen Sie die Datei, z. B. `GrayscaleTransform.idl`.  
  
4.  Fügen Sie „GrayscaleTransform.idl“ diesen Code hinzu.  
  
     [!code-cpp[wrl-media-capture#1](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]  
  
5.  Verwenden Sie den folgenden Code, um die Inhalte von „pch.h“ zu ersetzen.  
  
     [!code-cpp[wrl-media-capture#2](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]  
  
6.  Fügen Sie dem Projekt eine neue Headerdatei, benennen Sie sie `BufferLock.h`, und fügen Sie diesen Code hinzu:  
  
     [!code-cpp[wrl-media-capture#3](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]  
  
7.  „GrayscaleTransform.h“ wird in diesem Beispiel nicht verwendet. Sie können ihn bei Bedarf aus dem Projekt entfernen.  
  
8.  Verwenden Sie den folgenden Code, um die Inhalte von „GrayscaleTransform.cpp“ zu ersetzen.  
  
     [!code-cpp[wrl-media-capture#4](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]  
  
9. Das Projekt eine neue Moduldefinitionsdatei hinzugefügt haben, nennen Sie sie `GrayscaleTransform.def`, und fügen Sie diesen Code hinzu:  
  
   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```   
  
10. Verwenden Sie den folgenden Code, um die Inhalte von „dllmain.cpp“ zu ersetzen.  
  
     [!code-cpp[wrl-media-capture#6](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]  
  
11. In des Projekts **Eigenschaftenseiten** Dialogfeld Feld, legen Sie den folgenden **Linker** Eigenschaften.  
  
    1.  Klicken Sie unter **Eingabe**, für die **Moduldefinitionsdatei**, geben Sie `GrayScaleTransform.def`.  
  
    2.  Auch unter **Eingabe**, hinzufügen `runtimeobject.lib`, `mfuuid.lib`, und `mfplatf.lib` auf die **zusätzliche Abhängigkeiten** Eigenschaft.  
  
    3.  Klicken Sie unter **Windows-Metadaten**legen **Windows-Metadaten generieren** auf **Ja (/ WINMD)**.  
  
### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Die WRL der benutzerdefinierten Media Foundation-Komponente aus einer C#-app verwenden  
  
1.  Fügen Sie einen neuen **c# leere App (XAML)** -Projekt auf die `MediaCapture` Lösung. Nennen Sie das Projekt, z. B. `MediaCapture`.  
  
2.  In der **MediaCapture** Projekt, fügen einen Verweis auf die `GrayscaleTransform` Projekt. Um weitere Informationen hierzu finden Sie unter [wie: Hinzufügen oder Entfernen von verweisen mithilfe des Verweis-Managers](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).  
  
3.  In "Package.appxmanifest" auf die **Funktionen** Registerkarte **Mikrofon** und **Webcam**. Beide Funktionen sind erforderlich, um Fotos von der Webcam zu erfassen.  
  
4.  Fügen Sie in "MainPage.xaml" diesen Code in das Stammverzeichnis [Raster](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) Element:  
  
     [!code-xml[wrl-media-capture#7](../windows/codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]  
  
5.  Verwenden Sie den folgenden Code zum Ersetzen der Inhalte von „MainPage.xaml.cs“.  
  
     [!code-cs[wrl-media-capture#8](../windows/codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]  
  
 In der folgenden Abbildung wird die MediaCapture-App veranschaulicht.  
  
 ![MediaCapture-app zeichnet ein Foto](../windows/media/wrl_media_capture.png "WRL_Media_Capture")  
  
## <a name="next-steps"></a>Nächste Schritte  
 Im Beispiel wird gezeigt, wie Fotos von der standardmäßigen Webcam nacheinander erfasst werden. Die [medienerweiterungen](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) finden Sie weitere. Es veranschaulicht die Aufzählung von Webcamgeräten und die Arbeit mit lokalen Schemahandlern, und es veranschaulicht zusätzliche Medieneffekte, die bei einzelnen Fotos und Videostreams funktionieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Runtime C++-Vorlagenbibliothek (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197)   
 [Beispiel für die medienerweiterungen](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)