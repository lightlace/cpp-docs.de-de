---
title: "Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C++-Programms in der Befehlszeile"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlszeilenanwendung [C++], Systemeigen"
  - "Kompilieren von Programmen [C++]"
  - "Systemeigener Code [C++]"
  - "Visual C++, Systemeigener Code"
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
caps.latest.revision: 63
caps.handback.revision: "57"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C++-Programms in der Befehlszeile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ beinhaltet einen C\+\+\-Compiler für die Befehlszeile, mit dem Sie von einfachen Konsolenanwendungen bis zu universellen Windows\-Apps, Windows Store\-Apps und .NET\-Komponenten alles erstellen können.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie ein grundlegendes Visual C\+\+\-Konsolenprogramm mit einem Text\-Editor und kompilieren es dann in der Befehlszeile.  
  
> [!NOTE]
>  Sie können auch die integrierte Entwicklungsumgebung \(Integrated Development Environment, IDE\) von Visual Studio für die Kompilierung von Visual C\+\+\-Programmen verwenden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen \(C\+\+\)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md).  
  
 In dieser exemplarischen Vorgehensweise können Sie Ihr eigenes Visual C\+\+\-Programm verwenden, statt das gezeigte einzugeben, oder Sie können ein Visual C\+\+\-Codebeispiel aus einem anderen Hilfeartikel verwenden.  
  
## Vorbereitungsmaßnahmen  
 Um diese exemplarische Vorgehensweise nachzuvollziehen, benötigen Sie eine Version von Visual Studio, in der die Visual C\+\+\-Komponenten enthalten sind. Grundlegende Kenntnisse der Programmiersprache C\+\+ sind nützlich. Diese Anweisungen gehen von der Annahme aus, dass Sie Windows 10 und Visual Studio 2015 verwenden, die Anweisungen für andere Umgebungen und Versionen sind aber ähnlich.  
  
### So erstellen Sie eine Visual C\+\+\-Quelldatei und kompilieren diese über die Befehlszeile  
  
1.  Öffnen Sie zuerst eine **Developer\-Eingabeaufforderung**. Der Visual C\+\+\-Compiler muss in einer besonderen Befehlsumgebung ausgeführt werden, daher können Sie für diese exemplarische Vorgehensweise keine normale Eingabeaufforderung verwenden.  
  
     Öffnen Sie im Windows **Startmenü** den Menüeintrag **Alle Apps**. Scrollen Sie nach unten, um den Ordner **Visual Studio** für Ihre Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] zu finden und zu öffnen, und wählen Sie dann die Verknüpfung **Developer\-Eingabeaufforderung** aus.  
  
2.  Erstellen Sie ein neues Verzeichnis für Ihr Programm. Geben Sie im Fenster **Developer\-Eingabeaufforderung** einen `cd \`\-Befehl ein, um in das Stammverzeichnis des Laufwerks zu wechseln. Geben Sie einen `md examples`\-Befehl ein, um ein Verzeichnis für den Beispielcode zu erstellen. Geben Sie anschließend den Befehl `cd examples` ein, um dieses Verzeichnis zu Ihren aktuellen Arbeitsverzeichnis zu machen. Hier wird Ihr erstes Programm erstellt.  
  
3.  Geben Sie an der Eingabeaufforderung **notepad hello.cpp** ein.  
  
     Sie werden aufgefordert, eine Datei zu erstellen. Wählen Sie **Ja** aus. Daraufhin wird ein leeres Editor\-Fenster geöffnet, das für Ihre Codeeingabe bereit ist.  
  
4.  Geben Sie die folgenden Zeilen in Notepad ein:  
  
    ```cpp  
    #include <iostream> using namespace std; void main() { cout << "Hello, world, from Visual C++!" << endl; }  
    ```  
  
     Dies ist ein sehr einfaches Programm, das eine Zeile Text auf den Bildschirm schreibt und sich dann beendet. Um Fehler zu minimieren, kopieren Sie diesen Code, und fügen Sie ihn in Editor ein.  
  
5.  Speichern Sie Ihre Arbeit. Wählen Sie im Editor im Menü **Datei** den Befehl **Speichern** aus.  
  
     Sie haben soeben eine Visual C\+\+\-Quelldatei erstellt.  
  
6.  Geben Sie an der Befehlszeile `cl /EHsc hello.cpp` ein, um Ihr Programm zu kompilieren.  
  
     Der cl.exe\-Compiler generiert eine OBJ\-Datei, die den kompilierten Code enthält, und führt dann den Linker aus, um ein ausführbares Programm namens „hello.exe“ zu erstellen. Dieser Name wird in den Zeilen der Ausgabeinformationen angezeigt, die der Compiler anzeigt. Die Ausgabe des Compilers sollte etwa wie folgt aussehen:  
  
    ```Output  
    Microsoft (R) C/C++-Optimierungscompiler Version 19.00.23504 für x86 Copyright (C) Microsoft Corporation.  Alle Rechte vorbehalten. hello.cpp Microsoft (R) Incremental Linker Version 14.00.23504.0 Copyright (C) Microsoft Corporation.  Alle Rechte vorbehalten. /out:hello.exe hello.obj  
    ```  
  
     Wenn Fehler auftreten, überprüfen Sie Ihren Code in Editor, um sicherzustellen, dass er dem Beispiel entspricht. Führen Sie den Compilerbefehl nach dem Speichern Ihrer Änderungen erneut aus.  Wenn der Befehl „cl“ nicht gefunden wird, überprüfen Sie, ob Sie die Developer\-Eingabeaufforderung verwenden, nicht etwa eine gewöhnliche Eingabeaufforderung. Wenn sie noch nicht installiert ist, müssen Sie möglicherweise auch in Visual Studio\-Setup die Visual C\+\+\-Komponente installieren.  
  
7.  Geben Sie zum Ausführen des hello.exe\-Programms an der Eingabeaufforderung `hello` ein.  
  
     Das Programm zeigt folgenden Text an und wird anschließend beendet:  
  
    ```Output  
    Hello, world, from Visual C++!  
    ```  
  
     Herzlichen Glückwunsch, Sie haben mithilfe der Befehlszeilentools ein Programm erstellt und kompiliert.  
  
## Nächste Schritte  
 Weitere Informationen zum Öffnen eines Developer\- Eingabeaufforderungsfensters für die Verwendung der Befehlszeilentools finden Sie unter [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Administratoranmeldeinformationen sind möglicherweise erforderlich, um den Code in dieser exemplarischen Vorgehensweise abhängig vom Betriebssystem und der Konfiguration des Computers zu kompilieren. Zum Ausführen des Developer\-Eingabeaufforderungsfensters als Administrator klicken Sie mit der rechten Maustaste, um das Kontextmenü für die **Developer\-Eingabeaufforderung** zu öffnen, und wählen Sie dann **Als Administrator ausführen** aus.  
  
 Die **\/EHsc**\-Befehlszeilenoption weist den Compiler an, die C\+\+\-Ausnahmebehandlung zu aktivieren. Weitere Informationen finden Sie unter [\/EH \(Ausnahmebehandlungsmodell\)](../build/reference/eh-exception-handling-model.md).  
  
## Siehe auch  
 [Tour zu Visual C\+\+](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C\/C\+\+\-Programmen](../build/building-c-cpp-programs.md)   
 [Compileroptionen](../build/reference/compiler-options.md)