---
title: "Gewusst wie: Erstellen einer klassischen COM-Komponente mit WRL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen einer klassischen COM-Komponente mit WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) verwenden, um grundlegende klassische COM-Komponenten für die Verwendung in Desktop-Apps zu erstellen; für die zusätzliche Verwendung für [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] Apps. Für die Erstellung von COM-Komponenten; die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] erfordern weniger Code als das ATL. Informationen über die Teilmenge von COM, die [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] unterstützt, finden Sie unter [Windows Runtime C++-Vorlagenbibliothek (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
 Dieses Dokument zeigt, wie Sie mit der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] eine grundlegende COM-Komponente erstellen. Obwohl Sie den Bereitstellungsmechanismus, der für Ihre Anforderungen am besten geeignet ist, verwenden können, zeigt dieses Dokument auch eine einfache Möglichkeit zur Registrierung und Nutzung der COM-Komponente aus einer Desktop-App.  
  
### <a name="to-use-the-includecppwrlshorttokencppwrlshortmdmd-to-create-a-basic-classic-com-component"></a>Erstellen der [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)], um eine grundlegende COM-Komponente zu erstellen.  
  
1.  Erstellen Sie in Visual Studio eine **leere Projektmappe** Projekt. Nennen Sie das Projekt, z. B. `WRLClassicCOM`.  
  
2.  Hinzufügen einer **Win32-Projekt** der Projektmappe. Nennen Sie das Projekt, z. B. `CalculatorComponent`. Auf der **Anwendungseinstellungen** Registerkarte **DLL**.  
  
3.  Hinzufügen einer **Midl-Datei (.idl)** Datei in das Projekt. Benennen Sie die Datei, z. B. `CalculatorComponent.idl`.  
  
4.  Fügen Sie diesen Code zu CalculatorComponent.idl hinzu:  
  
     [!CODE [wrl-classic-com-component#1](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#1)]  
  
5.  Definieren Sie die `CalculatorComponent` Klasse in CalculatorComponent.cpp. Die `CalculatorComponent` Klasse erbt von [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md). [Microsoft::wrl::RuntimeClassFlags \< ClassicCom>](../windows/runtimeclassflags-structure.md) Gibt an, dass die Klasse abgeleitet [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx) und nicht [IInspectable](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx). (`IInspectable` steht nur für [!INCLUDE[win8_appstore_short](../windows/includes/win8_appstore_short_md.md)] app Komponenten.) `CoCreatableClass` erstellt eine Factory für die Klasse, die mit Funktionen wie z. B. verwendet werden kann [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx).  
  
     [!CODE [wrl-classic-com-component#2](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#2)]  
  
6.  Ersetzen Sie den Code durch den folgenden Code in dllmain.cpp. Diese Datei definiert die DLL-Exportfunktionen. Diese Funktionen verwenden die [Microsoft::WRL::Module](../windows/module-class.md) Klasse Klassenfactorys für das Modul zu verwalten.  
  
     [!CODE [wrl-classic-com-component#3](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#3)]  
  
7.  Hinzufügen einer **Moduldefinitionsdatei (.def)** Datei in das Projekt. Benennen Sie die Datei, z. B. `CalculatorComponent.def`. Diese Datei gibt dem Linker die Namen der zu exportierenden Funktionen.  
  
8.  Fügen Sie diesen Code zu CalculatorComponent.def hinzu:  
  
     [!CODE [wrl-classic-com-component#4](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#4)]  
  
9. Der Linker-Befehlszeile runtimeobject.lib hinzufügen. Informationen hierzu finden Sie unter [. LIB-Dateien als Linkereingabe](../build/reference/dot-lib-files-as-linker-input.md).  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Nutzen Sie die COM-Komponente aus einer Desktop-App.  
  
1.  Registrieren Sie die COM-Komponente mit der Windows-Registrierung. Dazu erstellen Sie eine Datei für Registrierungseinträge, nennen Sie sie `RegScript.reg`, und fügen Sie den folgenden Text hinzu. Ersetzen Sie *\< Dll-Pfad >* durch den Pfad der DLL, z. B. `C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`.  
  
     [!CODE [wrl-classic-com-component#5](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#5)]  
  
2.  RegScript.reg ausführen oder Ihrem Projekts hinzufügen **Postbuildereignis**. Weitere Informationen finden Sie unter [Pre-Build Event/Post-build Event Command Line Dialog Box](../Topic/Pre-build%20Event-Post-build%20Event%20Command%20Line%20Dialog%20Box.md).  
  
3.  Hinzufügen einer **Win32-Konsolenanwendung** Projekt der Projektmappe. Nennen Sie das Projekt, z. B. `Calculator`.  
  
4.  Verwenden Sie diesen Code, um den Inhalt des Calculator.cpp zu ersetzen:  
  
     [!CODE [wrl-classic-com-component#6](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#6)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Dieses Dokument verwendet die Standard-COM-Funktionen, um zu veranschaulichen, dass Sie [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] verwenden können, um eine COM-Komponente zu erstellen und sie einer beliebigen COM-aktivierten Technologie zur Verfügung zu stellen. Sie können auch [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] Typen wie [Microsoft::WRL::ComPtr](../windows/comptr-class.md) in Ihrer desktop-app zum Verwalten der Lebensdauer von COM und anderen Objekten. Der folgende code verwendet [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] zum Verwalten der Lebensdauer von `ICalculatorComponent` Zeiger. Die `CoInitializeWrapper` Klasse ist ein RAII-Wrapper, der sicherstellt, dass die COM-Bibliothek freigegeben wird und dass die Lebensdauer der COM-Bibliothek länger ist als die vom `ComPtr` intelligenten Zeiger-Objekt.  
  
 [!CODE [wrl-classic-com-component#7](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#7)]  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Runtime C++-Vorlagenbibliothek (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)