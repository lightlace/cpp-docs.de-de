---
title: 'Vorgehensweise: Erstellen einer klassischen COM-Komponente mit WRL | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e33eaebd49343c5c03b097eaf75d4745c7aaeac1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Gewusst wie: Erstellen einer klassischen COM-Komponente mit WRL
Sie können Windows Runtime C++ Template Library (WRL) verwenden, um grundlegende klassische COM-Komponenten für die Verwendung in desktop-apps erstellen außerdem Verwendung für [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] apps. Für die Erstellung von COM-Komponenten möglicherweise die Windows Runtime C++ Template Library weniger Code als das ATL. Weitere Informationen über die Teilmenge von COM, die die Windows Runtime C++ Template Library unterstützt, finden Sie unter [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
 Dieses Dokument wird gezeigt, wie die Windows Runtime C++ Template Library verwenden, um eine grundlegende COM-Komponente zu erstellen. Obwohl Sie den Bereitstellungsmechanismus, der für Ihre Anforderungen am besten geeignet ist, verwenden können, zeigt dieses Dokument auch eine einfache Möglichkeit zur Registrierung und Nutzung der COM-Komponente aus einer Desktop-App.  
  
### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Windows Runtime C++ Template Library verwenden, um eine grundlegende COM-Komponente zu erstellen.  
  
1.  Erstellen Sie in Visual Studio eine **leere Projektmappe** Projekt. Nennen Sie das Projekt, z. B. `WRLClassicCOM`.  
  
2.  Hinzufügen einer **Win32-Projekt** der Projektmappe. Nennen Sie das Projekt, z. B. `CalculatorComponent`. Auf der **Anwendungseinstellungen** Registerkarte **DLL**.  
  
3.  Hinzufügen einer **Midl-Datei (.idl)** Datei zum Projekt. Nennen Sie die Datei, z. B. `CalculatorComponent.idl`.  
  
4.  Fügen Sie diesen Code zu CalculatorComponent.idl hinzu:  
  
     [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]  
  
5.  Definieren Sie die `CalculatorComponent` Klasse in CalculatorComponent.cpp. Die `CalculatorComponent` Klasse erbt von [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md). [Microsoft::wrl::RuntimeClassFlags\<ClassicCom >](../windows/runtimeclassflags-structure.md) gibt an, dass die Klasse abgeleitet [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx) und nicht ["iinspectable"](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx). (`IInspectable` steht nur [!INCLUDE[win8_appstore_short](../windows/includes/win8_appstore_short_md.md)] app-Komponenten.) `CoCreatableClass` erstellt eine Factory für die Klasse, die mit Funktionen wie z. B. verwendet werden kann [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx).  
  
     [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]  
  
6.  Ersetzen Sie den Code durch den folgenden Code in dllmain.cpp. Diese Datei definiert die DLL-Exportfunktionen. Verwenden Sie diese Funktionen die [Microsoft::WRL::Module](../windows/module-class.md) Klasse, um die Klassenfactorys für das Modul zu verwalten.  
  
     [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]  
  
7.  Hinzufügen einer **Moduldefinitionsdatei (.def)** Datei zum Projekt. Nennen Sie die Datei, z. B. `CalculatorComponent.def`. Diese Datei gibt dem Linker die Namen der zu exportierenden Funktionen.  
  
8.  Fügen Sie diesen Code zu CalculatorComponent.def hinzu:  
  
    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE  
    ```

9. Der Linker-Befehlszeile runtimeobject.lib hinzufügen. Um weitere Informationen hierzu finden Sie unter [. LIB-Dateien als Linkereingabe](../build/reference/dot-lib-files-as-linker-input.md).  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Nutzen Sie die COM-Komponente aus einer Desktop-App.  
  
1.  Registrieren Sie die COM-Komponente mit der Windows-Registrierung. Zu diesem Zweck erstellen Sie eine Datei mit Registrierungseinträgen, nennen Sie sie `RegScript.reg`, und fügen Sie den folgenden Text hinzu. Ersetzen Sie  *\<Dll-Pfad >* mit dem Pfad der DLL, z. B. `C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`.  
  
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
  
2.  Regscript.reg auszuführen oder ihn zu Ihrem Projekts hinzufügen **Postbuildereignis**. Weitere Informationen finden Sie unter [Präbuild Ereignis/Postbuildereignis-Ereignis Befehlszeile Dialogfeld](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).  
  
3.  Hinzufügen einer **Win32-Konsolenanwendung** Projekt der Projektmappe. Nennen Sie das Projekt, z. B. `Calculator`.  
  
4.  Verwenden Sie diesen Code, um den Inhalt des Calculator.cpp zu ersetzen:  
  
     [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Dieses Dokument verwendet die standard-COM-Funktionen um zu veranschaulichen, dass Sie die Windows Runtime C++ Template Library verwenden können, erstellen eine COM-Komponente und alle COM-aktivierten Technologie zur Verfügung zu stellen. Sie können auch C++-Vorlagenbibliothek für Windows-Runtime-Typen verwenden, z. B. [Microsoft::WRL::ComPtr](../windows/comptr-class.md) in Ihrer desktop-app zum Verwalten der Lebensdauer von COM und andere Objekte. Der folgende Code verwendet die Windows Runtime C++ Template Library, zum Verwalten der Lebensdauer von der `ICalculatorComponent` Zeiger. Die `CoInitializeWrapper` Klasse ist ein RAII-Wrapper, der sicherstellt, dass die COM-Bibliothek freigegeben wird und dass die Lebensdauer der COM-Bibliothek länger ist als die vom `ComPtr` intelligenten Zeiger-Objekt.  
  
 [!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Runtime C++-Vorlagenbibliothek (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)