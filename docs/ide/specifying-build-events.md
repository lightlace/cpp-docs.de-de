---
title: "Angeben von Buildereignissen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.IVCEventTool.CommandLine"
  - "VC.Project.IVCEventTool.ExcludedFromBuild"
  - "VC.Project.IVCEventTool.Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Buildereignisse [C++]"
  - "Buildereignisse [C++], Angeben"
  - "Builds [C++], Anpassen von C++"
  - "Builds [C++], Ereignisse"
  - "Benutzerdefinierte Buildschritte [C++], Buildereignisse"
  - "Ereignisse [C++], Build"
  - "Postbuildereignisse"
  - "Prälinkereignis"
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Angeben von Buildereignissen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mithilfe von Buildereignissen können Befehle festgelegt werden, die vor dem Buildvorgang, vor dem Verknüpfungsvorgang oder nach dem Buildvorgang ausgeführt werden.  
  
 Buildereignisse werden nur dann ausgeführt, wenn im Buildvorgang diese Punkte erfolgreich erreicht werden.  Wenn während des Buildvorgangs ein Fehler ausgegeben wird, tritt kein *Postbuild*ereignis auf. Wenn der Fehler vor der Verknüpfungsphase auftritt, wird weder das *Prälink*ereignis noch das *Postbuild*ereignis erstellt.  Das *Prälink*ereignis tritt außerdem nicht auf, wenn keine Dateien verknüpft werden müssen.  In Projekten, die keinen Verknüpfungsschritt enthalten, tritt das *Prälink*ereignis ebenfalls nicht auf.  
  
 Wenn keine Dateien erstellt werden müssen, treten keine Buildereignisse auf.  
  
 Allgemeine Informationen zu Buildereignissen finden Sie unter [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md).  
  
### So legen Sie ein Buildereignis fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** das Projekt aus, für das das Buildereignis festgelegt werden soll.  
  
2.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
3.  Wählen Sie im Ordner **Buildereignisse** eine Buildereignis\-Eigenschaftenseite aus.  
  
4.  Legen Sie die dem Buildereignis zugeordneten Eigenschaften fest:  
  
    -   Geben Sie in der Befehlszeile einen Befehl so an, als ob Sie ihn an der Eingabeaufforderung eingeben würden.  Geben Sie einen gültigen Befehl oder eine Batchdatei und alle erforderlichen Eingabe\- oder Ausgabedateien an.  Geben Sie den Batchbefehl **call** vor dem Namen einer Batchdatei an, um sicherzustellen, dass alle nachfolgenden Befehle ausgeführt werden.  
  
         Mehrere Eingabe\- und Ausgabedateien können symbolisch mit MSBuild\-Makros angegeben werden.  [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)] zur Angabe des Speicherorts der Dateien oder der Namen der Dateisätze finden Sie unter [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md).  
  
         Da das Zeichen "%" von MSBuild reserviert wird, wenn eine Umgebungsvariable angegeben wird, ersetzen Sie jedes **%**\-Escapezeichen durch die hexadezimale Escapesequenz **%25**.  Ersetzen Sie z. B. **%WINDIR%** durch **%25WINDIR%25**:  MSBuild ersetzt jede **%25**\-Sequenz durch das Zeichen **%**, bevor auf die Umgebungsvariable zugegriffen wird.  
  
    -   Geben Sie unter **Beschreibung** eine Beschreibung für dieses Ereignis ein.  Die Beschreibung wird beim Auftreten dieses Ereignisses im **Ausgabefenster** angezeigt.  
  
    -   Geben Sie unter **Vom Build ausschließen** die Option **Ja** an, wenn das Ereignis nicht ausgeführt werden soll.  
  
## Siehe auch  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)   
 [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md)   
 [Problembehandlung für Buildanpassungen](../ide/troubleshooting-build-customizations.md)