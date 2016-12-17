---
title: "Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile"
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
  - "Kompilieren eines C-Programms [C++]"
  - "Befehlszeilenanwendung [C++], C-Programme"
  - "Kompilieren von Programmen [C++]"
  - "Visual C, Kompilieren"
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
caps.latest.revision: 46
caps.handback.revision: "31"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthält einen C\-Compiler, mit dem Sie alles von grundlegenden Konsolenprogrammen bis hin zu Windows\-Desktopanwendungen erstellen können.  
  
 In dieser exemplarischen Vorgehensweise wird erläutert, wie ein grundlegendes C\-Programm mit einem Text\-Editor erstellt wird, bevor es in der Befehlszeile kompiliert wird.  
  
 Sie können anstelle der in dieser exemplarischen Vorgehensweise gezeigten Beispielprogramme auch eigene C\-Programme verwenden.  Sie können aber auch jedes beliebige in den Hilfethemen enthaltene C\-Codebeispielprogramm verwenden.  
  
 Standardmäßig behandelt der Visual C\+\+\-Compiler alle auf .c endenden Dateien als C\-Quellcode und alle auf .cpp endenden Dateien als C\+\+\-Quellcode.  Wenn Sie erzwingen möchten, dass vom Compiler alle Dateien unabhängig von der Dateinamenerweiterung als C\-Dateien behandelt werden, verwenden Sie die [\/Tc](../build/reference/tc-tp-tc-tp-specify-source-file-type.md)\-Compileroption.  
  
## Vorbereitungsmaßnahmen  
 Sie benötigen grundlegende Kenntnisse der Programmiersprache C.  
  
### So können Sie eine C\-Quelldatei erstellen und sie über die Befehlszeile kompilieren  
  
