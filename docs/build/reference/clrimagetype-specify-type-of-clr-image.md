---
title: -CLRIMAGETYPE (Angeben des CLR-Images) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs: C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7d8edd6c9e62456e54ac6228f25d7f923a6813c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Angeben des CLR-Bildtyps)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Linker akzeptiert systemeigene Objekte und auch MSIL-Objekte, die mithilfe von kompiliert sind ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md), / CLR: pure oder/clr: safe. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet. Bei der Übergabe gemischter Objekte im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule. Wenn Sie beispielsweise sowohl ein überprüfbares als auch ein reines (safe und pure) Modul an den Linker übergeben, ist die Ausgabedatei rein (pure). Wenn Sie ein systemeigenes Image und ein Image im gemischten Modus übergeben (kompiliert mit **"/ CLR"**), das resultierende Image ein Image im gemischten Modus sein wird.  
  
 Mit /CLRIMAGETYPE können Sie eine niedrige Überprüfbarkeitsstufe angeben, wenn dies erforderlich ist.  
  
 In .NET 4.5 unterstützt /CLRIMAGETYPE eine SAFE32BITPREFERRED-Option. Damit werden im PE-Header des Images Flags gesetzt, die darauf hinweisen, dass MSIL-Objekte überprüfbar sind und auf allen Plattformen ausgeführt werden können, wobei jedoch 32-Bit-Ausführungsumgebungen bevorzugt werden. Mit dieser Option kann eine App auf ARM-Plattformen ausgeführt werden. Sie gibt auch an, dass sie unter WOW64 auf 64-Bit-Betriebssystemen anstatt in der 64-Bit-Ausführungsumgebung ausgeführt werden soll.  
  
 Bei einer .exe, die mit kompiliert wurde **"/ CLR"** oder **/CLR: pure** ausgeführt wird auf einem 64-Bit-Betriebssystem, die Anwendung ausgeführt wird, unter WOW64 ausgeführt, wodurch eine 32-Bit-Anwendung auf einem 64-Bit-Betriebssystem ausgeführt. Wird standardmäßig ein .exe, die kompiliert wird **/CLR: safe** unter 64-Bit-Unterstützung für das Betriebssystem ausgeführt wird. Es ist jedoch möglich, dass eine 32-Bit-Komponente in die überprüfbare Anwendung geladen wird. In diesem Fall schlägt die Ausführung des mit 64-Bit-Unterstützung ausgeführten überprüfbaren Images beim Laden der 32-Bit-Anwendung fehl. Damit ein überprüfbares Image weiterhin ausgeführt werden kann, wenn eine 32-Bit-Komponente auf einem 64-Bit-Betriebssystem geladen wird, verwenden Sie die Option /CLRIMAGETYPE:SAFE32BITPREFERRED. Wenn der Code nicht auf ARM-Plattformen ausgeführt werden muss, können Sie die Option /CLRIMAGETYPE:PURE angeben, um die Metadaten (.corflags) zu ändern, die markieren, dass er unter WOW64 ausgeführt werden soll (wodurch ein eigenes Eingabezeichen ersetzt wird):  
  
 **cl /clr:safe t.cpp /link /clrimagetype:pure /entry:?main@@$$HYMHXZ /subsystem:console**  
  
 Weitere Informationen zum Bestimmen des CLR-Imagetyps einer Datei finden Sie unter [/CLRHEADER](../../build/reference/clrheader.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
5.  Ändern der **CLR-Imagetyps** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)