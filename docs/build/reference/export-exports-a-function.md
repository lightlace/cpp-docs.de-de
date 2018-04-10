---
title: -EXPORT (Funktion exportieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2183a67679fc216396d03ac31a5a11db8d011454
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="export-exports-a-function"></a>/EXPORT (Funktion exportieren)
```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit dieser Option können Sie eine Funktion aus Ihrem Programm exportieren, sodass andere Programme die Funktion aufrufen können. Sie können auch Daten exportieren. Exporte werden normalerweise in einer DLL definiert.  
  
 Die *Eintragsname* ist der Name der Funktion oder Daten, der vom aufrufenden Programm verwendet werden. `ordinal`Gibt einen Index in die Exporttabelle im Bereich von 1 bis 65.535. Wenn Sie keinen angeben `ordinal`, LINK weist ein. Die **NONAME** Schlüsselwort exportiert die Funktion nur als Ordnungszahl, ohne eine *Eintragsname*.  
  
 Die **Daten** -Schlüsselwort Gibt an, dass das exportierte Element ein Datenelement ist. Das Datenelement im Clientprogramm muss deklariert werden, mithilfe von **"extern" von "__declspec(dllimport)" "**.  
  
 Es gibt drei Methoden zum Exportieren einer Definition, aufgelistet in empfohlener Reihenfolge von Nutzen:  
  
1.  [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) im Quellcode  
  
2.  Ein [EXPORTE](../../build/reference/exports.md) -Anweisung in DEF-Datei  
  
3.  Eine/Export-Spezifikation in einem LINK-Befehl  
  
 Alle drei Methoden können im selben Programm verwendet werden. Wenn LINK ein Programm, das Exporte enthält erstellt, erstellt er auch eine Importbibliothek, es sei denn, eine .exp-Datei in den Build verwendet wird.  
  
 LINK verwendet die ergänzten Formen von Bezeichnern. Der Compiler ergänzt einen Bezeichner an, wenn es sich um die OBJ-Datei erstellt. Wenn *Eintragsname* angegeben ist, an den Linker in seiner nicht ergänzten form (wie es im Quellcode angezeigt wird), LINK versucht, mit dem Namen übereinstimmen. Wenn sie eine eindeutige Übereinstimmung finden kann, gibt LINK eine Fehlermeldung an. Verwenden der [DUMPBIN](../../build/reference/dumpbin-reference.md) Tool zum Abrufen der [ergänzten Namen](../../build/reference/decorated-names.md) Form eines Bezeichners, wenn Sie es an den Linker angeben müssen.  
  
> [!NOTE]
>  Geben Sie die ergänzte Form des C-Bezeichner, die deklariert wurden keine `__cdecl` oder `__stdcall`.  
  
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