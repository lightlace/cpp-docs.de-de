---
title: "/VERSION (Versionsinformationen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Version"
  - "/version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/VERSION (Linkeroption)"
  - "Versionsinformationen (Linkeroption)"
  - "VERSION (Linkeroption)"
  - "-VERSION (Linkeroption)"
  - "Versionsnummern, Angeben in .exe"
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /VERSION (Versionsinformationen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/VERSION:major[.minor]  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *major* und *minor*  
 die Versionsnummer, die im Header der EXE\- oder DLL\-Datei enthalten sein soll.  
  
## Hinweise  
 Die \/VERSION\-Option weist den Linker an, eine Versionsnummer im Header der EXE\- oder DLL\-Datei zu platzieren.  Mit dem Tool **DUMPBIN**[\/HEADERS](../../build/reference/headers.md) können Sie im Bildversionsfeld von **OPTIONAL HEADER VALUES** die Auswirkung der Option **\/VERSION** überprüfen.  
  
 Die Argumente *major* und *minor* sind Dezimalzahlen im Bereich von 0 bis 65.535.  Die Standardversion ist 0.0.  
  
 Die Informationen, die mit \/VERSION angegebenen werden, wirken sich nicht auf die Versionsinformationen, die für eine Anwendung wird angezeigt, wenn Sie seine Eigenschaften im Datei\-Explorer anzeigen.  Diese Informationen stammen aus einer Ressourcendatei, mit der die Anwendung erstellt wird.  Weitere Informationen finden Sie unter [Versionsinfo\-Editor](../../mfc/version-information-editor.md).  
  
 Eine andere Möglichkeit, eine Versionsnummer einzufügen, besteht im Verwenden der Moduldefinitionsanweisung [VERSION](../../build/reference/version-c-cpp.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Ändern Sie die Eigenschaft **Version**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)