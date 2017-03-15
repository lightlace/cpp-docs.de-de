---
title: "Buildsystem&#228;nderungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.msbuild.changes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Buildsystemänderungen, $(Inherit)"
  - "Buildsystemänderungen, $(NoInherit)"
  - "Buildsystemänderungen, .vsprops"
  - "Buildsystemänderungen, Benutzerdefinierte Buildregeln"
  - "Buildsystemänderungen, MSBuild"
  - "Buildsystemänderungen, Projektdatei (.vcxprog)"
  - "MSBuild, Buildsystemänderungen"
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Buildsystem&#228;nderungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das MSBuild\-System wird verwendet, um Visual C\+\+\-Projekte zu erstellen.  In Visual Studio 2008 und vorherigen Versionen, wurde das VCBuild\-System verwendet.  Bestimmte Dateitypen und Konzepte, die von abhingen VCBuild entweder, vorhanden oder werden anders nicht im aktuellen System dargestellt.  In diesem Dokument werden die Unterschiede im aktuellen Buildsystem erläutert.  
  
## Das VCPROJ\-Format lautet jetzt VCXPROJ.  
 Projektdateien verwenden nicht mehr die VCPROJ\-Dateinamenerweiterung.  Visual Studio konvertiert Projektdateien, die in einer früheren Version von Visual C\+\+ erstellt wurden, automatisch in das vom aktuellen System verwendete Format.  Weitere Informationen zum manuellen Aktualisieren einer Projekterweiterung finden Sie unter [\/Upgrade](../Topic/-Upgrade%20\(devenv.exe\).md).  
  
 In der aktuellen Version lautet die Dateinamenerweiterung für eine Projektdatei VCXPROJ.  
  
## Das VSPROPS\-Format lautet jetzt PROPS.  
 In früheren Versionen ist das *Projekteigenschaftenblatt* eine XML\-basierte Datei mit der VSPROPS\-Dateinamenerweiterung.  Ein Projekteigenschaftenblatt ermöglicht Ihnen das Festlegen von Schaltern für Buildtools, wie Compiler oder Linker, und das Erstellen benutzerdefinierter Makros.  
  
 In der aktuellen Version ist die Dateinamenerweiterung für ein Projekteigenschaftenblatt PROPS.  
  
## Benutzerdefinierte Buildregeln und RULES\-Dateien  
 In früheren Versionen ist eine *Regeldatei* eine XML\-basierte Datei mit der RULES\-Dateinamenerweiterung.  Mithilfe einer Regeldatei können Sie benutzerdefinierte Buildregeln definieren und in den Buildvorgang eines Visual C\+\+\-Projekts integrieren.  Eine benutzerdefinierte Buildregel, die mindestens einer Dateinamenerweiterung zugeordnet werden kann, ermöglicht die Übergabe von Eingabedateien an ein Tool, mit dem mindestens eine Ausgabedatei erstellt wird.  
  
 In dieser Version werden benutzerdefinierte Buildregeln durch drei Dateitypen \(XML, PROPS und TARGETS\) anstatt durch eine RULES\-Datei dargestellt.  Wenn eine RULES\-Datei, die mit einer früheren Version von Visual C\+\+ erstellt wurde, zur aktuellen Version migriert wird, werden entsprechende XML\-, PROPS\- und TARGETS\-Dateien zusammen mit der ursprünglichen RULES\-Datei im Projekt erstellt und gespeichert.  
  
> [!IMPORTANT]
>  In der aktuellen Version unterstützt [!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)] die Erstellung neuer Regeln nicht.  Die einfachste Möglichkeit, zur Verwendung einer Regeldatei aus einem Projekt, das erstellt wurde, indem Sie eine frühere Version von Visual C\+\+ erstellt wurde, das Projekt zur aktuellen Version zu migrieren.  
  
