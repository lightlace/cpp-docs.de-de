---
title: "/SWAPRUN (Linkerausgabe in Auslagerungsdatei laden)"
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
  - "VC.Project.VCLinkerTool.SwapRunFromNet"
  - "/swaprun"
  - "VC.Project.VCLinkerTool.SwapRunFromCD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN (Linkeroption)"
  - "Dateien [C++], LINK"
  - "LINK-Tool [C++], Ausgabe"
  - "Linker [C++], Kopieren der Ausgabe in eine Auslagerungsdatei"
  - "Ausgabedateien, Linker"
  - "Auslagerungsdatei für Linker-Ausgabe"
  - "SWAPRUN (Linkeroption)"
  - "-SWAPRUN (Linkeroption)"
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /SWAPRUN (Linkerausgabe in Auslagerungsdatei laden)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{NET|CD}  
```  
  
## Hinweise  
 Die \/SWAPRUN\-Option teilt dem Betriebssystem mit, dass zuerst die Linkerausgabe in eine Auslagerungsdatei kopiert und das Image anschließend von dort aus ausgeführt wird.  Dies ist eine Funktion von Windows NT 4.0 \(oder höher\).  
  
 Ist NET angegeben, kopiert das Betriebssystem zuerst das Binärimage vom Netzwerk in eine Auslagerungsdatei und lädt es von dort.  Diese Option ist beim Ausführen von Anwendungen über das Netzwerk hilfreich.  Wenn **CD** angegeben wird, kopiert das Betriebssystem das Bild in eine Auslagerungsdatei auf einem wechselbaren Datenträger und lädt es dann.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **System**.  
  
4.  Ändern Sie eine der folgenden Eigenschaften:  
  
    -   **Wechseln zum Ausführen von der CD\-ROM**  
  
    -   **Wechseln zum Ausführen vom Netz**  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)