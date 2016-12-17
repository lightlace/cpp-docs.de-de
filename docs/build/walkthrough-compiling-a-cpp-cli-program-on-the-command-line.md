---
title: "Exemplarische Vorgehensweise: Kompilieren eines C++/CLI-Programms in der Befehlszeile"
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
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Kompilieren eines C++/CLI-Programms in der Befehlszeile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Visual C\+\+\-Programme erstellen, die auf die Common Language Runtime \(CLR\) abzielen und .NET Framework verwenden, und diese in der Befehlszeile erstellen.  Visual C\+\+ unterstützt die the C\+\+\/CLI\-Programmiersprache, die über zusätzliche Typen und Operatoren für das .NET\-Programmiermodell verfügt.  Eine Einführung in die C\+\+\/CLI\-Sprache finden Sie unter [Reines C\+\+: Hallo, C\+\+\/CLI](http://msdn.microsoft.com/magazine/cc163681.aspx).  Weitere Informationen finden Sie unter [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
 In dieser exemplarischen Vorgehensweise verwenden Sie einen Texteditor zur Erstellung eines grundlegenden C\+\+\/CLI\-Programms und kompilieren es dann auf der Befehlszeile.  \(Sie können Sie Ihr C\+\+\/CLI\-Programm verwenden, statt das gezeigte einzugeben, oder Sie können ein C\+\+\/CLI\-Codebeispiel aus einem anderen Hilfeartikel verwenden.  Diese Technik ist nützlich zum Erstellen und Testen von kleinen Modulen, die keine Benutzeroberflächenelemente enthalten.\)  
  
> [!NOTE]
>  Sie können auch die Visual Studio IDE für die Kompilierung von C\+\+\/CLI\-Programmen verwenden.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Kompilieren eines C\+\+\-Programms für die CLR in Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).  
  
## Vorbereitungsmaßnahmen  
 Sie benötigen grundlegende Kenntnisse der Programmiersprache C\+\+.  
  
## Kompilieren eines C\+\+\/CLI\-Programms  
 Die folgenden Schritte zeigen, wie Sie eine C\+\+\/CLI\-Konsolenanwendung kompilieren, die .NET Framework\-Klassen verwendet.  
  
 Zur Aktivierung der Kompilierung für C\+\+\/CLI müssen Sie die Compileroption [\/clr](../build/reference/clr-common-language-runtime-compilation.md) verwenden.  Der Visual C\+\+\-Compiler generiert eine .exe\-Datei, die MSIL\-Code oder gemischtren MSIL\- oder nativen Code sowie Links zu den erforderlichen .NET\-Framework\-Bibliotheken enthält.  
  
#### So kompilieren Sie eine C\+\+\/CLI\-Anwendung in der Befehlszeile  
  
1.  Öffnen Sie ein **Developer\-Eingabeaufforderungsfenster**.  \(Öffnen Sie im **Start**\-Fenster **Apps**.  Öffnen Sie den Ordner **Visual Studio\-Tools** unter Ihrer Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], und wählen Sie dann die Verknüpfung **Developer\-Eingabeaufforderung** aus.\) Weitere Informationen dazu, wie Sie ein Eingabeaufforderungsfenster öffnen, finden Sie unter [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
     Administratoranmeldeinformationen sind möglicherweise erforderlich, um den Code abhängig vom Betriebssystem und der Konfiguration des Computers zu kompilieren.  Zum Ausführen des Eingabeaufforderungsfensters als Administrator öffnen Sie das Kontextmenü für die **Developer\-Eingabeaufforderung**, und wählen Sie dann **Als Administrator ausführen** aus.  
  
2.  Geben Sie an der Eingabeaufforderung **notepad basicclr.cpp** ein.  
  
     Sie werden aufgefordert, eine Datei zu erstellen. Wählen Sie **Ja** aus.  
  
3.  Geben Sie die folgenden Zeilen in Notepad ein:  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  Wählen Sie in der Menüleiste **Datei** und dann **Speichern**.  
  
     Sie haben nun eine Visual C\+\+\-Quelldatei erstellt, die eine .NET\-Framework\-Klasse \(<xref:System.Console>\) im Namespace <xref:System> enthält.  
  
5.  Geben Sie an der Eingabeaufforderung **cl \/clr basicclr.cpp** ein.  Der cl.exe\-Compiler kompiliert den Quellcode in eine .obj\-Datei, die MSIL enthält, und führt dann den Linker aus, um ein ausführbares Programm namens basicclr.exe zu generieren.  
  
6.  Geben Sie zum Ausführen des basicclr.exe\-Programms an der Eingabeaufforderung **basicclr** ein.  
  
     Das Programm zeigt folgenden Text an und wird anschließend beendet:  
  
  **Dies ist ein C\+\+\/CLI\-Programm.**  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C\/C\+\+\-Programmen](../build/building-c-cpp-programs.md)   
 [Compileroptionen](../build/reference/compiler-options.md)