## Vererbungsmakros  
 In früheren Versionen gab das **$\(Inherit\)**\-Makro die Reihenfolge an, in der geerbte Eigenschaften auf der Befehlszeile erscheinen, die vom Projektbuildsystem verfasst wird.  Das **$\(NoInherit\)**\-Makro bewirkt, dass beliebige Vorkommen von $\(Inherit\) ignoriert werden und alle Eigenschaften, die andernfalls geerbt werden würden, nicht geerbt werden.  Zum Beispiel werden durch das $\(Inherit\)\-Makro die mit der [\/I \(Zusätzliche Includeverzeichnisse\)](../build/reference/i-additional-include-directories.md)\-Compileroption angegebenen Dateien an die Befehlszeile angefügt.  
  
 In der aktuellen Version wird Vererbung durch das Angeben des Werts einer Eigenschaft als Verkettung eines bzw. mehrerer literaler Werte und Eigenschaftenmakros unterstützt.  Die **$\(Inherit\)**\- und **$\(NoInherit\)**\-Makros werden nicht unterstützt.  
  
 Im folgenden Beispiel wird einer Eigenschaft auf einer Eigenschaftenseite eine durch Semikolons getrennte Liste zugewiesen.  Die Liste besteht aus der Verkettung des *\<value\>* \- Literals und des Werts der `MyProperty`\-Eigenschaft, auf die zugegriffen wird, mit der Makronotation ", **$\(***MyProperty***\)**.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## VCXPROJ.USER\-Dateien  
 In einer Benutzerdatei \(VCXPROJ\-Format\) werden benutzerspezifische Eigenschaften gespeichert, z. B. Debugging\-Einstellungen und Bereitstellungseinstellungen.  Die VCXPROJ.USER\-Datei gilt für alle Projekte eines bestimmten Benutzers.  
  
## VCXPROJ.FILTERS\-Datei  
 Wenn **der Projektmappen\-Explorer** verwendet wird, um einem Projekt eine Datei hinzuzufügen, definiert die Filter\-Datei \(vcxproj.filters\), wo die Datei auf Grundlage der Dateinamenerweiterung in der **Projektmappen\-Explorer**\-Strukturansicht hinzugefügt wird.  
  
## VC\+\+\-Verzeichniseinstellungen  
 Einstellungen für Visual C\+\+\-Verzeichnisse werden auf der [Eigenschaftenseite "VC\+\+\-Verzeichnisse"](../ide/vcpp-directories-property-page.md) angegeben.  In früheren Versionen von Visual Studio sind Verzeichniseinstellungen pro Benutzer gültig, und die Liste der ausgeschlossenen Verzeichnisse wird in der Datei "sysincl.dat" angegeben.  
  
 Sie können die VC\+\+\-Verzeichniseinstellungen nicht ändern, wenn Sie [devenv \/resetsettings](../Topic/-ResetSettings%20\(devenv.exe\).md) in der Befehlszeile ausführen.  Sie können auch die Einstellungen nicht ändern, wenn Sie das Menü **Extras** öffnen, auf **Einstellungen importieren und exportieren** klicken und anschließend die Option **Alle Einstellungen zurücksetzen** auswählen.  
  
 Migrieren Sie VC\+\+\-Verzeichniseinstellungen von einer VSSETTINGS\-Datei, die von einer früheren Version von Visual C\+\+ erstellt wurde.  Öffnen Sie das Menü **Extras**, klicken Sie auf **Einstellungen importieren und exportieren**, wählen Sie **Ausgewählte Umgebungseinstellungen importieren** aus, und befolgen Sie dann die Anweisungen im Assistenten.  Wenn Sie Visual Studio zum ersten Mal starten, können Sie auch im Dialogfeld **Standardumgebungseinstellungen auswählen** die Option **Gültige Einstellungen aus einer vorherigen Version migrieren und zusätzlich zu den unten ausgewählten Standardeinstellungen übernehmen** auswählen.  
  
## Siehe auch  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)