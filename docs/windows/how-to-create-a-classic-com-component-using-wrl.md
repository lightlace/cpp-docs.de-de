---
title: 'Vorgehensweise: Erstellen einer klassischen COM-Komponente mit WRL | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c3d16cada621232c54176717f9bbdedb71a7e21
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083425"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Gewusst wie: Erstellen einer klassischen COM-Komponente mit WRL

Sie können die Windows Runtime C++ Template Library (WRL) verwenden, um grundlegende klassische COM-Komponenten für die Verwendung in desktop-apps, zusätzlich zur Verwendung für die apps der universellen Windows-Plattform (UWP) zu erstellen. Für die Erstellung von COM-Komponenten möglicherweise die Windows Runtime C++ Template Library weniger Code als das ATL. Informationen über die Teilmenge von COM, die die Windows Runtime C++ Template Library unterstützt, finden Sie unter [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

Dieses Dokument veranschaulicht, wie die Windows Runtime C++ Template Library verwenden, um eine grundlegende COM-Komponente zu erstellen. Obwohl Sie den Bereitstellungsmechanismus, der für Ihre Anforderungen am besten geeignet ist, verwenden können, zeigt dieses Dokument auch eine einfache Möglichkeit zur Registrierung und Nutzung der COM-Komponente aus einer Desktop-App.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Die Windows Runtime C++ Template Library verwenden, um eine grundlegende COM-Komponente zu erstellen.

1. Erstellen Sie in Visual Studio eine **leere Projektmappe** Projekt. Nennen Sie das Projekt, z. B. `WRLClassicCOM`.

2. Hinzufügen einer **Win32-Projekt** der Projektmappe. Nennen Sie das Projekt, z. B. `CalculatorComponent`. Auf der **Anwendungseinstellungen** Registerkarte **DLL**.

3. Hinzufügen einer **Midl-Datei (.idl)** Datei zum Projekt. Nennen Sie die Datei, z. B. `CalculatorComponent.idl`.

4. Fügen Sie diesen Code zu CalculatorComponent.idl hinzu:

   [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. Definieren Sie die `CalculatorComponent` Klasse in CalculatorComponent.cpp. Die `CalculatorComponent` Klasse erbt von [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md). [Microsoft::wrl::RuntimeClassFlags\<ClassicCom >](../windows/runtimeclassflags-structure.md) gibt an, dass die Klasse abgeleitet [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) und nicht ["iinspectable"](https://msdn.microsoft.com/library/br205821). (`IInspectable` ist nur für Windows-Runtime-app-Komponenten verfügbar.) `CoCreatableClass` erstellt eine Factory für die Klasse, die mit Funktionen wie z. B. verwendet werden kann [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

   [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. Verwenden Sie den folgenden Code ersetzen den Code in `dllmain.cpp`. Diese Datei definiert die DLL-Exportfunktionen. Diese Funktionen verwenden die [Microsoft::WRL::Module](../windows/module-class.md) Klasse, um die Klassenfactorys für das Modul zu verwalten.

   [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Hinzufügen einer **Moduldefinitionsdatei (.def)** Datei zum Projekt. Nennen Sie die Datei, z. B. `CalculatorComponent.def`. Diese Datei gibt dem Linker die Namen der zu exportierenden Funktionen.

8. Fügen Sie diesen Code zu CalculatorComponent.def hinzu:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Der Linker-Befehlszeile runtimeobject.lib hinzufügen. Informationen dazu finden Sie unter [. LIB-Dateien als Linkereingabe](../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Nutzen Sie die COM-Komponente aus einer Desktop-App.

1. Registrieren Sie die COM-Komponente mit der Windows-Registrierung. Zu diesem Zweck erstellen Sie eine Datei mit Registrierungseinträgen, nennen Sie es `RegScript.reg`, und fügen Sie den folgenden Text hinzu. Ersetzen Sie dies  *\<Dll-Pfad >* mit dem Pfad der DLL, z. B. `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`.

    ```
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}]
    @="CalculatorComponent Class"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\InprocServer32]
    @="<dll-path>"
    "ThreadingModel"="Apartment"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Programmable]

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\TypeLib]
    @="{9D3E6826-CB8E-4D86-8B14-89F0D7EFCD01}"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Version]
    @="1.0"
    ```

2. Regscript.reg auszuführen oder Hinzufügen Ihres Projekts **Postbuildereignis**. Weitere Informationen finden Sie unter [Pre-Build Event/Post-build über die Befehlszeile Dialogfeld](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).

3. Hinzufügen einer **Win32-Konsolenanwendung** Projekt der Projektmappe. Nennen Sie das Projekt, z. B. `Calculator`.

4. Verwenden Sie diesen Code ersetzt den Inhalt der `Calculator.cpp`:

   [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Stabile Programmierung

Dieses Dokument verwendet die standard-COM-Funktionen um zu veranschaulichen, dass Sie die Windows Runtime C++ Template Library verwenden können, erstellen eine COM-Komponente, und es alle COM-aktivierten Technologie zur Verfügung zu stellen. Sie können auch C++-Vorlagenbibliothek für Windows-Runtime-Typen verwenden, z. B. [Microsoft::WRL::ComPtr](../windows/comptr-class.md) in Ihrer desktop-app zum Verwalten der Lebensdauer von COM und anderen Objekten. Der folgende Code verwendet die Windows Runtime C++ Template Library, zum Verwalten der Lebensdauer von der `ICalculatorComponent` Zeiger. Die `CoInitializeWrapper` Klasse ist ein RAII-Wrapper, der sicherstellt, dass die COM-Bibliothek freigegeben wird und dass die Lebensdauer der COM-Bibliothek länger ist als die vom `ComPtr` intelligenten Zeiger-Objekt.

[!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>Siehe auch

[C++-Vorlagenbibliothek für Windows-Runtime (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)