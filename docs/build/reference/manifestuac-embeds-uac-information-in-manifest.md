---
title: "/MANIFESTUAC (bettet UAC-Informationen in Manifest ein) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UACUIAccess"
  - "VC.Project.VCLinkerTool.UACExecutionLevel"
  - "VC.Project.VCLinkerTool.EnableUAC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTUAC (Linkeroption)"
  - "MANIFESTUAC (Linkeroption)"
  - "-MANIFESTUAC (Linkeroption)"
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /MANIFESTUAC (bettet UAC-Informationen in Manifest ein)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob Informationen zur Benutzerkontensteuerung \(UAC\) in das Programmmanifest eingebettet werden.  
  
## Syntax  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### Parameter  
 `fragment`  
 Eine Zeichenfolge, die den `level`\-Wert und den `uiAccess`\-Wert enthält.  Weitere Informationen finden Sie unter "Hinweise" weiter unten in diesem Thema.  
  
 `_level`  
 Entweder *asInvoker*, *highestAvailable* oder *requireAdministrator*.  Wird standardmäßig auf "asInvoker" festgelegt.  Weitere Informationen finden Sie unter "Hinweise" weiter unten in diesem Thema.  
  
 `_uiAccess`  
 `true`, wenn die Anwendung Sicherheitsebenen für Benutzeroberflächen umgehen und Eingabe in Fenster mit höheren Berechtigungen auf dem Desktop lenken soll; andernfalls `false`.  Wird standardmäßig auf `false` festgelegt.  Nur für barrierefreie Anwendungen mit Benutzeroberflächen auf `true` festlegen.  
  
## Hinweise  
 Wenn Sie mehrere \/MANIFESTUAC\-Optionen in der Befehlszeile eingeben, erhält die zuletzt eingegebene den Vorrang.  
  
 Für "\/MANIFESTUAC:level" gibt es folgende Auswahlmöglichkeiten:  
  
-   `asInvoker`: Die Anwendung wird mit den gleichen Berechtigungen wie der Prozess ausgeführt, der sie gestartet hat.  Die Berechtigungen der Anwendung können durch Auswahl von **Als Administrator ausführen** auf eine höhere Ebene erweitert werden.  
  
-   "highestAvailable": Die Anwendung wird auf der höchsten für sie verfügbaren Berechtigungsebene ausgeführt.  Wenn der Benutzer, der die Anwendung startet, Mitglied der Gruppe "Administratoren" ist, entspricht diese Option "requireAdministrator".  Wenn die höchste verfügbare Berechtigungsebene höher als die Ebene des öffnenden Prozesses ist, fordert das System zur Eingabe von Anmeldeinformationen auf.  
  
-   "requireAdministrator": Die Anwendung wird mit Administratorrechten ausgeführt.  Der Benutzer, der die Anwendung startet, muss ein Mitglied der Gruppe "Administratoren" sein.  Wenn der öffnende Prozess nicht mit Administratorrechten ausgeführt wird, fordert das System zur Eingabe von Anmeldeinformationen auf.  
  
 Sie können die Ebene und die uiAccess\-Werte in einem Schritt angeben, indem Sie die \/MANIFESTUAC:fragment\-Option verwenden.  Das Fragment muss das folgende Format aufweisen:  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Manifestdatei** aus.  
  
5.  Ändern Sie die Eigenschaften **Benutzerkontensteuerung \(UAC\) aktivieren**, **UAC\-Ausführungsebene** und **Schutz vor Umgehen der Benutzeroberfläche für die Benutzerkontensteuerung**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC*>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)