1.  Öffnen Sie eine Developer\-Eingabeaufforderung.  Öffnen Sie in Windows 8 auf dem **Start**\-Bildschirm den Ordner **Visual Studio\-Tools**, und wählen Sie dann die Verknüpfung **Developer\-Eingabeaufforderung** aus.  In früheren Versionen von Windows wählen Sie die Schaltfläche **Start**, erweitern Sie **Alle Programme**, **Microsoft Visual Studio** und **Visual Studio\-Tools**, und wählen Sie dann **Developer\-Eingabeaufforderung**.  
  
     Abhängig von der Version von Windows auf dem Computer und der Systemsicherheitskonfiguration müssen Sie ggf. das Kontextmenü für **Developer\-Eingabeaufforderung** öffnen und dann **Als Administrator ausführen** auswählen, um die Anwendung gemäß den folgenden Schritten zu erstellen und auszuführen.  
  
    > [!NOTE]
    >  Von der **Developer\-Eingabeaufforderung** wird automatisch der richtige Pfad für den C\-Compiler und alle erforderlichen Bibliotheken festgelegt.  Verwenden Sie sie statt des regulären Eingabeaufforderungsfensters.  Weitere Informationen finden Sie unter [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
2.  Erstellen Sie an der Eingabeaufforderung ein Verzeichnis für die Quelldatei, das Sie als aktuelles Arbeitsverzeichnis verwenden.  Geben Sie beispielsweise **md c:\\simple** ein, und drücken Sie die Eingabeteste, um ein "simple" benanntes Verzeichnis zu erstellen. Geben Sie dann **cd c:\\simple** ein, und drücken Sie die Eingabetaste, um zu diesem Verzeichnis zu wechseln.  
  
3.  Geben Sie an der Eingabeaufforderung **notepad** ein, und drücken Sie die EINGABETASTE.  
  
4.  Geben Sie im Editor die folgenden Zeilen ein:  
  
     [!CODE [NVC_Walkthrough_Compile_C#100](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_compile_c#100)]  
  
5.  Wählen Sie in der Menüleiste **Datei**, **Speichern** aus, um das Dialogfeld **Speichern unter** zu öffnen.  Navigieren Sie zum Verzeichnis, das Sie erstellt haben.  Geben Sie im Feld **Dateiname** einen Namen für die Quelldatei ein – z. B. "simple.c". Wählen Sie dann in der Dropdownliste **Dateityp** die Option **Alle Dateien \(\*.\*\)** aus.  Wählen Sie die Schaltfläche **Speichern**, um eine C\-Quelldatei im Arbeitsverzeichnis zu erstellen.  
  
6.  Geben Sie an der Eingabeaufforderung **dir** ein, und drücken Sie die Eingabetaste.  Es sollte die Quelldatei, die Sie erstellt haben, angezeigt werden:  
  
  **C:\\simple\>dir**  
 **Volume in Laufwerk C hat keine Bezeichnung.  Volumeseriennummer: CC62\-6545**  
 **Verzeichnis von C:\\simple**  
**10\/02\/2012  03:46 PM    \<DIR\>          .  10\/02\/2012  03:46 PM    \<DIR\>          ..  10\/02\/2012  03:36 PM               102 simple.c**  
 **1 File\(s\)      102 bytes**  
 **2 Dir\(s\)  514.900.566.016 bytes free**      Die Details werden sich auf Ihrem Computer von den hier gezeigten unterscheiden.  Wenn die Quellcodedatei nicht angezeigt wird, vergewissern Sie sich, dass Sie in das von Ihnen erstellte Verzeichnis gewechselt sind, und stellen Sie sicher, dass Sie die Quelldatei darin mit der Dateinamenerweiterung „.c“ speichern.  
  
7.  Geben Sie an der Eingabeaufforderung den Befehl **cl** zusammen mit dem Namen der Quelldatei ein, z. B. **cl simple.c**. Drücken Sie dann die EINGABETASTE, um das Programm zu kompilieren.  Der cl.exe\-Compiler generiert eine .obj\-Datei, die den kompilierten Code enthält, und führt dann den Linker aus, um ein ausführbares Programm zu erstellen, das den Namen Ihrer Quelldatei, aber die Dateinamenerweiterung EXE hat, zum Beispiel "simple.exe".  
  
     Der Name des ausführbaren Programms wird in den vom Compiler erzeugten Ausgabeinformationen angezeigt.  
  
     **Ausgabe**  
  
  **Microsoft \(R\) C\/C\+\+\-Optimierungscompiler Version 17.00.50727.1 für x86**  
**Copyright \(C\) Microsoft Corporation.  Alle Rechte vorbehalten.  simple.c**  
**Microsoft \(R\) Incremental Linker Version 11.00.50727.1**  
**Copyright \(C\) Microsoft Corporation.  Alle Rechte vorbehalten.  \/out:simple.exe**  
**simple.obj**      Die Versionsnummer der Tools hängt von der Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] und den bei Ihnen installierten Updates ab.  
  
    > [!NOTE]
    >  Wenn Sie beispielsweise einen Fehler wie „'cl' wurde nicht als interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt“, Fehler C1034 oder Fehler LNK1104 erhalten, müssen Sie die Umgebung für den Compiler und die Tools einrichten.  Einzelheiten hierzu finden Sie in Schritt 1.  
    >   
    >  Wenn Sie einen Compilerfehler oder eine Warnung erhalten, überprüfen Sie den Quellcode auf Fehler, speichern Sie die Arbeit, und führen Sie den Compiler erneut aus.  Verwenden Sie das Suchfeld auf dieser Seite, um weitere Informationen zu bestimmten Fehlern zu erhalten.  
  
8.  Um das Programm auszuführen, geben Sie dessen Namen ohne die Dateierweiterung ein, z. B. **simple**, und drücken Sie die EINGABETASTE.  
  
     Das Programm zeigt folgenden Text an und wird anschließend beendet:  
  
     `This is a native C program.`  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen eines Win32\-Konsolenprogramms \(C\+\+\)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)   
 [C\-Sprachreferenz](../c-language/c-language-reference.md)   
 [Erstellen von C\/C\+\+\-Programmen](../build/building-c-cpp-programs.md)   
 [Kompatibilität](../c-runtime-library/compatibility.md)