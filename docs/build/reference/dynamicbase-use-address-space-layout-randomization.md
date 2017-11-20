---
title: -DYNAMICBASE (Verwendung Adresse Space Layout Randomization) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.RandomizedBaseAddress
dev_langs: C++
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2bce480d906210ebd8eb597902c7f1aac855c6ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (Address Space Layout Randomization verwenden)
Gibt an, ob ein ausführbares Image generiert werden, die nach dem Zufallsprinzip zur Ladezeit ein REBASE werden können Address Space Layout Randomization (ASLR)-Funktion von [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
## <a name="syntax"></a>Syntax  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig ist "/ DynamicBase" auf.  
  
 Diese Option ändert den Header einer ausführbaren Datei, um anzugeben, ob die Anwendung nach dem Zufallsprinzip zur Ladezeit zurückgesetzt werden soll.  
  
 Adresse Space Layout Randomization wird unterstützt, auf [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
5.  Ändern der **Zufällige Basisadresse** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)