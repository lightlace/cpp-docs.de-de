---
title: -MANIFEST (Erstellen von Seite-an-Seite-Assemblymanifest) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateManifest
dev_langs: C++
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb26957109a558b48d6252e042e9082f7357fbd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Erstellen eines Manifests für eine parallele Assembly)
```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## <a name="remarks"></a>Hinweise  
 /MANIFEST gibt an, dass der Linker eine parallele Manifestdatei erstellen soll. Weitere Informationen über Manifestdateien finden Sie unter [Manifestdateienreferenz](http://msdn.microsoft.com/library/aa375632).  
  
 Die Standardeinstellung ist "/MANIFEST".  
  
 Die /MANIFEST:EMBED-Option gibt an, dass der Linker die Manifestdatei im Image als Ressource vom Typ "RT_MANIFEST" einbetten soll. Der optionale `ID`-Parameter ist die Ressourcen-ID, die für das Manifest verwendet werden soll. Verwenden Sie den Wert 1 für eine ausführbare Datei. Verwenden Sie den Wert 2 für eine DLL, damit diese private Abhängigkeiten angeben kann. Wenn der `ID`-Parameter nicht angegeben wird, ist der Standardwert 2, wenn die /DLL-Option festgelegt wird; andernfalls ist der Standardwert 1.  
  
 Ab Visual Studio 2008 enthalten Manifestdateien für ausführbare Dateien einen Abschnitt, der Informationen zur Benutzerkontensteuerung (UAC) angibt. Wenn Sie "/ manifest", aber keines von beiden angeben [/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) noch [/DLL](../../build/reference/dll-build-a-dll.md), standardmäßige UAC-Fragment, das auf der Ebene UAC festgelegt ist *AsInvoker* in das Assemblymanifest eingefügt wird. Weitere Informationen über UAC-Ebenen finden Sie unter [/MANIFESTUAC (bettet UAC-Informationen in Manifest)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Um das UAC-Standardverhalten zu ändern, führen Sie einen der folgenden Schritte aus:  
  
-   Geben Sie die /MANIFESTUAC-Option an, und legen Sie die UAC-Ebene auf den gewünschten Wert fest.  
  
-   Oder geben Sie die /MANIFESTUAC:NO-Option an, wenn Sie im Manifest kein UAC-Fragment generieren möchten.  
  
 Wenn Sie nicht "/ manifest" angeben, aber geben Sie [/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) Kommentare, wird eine Manifestdatei erstellt. Wenn Sie "/MANIFEST:NO" angeben, wird keine Manifestdatei erstellt.  
  
 Wenn Sie "/MANIFEST" angeben, wird der Name der Manifestdatei aus dem Namen der Ausgabedatei und der Endung .MANIFEST zusammengesetzt. Wenn die Ausgabedatei beispielsweise "MyFile.exe" heißt, hat die Manifestdatei den Namen "MyFile.exe.manifest".  Wenn Sie/ManifestFile:*Namen*, der Namen des Manifests ist angeben *Namen*.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Manifestdatei** Eigenschaftenseite.  
  
5.  Ändern der **Manifest generieren** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)