---
title: "/FIXED (Feste Basisadresse) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/fixed"
  - "VC.Project.VCLinkerTool.FixedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FIXED (Linkeroption)"
  - "FIXED (Linkeroption)"
  - "-FIXED (Linkeroption)"
  - "Bevorzugte Basisadresse für das Laden eines Programms"
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /FIXED (Feste Basisadresse)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FIXED[:NO]  
```  
  
## Hinweise  
 Weist das Betriebssystem an, das Programm nur an seine bevorzugte Basisadresse zu laden.  Wenn diese Basisadresse nicht zur Verfügung steht, lädt das Betriebssystem die Datei nicht.  Weitere Informationen finden Sie unter [\/BASE \(Basisadresse\)](../../build/reference/base-base-address.md).  
  
 Für eine DLL ist "\/FIXED:NO" die Standardeinstellung; bei anderen Projekttypen lautet die Standardeinstellung "\/FIXED".  
  
 Bei Angabe von "\/FIXED" generiert LINK keinen Verschiebungsabschnitt im Programm.  Wenn das Betriebssystem das Programm zur Laufzeit nicht an der angegebenen Adresse laden kann, wird eine Fehlermeldung ausgegeben, und der Ladevorgang wird nicht ausgeführt.  
  
 Bei Angabe von "\/FIXED:NO" wird ein Verschiebungsabschnitt im Programm generiert.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Geben Sie im Feld **Zusätzliche Optionen** den Optionsnamen und die Einstellung ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)