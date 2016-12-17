---
title: "Gewusst wie: Aktivieren von IntelliSense f&#252;r Makefile-Projekte"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.IntelliSense"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntelliSense, Makefile-Projekte"
  - "Makefile-Projekte, IntelliSense"
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Aktivieren von IntelliSense f&#252;r Makefile-Projekte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn bestimmte Projekteinstellungen oder Compileroptionen nicht richtig eingestellt wurden, kann IntelliSense nicht für Visual C\+\+\-Makefile\-Projekte in der IDE verwendet werden.  Konfigurieren Sie Visual C\+\+\-Makefile\-Projekte mithilfe der folgenden Schritte, damit IntelliSense funktionsfähig ist, wenn Makefile\-Projekte in der Visual Studio\-Entwicklungsumgebung geöffnet sind.  
  
### So aktivieren Sie IntelliSense für Makefile\-Projekte in der IDE  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten**.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Wählen Sie die Eigenschaftenseite **NMake** aus, und ändern Sie dann die entsprechenden Eigenschaften unter **IntelliSense**.  
  
    -   Legen Sie die Eigenschaft **Präprozessordefinitionen** zur Definition von Präprozessorsymbolen im Makefile\-Projekt fest.  Weitere Informationen finden Sie unter [\/D \(Präprozessordefinitionen\)](../build/reference/d-preprocessor-definitions.md).  
  
    -   Legen Sie mit der Eigenschaft **Suchpfad einschließen** die Verzeichnisliste fest, die der Compiler zum Auflösen der an Präprozessordirektiven im Makefile\-Projekt übergebenen Dateiverweise durchsucht.  Weitere Informationen finden Sie unter [\/I \(Zusätzliche Includeverzeichnisse\)](../build/reference/i-additional-include-directories.md).  
  
         Legen Sie mit der **INCLUDE**\-Umgebungsvariablen für Projekte, die mithilfe von CL.EXE im Befehlsfenster erstellt werden, die Verzeichnisse fest, die der Compiler zum Auflösen der an die Präprozessordirektiven im Makefile\-Projekt übergebenen Dateiverweise durchsucht.  
  
    -   Legen Sie mit der Eigenschaft **Erzwungene Includes** die Headerdateien fest, die beim Erstellen des Makefile\-Projekts verarbeitet werden.  Weitere Informationen finden Sie unter [\/FI \(Name der expliziten Includedatei\)](../build/reference/fi-name-forced-include-file.md).  
  
    -   Legen Sie mit der Eigenschaft **Assemblysuchpfad** die Verzeichnisliste fest, die der Compiler zum Auflösen von Verweisen auf .NET\-Assemblys im Projekt durchsucht.  Weitere Informationen finden Sie unter [\/AI \(Metadatenverzeichnisse festlegen\)](../build/reference/ai-specify-metadata-directories.md).  
  
    -   Legen Sie mit der Eigenschaft **Erzwungene Verwendung von Assemblys** die beim Erstellen des Makefile\-Projekts zu verarbeitenden .NET\-Assemblys fest.  Weitere Informationen finden Sie unter [\/FU \(Name der expliziten \#using\-Datei\)](../build/reference/fu-name-forced-hash-using-file.md).  
  
    -   Legen Sie die Eigenschaft **Zusätzliche Optionen** fest, um zusätzliche Compilerschalter anzugeben, die von IntelliSense beim Analysieren von C\+\+\-Dateien verwendet werden sollen.  
  
4.  Klicken Sie auf **OK**, um die Eigenschaftenseiten zu schließen.  
  
5.  Speichern Sie die geänderten Projekteinstellungen mit dem Befehl **Alle speichern**.  
  
 Wenn Sie das Makefile\-Projekt das nächste Mail in der Visual Studio\-Entwicklungsumgebung öffnen, führen Sie den Befehl **Projektmappe bereinigen** und den Befehl **Projektmappe erstellen** für das Makefile\-Projekt aus.  IntelliSense sollte ordnungsgemäß in der IDE funktionieren.  
  
## Siehe auch  
 [Verwenden von IntelliSense](../Topic/Using%20IntelliSense.md)   
 [NMAKE\-Referenz](../build/nmake-reference.md)   
 [Gewusst wie: Erstellen eines C\+\+\-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)