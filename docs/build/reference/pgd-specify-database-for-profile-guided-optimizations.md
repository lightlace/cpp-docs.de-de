---
title: "-PGD (Angeben einer Datenbank für Profilgesteuerte Optimierungen) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb61395d9f3b8c98e17e3683a7c3897b9315d78b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Angeben einer Datenbank für die profilgesteuerte Optimierungen)
/ PGD:`filename`  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `filename`  
 Gibt den Namen der PGD-Datei, die zum Speichern von Informationen zum ausgeführten Programm verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung [/LTCG: PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md), verwenden Sie/PGD, um einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei anzugeben. Wenn Sie/PGD nicht angeben, wird der Name der PGD-Datei wird der Name der Ausgabedatei (.exe oder .dll) identisch sein und erstellt werden, im gleichen Verzeichnis, von dem die Verknüpfung aufgerufen wurde.  
  
 Bei Verwendung von/LTCG: PGOPTIMIZE mit der/PGD Geben Sie den Namen der PGD-Datei zu verwenden, um das optimierte Image zu erstellen.  
  
 Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Optimierung** Eigenschaftenseite.  
  
5.  Ändern der **Profilgesteuerte Datenbank** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)