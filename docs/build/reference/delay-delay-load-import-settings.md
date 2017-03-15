---
title: "/DELAY (Laden von Importeinstellungen verz&#246;gern) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delay"
  - "VC.Project.VCLinkerTool.DelayNoBind"
  - "VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL"
  - "VC.Project.VCLinkerTool.DelayUnload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY (Linkeroption)"
  - "DELAY (Linkeroption)"
  - "-DELAY (Linkeroption)"
  - "Verzögertes Laden von DLLs, /DELAY (Option)"
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /DELAY (Laden von Importeinstellungen verz&#246;gern)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## Hinweise  
 Die \/DELAY\-Option steuert das [verzögerte Laden](../../build/reference/linker-support-for-delay-loaded-dlls.md) von DLLs:  
  
-   Der UNLOAD\-Qualifizierer weist die Hilfsfunktion für das verzögerte Laden an, das explizite Entladen der DLL zu unterstützen.  Die Importadresstabelle \(IAT\) wird in ihre ursprüngliche Form zurückgesetzt, wodurch IAT\-Zeiger ungültig und überschrieben werden.  
  
     Wenn Sie UNLOAD nicht auswählen, schlägt jeder Aufruf an [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) fehl.  
  
-   Der NOBIND\-Qualifizierer weist den Linker an, keine bindungsfähige IAT in das endgültige Image einzuschließen.  Das Standardverhalten ist, die bindungsfähige IAT für verzögert geladene DLLs zu erstellen.  Das daraus resultierende Image kann nicht statisch gebunden werden.  \(Images mit bindungsfähigen IATs können vor der Ausführung statisch gebunden werden.\) Siehe [\/BIND](../../build/reference/bind.md).  
  
     Wenn die DLL gebunden ist, versucht die Hilfsfunktion, die gebundenen Informationen zu verwenden, statt [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) in jedem der referenzierten Importe aufzurufen.  Wenn entweder der Zeitstempel oder die bevorzugte Adresse nicht mit denen der geladenen DLL übereinstimmt, geht die Hilfsfunktion davon aus, dass die gebundene IAT veraltet ist, und fährt fort, als würde die gebundene IAT nicht existieren.  
  
     NOBIND führt dazu, dass Ihr Programmimage größer ist, kann aber die Ladezeit der DLL beschleunigen.  Wenn Sie nicht beabsichtigen, die DLL zu binden, verhindert NOBIND, dass die gebundene IAT erstellt wird.  
  
 Verwenden Sie die Option [\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md), um das verzögerte Laden von DLLs anzugeben.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie **Konfigurationseigenschaften**, **Linker**, und wählen Sie dann **Erweitert** aus.  
  
3.  Ändern Sie die Eigenschaft **Verzögert geladene DLL**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)