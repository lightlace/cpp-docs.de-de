---
title: "Angeben von benutzerdefinierten Buildtools | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets"
  - "VC.Project.VCCustomBuildTool.Outputs"
  - "VC.Project.VCCustomBuildTool.Command"
  - "VC.Project.VCCustomBuildTool.CommandLine"
  - "VC.Project.VCCustomBuildTool.AdditionalDependencies"
  - "VC.Project.VCCustomBuildTool.Message"
  - "VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets"
  - "VC.Project.VCCustomBuildTool.Description"
  - "VC.Project.VCCustomBuildTool.AdditionalInputs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Buildtools (C++), Angeben"
  - "Builds (C++), Benutzerdefinierte Buildtools"
  - "Benutzerdefinierte Buildtools (C++), Angeben"
ms.assetid: e5161946-8002-418d-991e-219e6a8586f5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Angeben von benutzerdefinierten Buildtools
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit einem *benutzerdefinierten Buildtool* werden dem Buildsystem die Informationen übermittelt, die es benötigt, um Ausgabedateien aus einer Eingabedatei zu erstellen.  Ein benutzerdefiniertes Buildtool gibt einen auszuführenden Befehl, eine Liste mit Eingabe\- und eine Liste mit Ausgabedateien, die durch den Befehl generiert werden, sowie eine optionale Beschreibung des Tools an.  
  
 Allgemeine Informationen zu benutzerdefinierten Buildtools und \-schritten finden Sie unter [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md).  
  
### So geben Sie ein benutzerdefiniertes Tool an  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf **Konfigurationseigenschaften**, um das Feld **Konfiguration** zu aktivieren.  Wählen Sie im Feld **Konfiguration** die Konfiguration aus, für die Sie ein benutzerdefiniertes Buildtool festlegen möchten.  
  
3.  Wählen Sie im **Projektmappen\-Explorer** die Eingabedatei für das benutzerdefinierte Buildtool aus.  
  
     Wenn der Ordner **Benutzerdefiniertes Buildtool** nicht angezeigt wird, wird die Erweiterung der ausgewählten Datei einem Standardtool zugeordnet.  Das standardmäßige Tool für C\- und CPP\-Dateien ist der Compiler.  Klicken Sie zum Überschreiben einer Standardtooleinstellung unter dem Knoten **Konfigurationseigenschaften** im Ordner **Allgemein** in der Eigenschaft **Artikeltyp** auf **Benutzerdefiniertes Buildtool**.  Wenn Sie auf **Übernehmen** klicken, wird der Knoten **Benutzerdefiniertes Buildtool** angezeigt.  
  
