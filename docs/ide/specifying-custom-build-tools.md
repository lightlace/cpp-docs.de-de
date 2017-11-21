---
title: Geben Sie benutzerdefinierte Tools erstellen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets
- VC.Project.VCCustomBuildTool.Outputs
- VC.Project.VCCustomBuildTool.Command
- VC.Project.VCCustomBuildTool.CommandLine
- VC.Project.VCCustomBuildTool.AdditionalDependencies
- VC.Project.VCCustomBuildTool.Message
- VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets
- VC.Project.VCCustomBuildTool.Description
- VC.Project.VCCustomBuildTool.AdditionalInputs
dev_langs: C++
helpviewer_keywords:
- build tools (C++), specifying
- custom build tools (C++), specifying
- builds (C++), custom build tools
ms.assetid: e5161946-8002-418d-991e-219e6a8586f5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c65664e6c09028f1f15ded917a59ad013868f841
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="specifying-custom-build-tools"></a>Angeben von benutzerdefinierten Buildtools
Ein *benutzerdefiniertes Buildtool* bietet das Buildsystem benötigt werden, um bestimmte Eingabedateien zu erstellen. Ein benutzerdefiniertes Buildtool gibt keinen auszuführenden Befehl, eine Liste der Eingabedateien, eine Liste von Ausgabedateien, die vom Befehl generiert werden und eine optionale Beschreibung des Tools.  
  
 Allgemeine Informationen zu benutzerdefinierten Buildtools und benutzerdefinierte Buildschritte, finden Sie unter [benutzerdefinierte Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md).  
  
### <a name="to-specify-a-custom-build-tool"></a>Um ein benutzerdefiniertes Buildtool anzugeben.  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf **Konfigurationseigenschaften** So aktivieren Sie die **Konfiguration** Feld. In der **Konfiguration** Feld, wählen Sie die Konfiguration für die Sie ein benutzerdefiniertes Buildtool angeben möchten.  
  
3.  In **Projektmappen-Explorer**, wählen Sie die Eingabedatei für das benutzerdefinierte Buildtool.  
  
     Wenn die **benutzerdefiniertes Buildtool** Ordner nicht angezeigt wird, die Erweiterung von Ihnen ausgewählte Datei ist ein Standardtool zugeordnet. Beispielsweise ist das Standardtool für c- und CPP-Dateien vom Compiler. Tool-Standardeinstellung, überschreiben die **Konfigurationseigenschaften** Knoten in der **allgemeine** Ordner in der **Work Item Type** -Eigenschaft, klicken Sie auf **für benutzerdefinierten Buildschritt Tool**. Klicken Sie auf **übernehmen** und **benutzerdefiniertes Buildtool** Knoten wird angezeigt.  
  
