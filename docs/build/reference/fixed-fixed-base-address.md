---
title: -FIXED (Feste Basisadresse) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs: C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 201a0357d182713c473fd3e259e4e9c2a71abf4e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fixed-fixed-base-address"></a>/FIXED (Feste Basisadresse)
```  
/FIXED[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Weist das Betriebssystem an, das Programm nur an seine bevorzugte Basisadresse zu laden. Wenn diese Basisadresse nicht zur Verfügung steht, lädt das Betriebssystem die Datei nicht. Weitere Informationen finden Sie unter [/BASE (Basisadresse)](../../build/reference/base-base-address.md).  
  
 Für eine DLL ist "/FIXED:NO" die Standardeinstellung; bei anderen Projekttypen lautet die Standardeinstellung "/FIXED".  
  
 Bei Angabe von "/FIXED" generiert LINK keinen Verschiebungsabschnitt im Programm. Wenn das Betriebssystem das Programm zur Laufzeit nicht an der angegebenen Adresse laden kann, wird eine Fehlermeldung ausgegeben, und der Ladevorgang wird nicht ausgeführt.  
  
 Bei Angabe von "/FIXED:NO" wird ein Verschiebungsabschnitt im Programm generiert.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Geben Sie den Optionsnamen und festlegen, der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)