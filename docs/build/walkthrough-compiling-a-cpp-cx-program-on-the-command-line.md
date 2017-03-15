---
title: "Exemplarische Vorgehensweise: Kompilieren eines C++/CX-Programms in der Befehlszeile"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Kompilieren eines C++/CX-Programms in der Befehlszeile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Visual C\+\+\-Programme erstellen, die auf die Windows Runtime abzielen und diese in der Befehlszeile erstellen.  Visual C\+\+ unterstützt Visual C\+\+\-Komponentenerweiterungen \(C\+\+\/CX\), die zusätzliche Typen und Operatoren für das Windows\-Runtime\-Programmiermodell bereitstellen.  Sie können C\+\+\/CX verwenden, um Windows Phone 8.1\-, Windows Store\- und Windows\-Desktop\-Apps zu erstellen.  Weitere Informationen finden Sie unter [Einführung in C\+\+\/CX](http://msdn.microsoft.com/magazine/dn166929.aspx) und [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).  
  
 In dieser exemplarischen Vorgehensweise verwenden Sie einen Texteditor zur Erstellung eines grundlegenden C\+\+\/CX\-Programms und kompilieren es dann auf der Befehlszeile.  \(Sie können Sie Ihr C\+\+\/CX\-Programm verwenden, statt das gezeigte einzugeben oder Sie können ein C\+\+\/CX\-Codebeispiel aus einem anderen Hilfeartikel verwenden.  Diese Technik ist nützlich zum Erstellen und Testen von kleinen Modulen, die keine Benutzeroberflächenelemente enthalten.\)  
  
> [!NOTE]
>  Sie können auch die Visual Studio IDE für die Kompilierung von C\+\+\/CX\-Programmen verwenden.  Da die IDE Design, Debuggen, Emulation und Unterstützung für die Bereitstellung, die auf der Befehlszeile nicht verfügbar ist, enthält, empfehlen wir die Verwendung der IDE zum Erstellen von Windows Store\-Apps.  Weitere Informationen finden Sie unter [Create a basic C\+\+ Store app](http://msdn.microsoft.com/library/windows/apps/dn263168).  
  
## Vorbereitungsmaßnahmen  
 Sie benötigen grundlegende Kenntnisse der Programmiersprache C\+\+.  
  
## Kompilieren eines C\+\+\/CX\-Programms  
 TZur Aktivierung der Kompilierung für C\+\+\/CX müssen Sie die Compileroption [\/ZW](../build/reference/zw-windows-runtime-compilation.md) verwenden.  Der Visual C\+\+\-Compiler generiert eine .exe\-Datei, die auf die Windows Runtime abzielt und mit den erforderlichen Bibliotheken verknüpft wird.  
  
#### So kompilieren Sie eine C\+\+\/CX\-Anwendung in der Befehlszeile  
  
1.  Öffnen Sie ein **Developer\-Eingabeaufforderungsfenster**.  \(Öffnen Sie im **Start**\-Fenster **Apps**.  Öffnen Sie den Ordner **Visual Studio\-Tools** unter Ihrer Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], und wählen Sie dann die Verknüpfung **Developer\-Eingabeaufforderung** aus.\) Weitere Informationen dazu, wie Sie ein Eingabeaufforderungsfenster öffnen, finden Sie unter [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
     Administratoranmeldeinformationen sind möglicherweise erforderlich, um den Code abhängig vom Betriebssystem und der Konfiguration des Computers zu kompilieren.  Zum Ausführen des Eingabeaufforderungsfensters als Administrator öffnen Sie das Kontextmenü für die **Developer\-Eingabeaufforderung**, und wählen Sie dann **Als Administrator ausführen** aus.  
  
2.  Geben Sie an der Eingabeaufforderung **notepad basiccx.cpp** ein.  
  
     Sie werden aufgefordert, eine Datei zu erstellen. Wählen Sie **Ja** aus.  
  
3.  Geben Sie die folgenden Zeilen in Notepad ein:  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  Wählen Sie in der Menüleiste **Datei** und dann **Speichern**.  
  
     Sie haben eine Visual C\+\+\-Quelldatei erstellt, die den Windows Runtime [Plattformnamespace](../Topic/Platform%20namespace%20\(C++-CX\).md)\-Namespace verwendet.  
  
5.  Geben Sie an der Eingabeaufforderung **cl \/EHsc \/ZW basiccx.cpp \/link \/SUBSYSTEM:CONSOLE** ein.  Der cl.exe\-Compiler kompiliert den Quellcode in eine .obj\-Datei und führt dann den Linker aus, um ein ausführbares Programm namens basiccx.exe zu generieren.  \(Die Compileroption [\/EHsc](../build/reference/eh-exception-handling-model.md) gibt das C\+\+\-Ausnahmebehandlungsmodell und das Flag [\/link](../build/reference/link-pass-options-to-linker.md) gibt eine Konsolenanwendung an.\)  
  
6.  Geben Sie zum Ausführen des basiccx.exe\-Programms an der Eingabeaufforderung **basiccx** ein.  
  
     Das Programm zeigt folgenden Text an und wird anschließend beendet:  
  
  **Dies ist ein C\+\+\/CX\-Programm.**  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C\/C\+\+\-Programmen](../build/building-c-cpp-programs.md)   
 [Compileroptionen](../build/reference/compiler-options.md)