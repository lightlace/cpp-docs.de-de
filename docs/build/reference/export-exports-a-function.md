---
title: "/EXPORT (Funktion exportieren)"
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
  - "VC.Project.VCLinkerTool.ExportFunctions"
  - "/export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXPORT (Linkeroption)"
  - "EXPORT (Linkeroption)"
  - "-EXPORT (Linkeroption)"
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /EXPORT (Funktion exportieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## Hinweise  
 Mithilfe dieser Option können Sie eine Funktion aus Ihrem Programm exportieren, damit andere Programme die Funktion aufrufen können.  Sie können Daten auch exportieren.  Exporte werden gewöhnlich in einer DLL definiert.  
  
 *entryname* entspricht dem Namen der Funktion oder des Datenelements, der vom aufrufenden Programm verwendet werden muss.  Mit `ordinal` wird ein Index in die Exporttabelle im Bereich 1 bis 65.535 geschrieben. Falls Sie `ordinal` nicht angeben, wird eine Ordnungszahl von LINK zugewiesen.  Durch das **NONAME**\-Schlüsselwort wird die Funktion ohne *entryname* nur als Ordnungszahl exportiert.  
  
 Das Schlüsselwort **DATA** legt fest, dass das exportierte Element ein Datenelement ist.  Das Datenelement im Clientprogramm muss mithilfe von **extern \_\_declspec\(dllimport\)** deklariert werden.  
  
 Es gibt drei Methoden zum Exportieren einer Definition. Sie sind in der Reihenfolge aufgeführt, in der sie verwendet werden sollten:  
  
1.  [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) im Quellcode  
  
2.  Eine [EXPORTS](../../build/reference/exports.md)\-Anweisung in einer DEF\-Datei  
  
3.  Eine **\/EXPORT**\-Spezifikation in einem **LINK**\-Befehl  
  
 Es ist möglich, alle drei Methoden im selben Programm einzusetzen.  Wenn LINK ein Programm erstellt, das Exporte enthält, wird auch eine Importbibliothek erstellt, es sei denn, bei der Erstellung wird eine EXP\-Datei verwendet.  
  
 **LINK** verwendet die ergänzten Formen von Bezeichnern.  Vom Compiler wird den Bezeichnern beim Erstellen der OBJ\-Datei eine Ergänzung hinzugefügt.  Wenn der Platzhalter *entryname* dem Linker in der nicht ergänzten Form \(wie er im Quellcode angezeigt wird\) angegeben wird, dann versucht **LINK**, den Namen zuzuordnen.  Wenn keine eindeutige Übereinstimmung ermittelt werden kann, gibt **LINK** eine Fehlermeldung aus.  Mit dem [DUMPBIN](../../build/reference/dumpbin-reference.md)\-Tool können Sie die [ergänzten Namen](../../build/reference/decorated-names.md) von Bezeichnern abrufen, wenn Sie diese dem Linker angeben müssen.  
  
> [!NOTE]
>  Geben Sie C\-Bezeichner, die als `__cdecl` oder `__stdcall` deklariert wurden, ohne Namensergänzung an.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)