---
title: "/PGD (Angeben einer Datenbank f&#252;r die profilgesteuerte Optimierungen)"
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
  - "VC.Project.VCLinkerTool.ProfileGuidedDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PGD (Linkeroption)"
  - "-PGD (Linkeroption)"
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /PGD (Angeben einer Datenbank f&#252;r die profilgesteuerte Optimierungen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/PGD:`filename`  
  
## Hinweise  
 Hierbei ist:  
  
 `filename`  
 Gibt einen Namen für die PGD\-Datei an, in der Informationen zum ausgeführten Programm gespeichert werden.  
  
## Hinweise  
 Wenn Sie [\/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) verwenden, geben Sie mit \/PGD einen nicht standardmäßigen Namen oder Speicherort für die PGD\-Datei an.  Wenn Sie \/PGD nicht angeben, stimmt der Name der PGD\-Datei mit dem Namen der Ausgabedatei \(EXE oder DLL\) überein, und die PGD\-Datei wird in demselben Verzeichnis erstellt, in dem der Link aufgerufen wird.  
  
 Wenn Sie \/LTCG:PGOPTIMIZE verwenden, geben Sie mit \/PGD den Namen der PGD\-Datei an, mit der das optimierte Bild erstellt wird.  
  
 Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung \(PGO\)](../../build/reference/profile-guided-optimizations.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Optimierung** aus.  
  
5.  Ändern Sie die Eigenschaft **Profilgesteuerte Datenbank**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)