4.  Geben Sie unter dem Knoten **Benutzerdefiniertes Buildtool** im Ordner **Allgemein** die Eigenschaften an, die dem benutzerdefinierten Buildtool zugeordnet sind:  
  
    -   Geben Sie unter **Zusätzliche Abhängigkeiten** zusätzlich zu der Datei, für die das benutzerdefinierte Buildtool definiert wurde, weitere Dateien an \(die dem benutzerdefinierten Buildtool zugeordnete Datei wird implizit als Eingabe für das Tool angesehen\).  Zusätzliche Eingabedateien sind für ein benutzerdefiniertes Buildtool nicht unbedingt erforderlich.  Wenn Sie über mehrere zusätzliche Eingaben verfügen, trennen Sie diese durch ein Semikolon.  
  
         Wenn das Datum einer Datei unter **Zusätzliche Abhängigkeiten** nach dem Datum der Eingabedatei liegt, wird das benutzerdefinierte Buildtool ausgeführt.  Wenn alle Dateien unter **Zusätzliche Abhängigkeiten** älter als die Eingabedatei sind und die Eingabedatei älter als die Eigenschaftendatei **Ausgaben** ist, wird das benutzerdefinierte Buildtool nicht ausgeführt.  
  
         Angenommen, Sie verfügen über ein benutzerdefiniertes Buildtool, das "MyInput.x" als Eingabe verwendet und "MyInput.cpp" generiert, und die Datei "MyInput.x" enthält die Headerdatei "MyHeader.h".  Sie können "MyHeader.h" gegenüber "MyInput.x" als Eingabeabhängigkeit festlegen. In diesem Fall wird die Datei "MyInput.cpp" vom Buildsystem erstellt, wenn sie im Vergleich zu "MyInput.x" oder "MyHeader.h" älter ist.  
  
         Durch Eingabeabhängigkeiten wird außerdem sichergestellt, dass benutzerdefinierte Buildtools in der gewünschten Reihenfolge ausgeführt werden.  Angenommen, bei der Datei "MyHeader.h" im vorangehenden Beispiel handelt es sich tatsächlich um die Ausgabe eines benutzerdefinierten Buildtools.  Da "MyHeader.h" eine Abhängigkeit von "MyInput.x" ist, erstellt das Buildsystem zuerst die Datei "Myheader.h", bevor es das benutzerdefinierte Buildtool für "MyInput.x" ausführt.  
  
    -   Geben Sie in der Befehlszeile einen Befehl so an, als ob Sie ihn an der Eingabeaufforderung eingeben würden.  Geben Sie einen gültigen Befehl oder eine Batchdatei und alle erforderlichen Eingabe\- oder Ausgabedateien an.  Geben Sie den Batchbefehl **call** vor dem Namen einer Batchdatei an, um sicherzustellen, dass alle nachfolgenden Befehle ausgeführt werden.  
  
         Mehrere Eingabe\- und Ausgabedateien können symbolisch mit MSBuild\-Makros angegeben werden.  [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)] zur Angabe des Speicherorts der Dateien oder der Namen der Dateisätze finden Sie unter [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md).  
  
         Da das Zeichen "%" von MSBuild reserviert wird, wenn eine Umgebungsvariable angegeben wird, ersetzen Sie jedes **%**\-Escapezeichen durch die hexadezimale Escapesequenz **%25**.  Ersetzen Sie z. B. **%WINDIR%** durch **%25WINDIR%25**:  MSBuild ersetzt jede **%25**\-Sequenz durch das Zeichen **%**, bevor auf die Umgebungsvariable zugegriffen wird.  
  
    -   Geben Sie in **Beschreibung** eine beschreibende Meldung zu diesem benutzerdefinierten Buildtool ein.  Die Meldung wird im Ausgabefenster angezeigt, wenn dieses Tool vom Buildsystem verarbeitet wird.  
  
    -   Geben Sie unter **Ausgaben** den Namen der Ausgabedatei an.  Dieser Eintrag ist erforderlich, da ein benutzerdefiniertes Buildtool ohne einen Wert für diese Eigenschaft nicht ausgeführt werden kann.  Wenn ein benutzerdefiniertes Buildtool über mehrere Ausgaben verfügt, werden die Dateinamen durch ein Semikolon getrennt.  
  
         Der Name der Ausgabedatei sollte der Eingabe für die Eigenschaft **Befehlszeile** entsprechen.  Das Projektbuildsystem sucht nach der Datei und überprüft ihr Datum.  Wenn die Ausgabedatei neuer als die Eingabedatei ist, bzw. wenn sie nicht gefunden wird, wird das benutzerdefinierte Buildtool ausgeführt.  Wenn alle Dateien unter **Zusätzliche Abhängigkeiten** älter als die Eingabedatei sind und die Eingabedatei älter als die in der **Outputs**\-Eigenschaft angegebene Datei ist, wird das benutzerdefinierte Buildtool nicht ausgeführt.  
  
 Wenn das Buildsystem eine durch das benutzerdefinierte Buildtool generierte Ausgabedatei verarbeiten soll, müssen Sie diese dem Projekt manuell hinzufügen.  Die Datei wird während des Buildvorgangs durch das benutzerdefinierte Buildtool aktualisiert.  
  
## Beispiel  
 Stellen Sie sich vor, Sie möchten eine Datei mit dem Namen "parser.l" in Ihr Projekt aufnehmen.  Diese Datei soll von einer lexikalischen Analyse verarbeitet werden, um eine C\-Datei mit demselben Basisnamen \(parser.c\) zu erstellen.  
  
 Zuerst fügen Sie dem Projekt parser.l und parser.c hinzu.  Wenn die Dateien noch nicht vorhanden sind, fügen Sie einfach einen Verweis auf die Dateien hinzu.  Sie erstellen ein benutzerdefiniertes Buildtool für "parser.l" und geben Folgendes für die **Commands**\-Eigenschaft ein:  
  
```  
lexer %(FullPath) .\%(Filename).c  
```  
  
 Durch diesen Befehl wird die lexikalische Analyse für parser.l ausgeführt und parser.c in das Projektverzeichnis ausgegeben.  
  
 Geben Sie für die Eigenschaft **Ausgaben** Folgendes ein:  
  
```  
.\%(Filename).c  
```  
  
 Wenn Sie das Projekt erstellen, vergleicht das Buildsystem die Timestamps von "parser.l" und "parser.c".  Wenn "parser.l" aktueller ist, oder wenn "parser.c" nicht vorhanden ist, wird die Eigenschaft **Befehlszeile** vom Buildsystem ausgeführt, um "parser.c" zu aktualisieren.  Da "parser.c" ebenfalls dem Projekt hinzugefügt wurde, kompiliert das Buildsystem anschließend "parser.c".  
  
## Siehe auch  
 [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md)   
 [Problembehandlung für Buildanpassungen](../ide/troubleshooting-build-customizations.md)