4.  In der **benutzerdefiniertes Buildtool** Knoten in der **allgemeine** Ordner Geben Sie die Eigenschaften für das benutzerdefinierte Tool zu erstellen:  
  
    -   In **zusätzliche Abhängigkeiten**, geben Sie ggf. zusätzlichen Dateien außerhalb der Datei für die das benutzerdefinierte Buildtool definiert wurde (die Datei, die das benutzerdefinierte Buildtool zugeordnet ist implizit als Eingabe für das Tool betrachtet). Zusätzliche Eingabedateien ist keine Voraussetzung für ein benutzerdefiniertes Buildtool. Wenn Sie mehr als eine zusätzliche Eingabe verfügen, durch Semikolons getrennt werden.  
  
         Wenn ein **zusätzliche Abhängigkeiten** Datei Datum liegt nach der Eingabedatei, und klicken Sie dann das benutzerdefinierte Buildtool ausgeführt wird. Wenn alle von der **zusätzliche Abhängigkeiten** Dateien sind älter als die Eingabedatei und die Eingabedatei ist älter als die **Ausgaben** Eigenschaftendatei, und klicken Sie dann auf das benutzerdefinierte Buildtool wird nicht ausgeführt.  
  
         Nehmen wir beispielsweise an, dass Sie ein benutzerdefiniertes Buildtool verfügen, das MyInput.x als Eingabe und MyInput.cpp generiert und diese MeineEingabe.x enthält eine Headerdatei MeinHeader.h. Sie können MyHeader.h angeben, als Eingabe Abhängigkeit zu MeineEingabe.x, und das Buildsystem erstellen MyInput.cpp aus, wenn es in Bezug auf MeineEingabe.x MyHeader.h veraltet ist.  
  
         Eingabe Abhängigkeiten können auch Stellen Sie sicher, dass Ihre benutzerdefinierten Buildtools in der Reihenfolge ausgeführt, die Sie um benötigt. Nehmen Sie im vorherigen Beispiel MyHeader.h sich tatsächlich um die Ausgabe ein benutzerdefiniertes Buildtool an. Da MyHeader.h eine Abhängigkeit von MyInput.x ist, erstellt das Buildsystem zuerst MyHeader.h vor dem Ausführen des benutzerdefinierten Build-Tools für MeineEingabe.x.  
  
    -   In **Befehlszeile**, geben Sie einen Befehl aus, als ob Sie sie an der Eingabeaufforderung angegeben wurden. Geben Sie einen gültigen Befehl oder eine Batchdatei, und alle erforderlichen Eingabe- oder Ausgabedateien. Geben Sie die **Aufrufen** batch-Befehl vor dem Namen einer Batchdatei aus, um zu gewährleisten, dass alle nachfolgenden Befehle ausgeführt werden.  
  
         Mehrere Eingabe- und Dateien können symbolisch mit MSBuild-Makros angegeben werden. [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)]Angabe des Speicherorts von Dateien oder die Namen von Sätzen von Dateien, finden Sie unter [allgemeine Makros für Buildbefehle und-Eigenschaften](../ide/common-macros-for-build-commands-and-properties.md).  
  
         Da das Zeichen "%" von MSBuild reserviert ist, wenn Sie angeben, eine Umgebungsvariable ersetzen Sie jeden  **%**  escape-Zeichen mit der **% 25** hexadezimale Escapesequenz. Ersetzen Sie z. B. **"% windir%"** mit **25WINDIR % 25**. MSBuild ersetzt jede **% 25** Sequenz mit dem  **%**  Zeichen, bevor er die Umgebungsvariable zugreift.  
  
    -   In **Beschreibung**, geben Sie eine beschreibende Meldung zu diesem benutzerdefinierten Build-Tool. Die Meldung wird ausgegeben, um die **Ausgabe** Fenster, wenn das Buildsystem dieses Tool verarbeitet.  
  
    -   In **Ausgaben**, geben Sie den Namen der Ausgabedatei. Dieser ist Eintrag erforderlich; ohne einen Wert für diese Eigenschaft ist wird das benutzerdefinierte Buildtool nicht ausgeführt. Verfügt ein benutzerdefiniertes Buildtool mehr als einer Ausgabe, trennen Sie Namen durch ein Semikolon.  
  
         Der Name der Ausgabedatei identisch sein soll, wie sie in angegeben ist die **Befehlszeile** Eigenschaft. Das Build-Projektsystem wird nach der Datei gesucht und überprüfen Sie das Datum. Wenn die Ausgabedatei neuer als die Eingabedatei ist oder wenn die Ausgabedatei nicht gefunden wird, wird das benutzerdefinierte Buildtool ausgeführt. Wenn alle von der **zusätzliche Abhängigkeiten** Dateien sind älter als die Eingabedatei und die Eingabedatei ist älter als die angegebene Datei der **Ausgaben** -Eigenschaft, die benutzerdefiniertes Buildtool wird nicht ausgeführt.  
  
 Wenn das Buildsystem, Vorgänge für eine Ausgabedatei, die durch das benutzerdefinierte Buildtool generiert werden sollen, müssen Sie manuell zum Projekt hinzufügen. Das benutzerdefinierte Buildtool wird die Datei während der Builderstellung aktualisieren.  
  
## <a name="example"></a>Beispiel  
 Angenommen Sie, Sie in Ihrem Projekt eine Datei mit dem Namen parser.l einschließen möchten. Soll eine Lexikalische Analyse verarbeitet werden, um eine c-Datei zu erstellen, die den gleichen Basisnamen (parser.c) aufweist.  
  
 Fügen Sie zunächst parser.l und parser.c zum Projekt aus. Wenn die Dateien noch nicht vorhanden sind, fügen Sie einfach einen Verweis auf die Dateien hinzu. Sie erstellen ein benutzerdefiniertes Buildtool für parser.l, und geben Sie Folgendes in die **Befehle** Eigenschaft:  
  
```  
lexer %(FullPath) .\%(Filename).c  
```  
  
 Mit diesem Befehl wird die lexikalischen parser.l ausgeführt und Parser.c in das Projektverzeichnis.  
  
 In der **Ausgaben** -Eigenschaft, geben Sie Folgendes ein:  
  
```  
.\%(Filename).c  
```  
  
 Wenn Sie das Projekt erstellen, vergleicht das Buildsystem die Timestamps von parser.l und parser.c an. Wenn parser.l aktuell ist, oder wenn parser.c nicht vorhanden ist, das Buildsystem den Wert des führt der **Befehlszeile** Eigenschaft um parser.c auf dem neuesten Stand zu bringen. Da parser.c ebenfalls dem Projekt hinzugefügt wurde, kompiliert das Buildsystem dann parser.c.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Makros für Buildbefehle und-Eigenschaften](../ide/common-macros-for-build-commands-and-properties.md)   
 [Problembehandlung für Buildanpassungen](../ide/troubleshooting-build-customizations.md)