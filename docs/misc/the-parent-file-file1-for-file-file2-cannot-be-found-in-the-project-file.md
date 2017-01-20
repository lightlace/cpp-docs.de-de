---
title: "The parent file, &#39;file1&#39;, for file &#39;file2&#39; cannot be found in the project file"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.projfile_missing_dependency"
ms.assetid: 1902c0b5-d09d-49b9-8f71-e325f7b9cfd7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# The parent file, &#39;file1&#39;, for file &#39;file2&#39; cannot be found in the project file
Das Projektsystem kann den entsprechenden Knoten für eine Datei nicht finden.  
  
 Abhängige Dateien bleiben in der Projektdatei erhalten, indem ein `DependentUpon`\-Attribut zum `<File>`\-Knoten hinzugefügt wird.  Beispiele:  
  
```  
<File  
    RelPath = "Form1.resx"  
    SubType = "Code"  
    BuildAction = "EmbeddedResource"  
    DependentUpon="Form1.vb"  
/>  
```  
  
 Dadurch wird **Form1.resx** unter **Form1.vb** in der Projekthierarchie aufgeführt.  
  
 Dieser Fehler wird meistens durch das manuelle Bearbeiten der Projektdatei verursacht.  
  
### So beheben Sie diesen Fehler  
  
-   Bearbeiten und aktualisieren Sie die Projektdatei.  
  
     Die betroffenen Dateien werden dem Projekt hinzugefügt, jedoch wird die Abhängigkeit nicht erhalten.  
  
## Siehe auch  
 [NIB: Project Properties \(Visual Studio\)](assetId:///eb4c97ed-f667-4850-98d0-6e2a4d21bbca)