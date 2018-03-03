---
title: -CLRTHREADATTRIBUTE (Set CLR-Threadattributs) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
dev_langs:
- C++
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1aae2dadc2fa7a8c9dc67780bb88b4da60d256e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (Festlegen des CLR-Threadattributs)
Geben Sie explizit das Threadingattribut für den Einstiegspunkt des CLR-Programms.  
  
## <a name="syntax"></a>Syntax  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### <a name="parameters"></a>Parameter  
 MTA  
 Das MTAThreadAttribute-Attribut für den Einstiegspunkt des Programms angewendet.  
  
 KEINE  
 Identisch mit/CLRTHREADATTRIBUTE nicht angeben.  Ermöglicht das Festlegen des standardmäßigen Threadingattribut Common Language Runtime (CLR).  
  
 STA  
 Das STAThreadAttribute-Attribut für den Einstiegspunkt des Programms angewendet.  
  
## <a name="remarks"></a>Hinweise  
 Festlegen der Thread-Attribut gilt nur beim Erstellen einer .exe wie sie den Einstiegspunkt des Hauptthreads wirkt sich auf.  
  
 Bei Verwendung der Standardeinstiegspunkt ("Main" oder "z. B." wmain "") Geben Sie dem Threadingmodell entweder mithilfe von/CLRTHREADATTRIBUTE oder durch Platzieren der threading Attribut (STAThreadAttribute oder MTAThreadAttribute) für die Standard-Eintrag-Funktion.  
  
 Wenn Sie einen nicht standardmäßigen Einstiegspunkt verwenden, geben Sie das Threadingmodell entweder mithilfe von/CLRTHREADATTRIBUTE oder durch das Platzieren des für die Funktion nicht standardmäßiger Eintrag Attribut, und geben Sie den nicht standardmäßigen Einstiegspunkt mit [/Entry](../../build/reference/entry-entry-point-symbol.md) .  
  
 Wenn im Quellcode angegebene Threadingmodell nicht mit/CLRTHREADATTRIBUTE angegebenen Threadingmodell übereinstimmt, wird der Linker/CLRTHREADATTRIBUTE ignorieren und Anwenden des Threadingmodells im Quellcode angegeben.  
  
 Es wird mit Single-threading, z. B. erforderlich sein, wenn CLR-Programms ein COM-Objekt gehostet wird, einzelne threading genutzt.  Wenn die CLR verwendet Multithreading programmieren, kann nicht es ein COM-Objekts hosten, das einzelnen threading verwendet.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
5.  Ändern der **CLR-Thread-Attribut** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)