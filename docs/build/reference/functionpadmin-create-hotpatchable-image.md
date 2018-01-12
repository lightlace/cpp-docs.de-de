---
title: "-FUNCTIONPADMIN (erstellen Hotpatch-fähiges Abbild) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /functionpadmin
dev_langs: C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f737cdb412420ffb87664024b2314941e67b045b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Erstellen eines Hotpatch-fähigen Abbildes)
Bereitet ein Image für Hotpatching vor.  
  
## <a name="syntax"></a>Syntax  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `space` (optional)  
 Die Größe der Auffüllung am Anfang jeder Funktion hinzufügen 5, 6 oder 16.  X86 Images erfordern fünf Byte-Auffüllung, X64 Images erfordern 6 Bytes und für die Itanium-Prozessorfamilie erstellte Images erfordern 16 Byte-Auffüllung am Anfang jeder Funktion.  
  
 Standardmäßig wird der Compiler die richtige Menge an Speicherplatz im Abbild, basierend auf dem Computertyp des Bilds hinzufügen.  
  
 Damit der Linker ein Hotpatch-fähiges Abbild erstellt werden kann, die OBJ-Dateien müssen wurden kompiliert mit [/hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)](../../build/reference/hotpatch-create-hotpatchable-image.md).  
  
 Wenn Sie kompilieren und verknüpfen ein Bild mit einem einzelnen Aufruf von cl.exe, **/hotpatch** impliziert **/functionpadmin**.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)