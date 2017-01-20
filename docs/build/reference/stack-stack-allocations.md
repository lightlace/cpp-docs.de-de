---
title: "/STACK (Stapelreservierungen)"
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
  - "VC.Project.VCLinkerTool.StackReserveSize"
  - "VC.Project.VCLinkerTool.StackCommitSize"
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACK (Linkeroption)"
  - "-STACK (Linkeroption)"
  - "Speicherbelegung, Stapel"
  - "/STACK (Linkeroption)"
  - "Stapel, Festlegen der Größe"
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# /STACK (Stapelreservierungen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## Hinweise  
 Durch die Option \/STACK wird die Stapelgröße in Bytes festgelegt.  Verwenden Sie diese Option nur zum Erstellen von EXE\-Dateien.  
  
 Der `reserve`\-Wert gibt die gesamte Stapelzuordnung im virtuellen Speicher an.  Für ARM\-, x86\- und [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\-Computer beträgt die Standardstapelgröße 1 MB.  
  
 Wie das `commit`\-Argument interpretiert wird, hängt vom jeweiligen Betriebssystem ab.  Unter Windows RT wird damit die physische Speichermenge bezeichnet, die zu einem Zeitpunkt belegt werden soll.  Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei.  Ein höherer `commit`\-Wert spart Zeit, wenn die Anwendung mehr Stapelspeicher benötigt, erhöht aber auch den Arbeitsspeicherbedarf und möglicherweise die Startzeit.  Für ARM\-, x86\- und [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\-Computer beträgt der Standardcommitwert 4 KB.  
  
 Geben Sie die Werte für `reserve` und `commit` dezimal oder in C\-Notation an.  
  
 Die Stapelgröße kann auch mit der Anweisung [STACKSIZE](../../build/reference/stacksize.md) in einer Moduldefinitionsdatei \(DEF\-Datei\) festgelegt werden.  **STACKSIZE** überschreibt die Speicherbelegungsoption \/STACK, wenn beide Optionen angegeben sind.  Sie können nach Erstellung einer EXE\-Datei die Stapelgröße mit dem Tool [EDITBIN](../../build/reference/editbin-reference.md) ändern.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **System** aus.  
  
4.  Ändern Sie eine der folgenden Eigenschaften:  
  
    -   **StackCommitSize**  
  
    -   **StackReserveSize**  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)