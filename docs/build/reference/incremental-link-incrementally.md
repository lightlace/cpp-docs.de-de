---
title: "/INCREMENTAL (inkrementell verkn&#252;pfen)"
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
  - "/incremental"
  - "VC.Project.VCLinkerTool.LinkIncremental"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCREMENTAL (Linkeroption)"
  - "INCREMENTAL (Linkeroption)"
  - "-INCREMENTAL (Linkeroption)"
  - "Inkrementelle Verknüpfung"
  - "Inkrementell verknüpfen (Option)"
  - "LINK-Tool [C++], Optionen für vollständiges Verknüpfen"
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /INCREMENTAL (inkrementell verkn&#252;pfen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCREMENTAL[:NO]  
```  
  
## Hinweise  
 Steuert, wie der Linker inkrementelle Verknüpfungen behandelt.  
  
 Standardmäßig wird der Linker im inkrementellen Modus ausgeführt.  Um einen inkrementellen Standardlink zu überschreiben, müssen Sie "\/INCREMENTAL:NO" angeben.  
  
 Ein inkrementell verknüpftes Programm ist funktional gleichwertig mit einem Programm, das nicht inkrementell verknüpft wurde.  Da eine inkrementell verknüpfte ausführbare Datei \(EXE\-Datei\) oder DLL jedoch für spätere inkrementelle Links vorbereitet ist, gilt für sie Folgendes:  
  
-   Sie ist größer als ein nicht inkrementell verknüpftes Programm, da Code und Daten ergänzt werden. \(Die Auffüllung ermöglicht es dem Linker, die Größe von Funktionen und Daten zu erhöhen, ohne die EXE\-Datei neu erstellen zu müssen.\)  
  
-   Sie kann Sprung\-Thunks enthalten, um das Verschieben von Funktionen auf neue Adressen zu verarbeiten.  
  
    > [!NOTE]
    >  Um sicherzustellen, dass das Releasebuild keine Füllzeichen oder Thunks enthält, sollten Sie Ihr Programm nicht inkrementell verknüpfen.  
  
 Um unabhängig von der Standardeinstellung die inkrementelle Verknüpfung vorzunehmen, müssen Sie "\/INCREMENTAL" angeben.  Wenn diese Option gewählt wurde, gibt der Linker eine Warnung aus, falls er keine inkrementelle Verknüpfung durchführen kann, und verknüpft dann das Programm nicht inkrementell.  Bei bestimmten Optionen und in bestimmten Situationen wird "\/INCREMENTAL" überschrieben.  
  
 Die meisten Programme können inkrementell verknüpft werden.  Einige Änderungen sind jedoch zu umfangreich, und bestimmte Optionen sind mit dem inkrementellen Verknüpfen nicht kompatibel.  LINK führt einen vollständigen Verknüpfungsvorgang durch, wenn eine der folgenden Optionen angegeben wurde:  
  
-   Inkrementell verknüpfen wurde nicht ausgewählt \("\/INCREMENTAL:NO"\).  
  
-   "\/OPT:REF" wurde ausgewählt.  
  
-   "\/OPT:ICF" wurde ausgewählt.  
  
-   "\/OPT:LBR" wurde ausgewählt.  
  
-   "\/ORDER" wurde ausgewählt.  
  
 Beim Festlegen von [\/DEBUG](../../build/reference/debug-generate-debug-info.md) wird "\/INCREMENTAL" impliziert.  
  
 Außerdem führt "LINK" einen vollständigen Verknüpfungsvorgang durch, wenn eine der folgenden Situationen eintritt:  
  
-   Die inkrementelle Statusdatei \(ILK\-Datei\) fehlt. \(LINK erstellt eine neue ILK\-Datei zur Vorbereitung auf spätere inkrementelle Verknüpfungen.\)  
  
-   Es sind keine Schreibrechte für die ILK\-Datei vorhanden. \("LINK" berücksichtigt die ILK\-Datei nicht und verknüpft nicht inkrementell.\)  
  
-   Die EXE\- oder DLL\-Ausgabedatei fehlt.  
  
-   Der Zeitstempel der ILK\-, EXE\- oder DLL\-Datei hat sich geändert.  
  
-   Eine LINK\-Option hat sich geändert.  Die meisten LINK\-Optionen führen, wenn sie zwischen zwei Erstellungsvorgängen geändert werden, zu einer vollständigen Verknüpfung.  
  
-   Eine Objektdatei \(OBJ\-Datei\) wurde hinzugefügt oder ausgelassen.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Allgemein** aus.  
  
4.  Ändern Sie die Eigenschaft **Inkrementelles Verknüpfen aktivieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)