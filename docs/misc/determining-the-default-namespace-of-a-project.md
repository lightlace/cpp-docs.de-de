---
title: "Ermitteln des Standardnamespaces eines Projekts"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Benutzerdefinierte Tools, Standardnamespace berechnen"
ms.assetid: 6d890676-7016-458c-8a6a-95cc0a068612
caps.latest.revision: 13
caps.handback.revision: "13"
manager: "douge"
---
# Ermitteln des Standardnamespaces eines Projekts
Für [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]wenn die `CustomToolNamespace`\-Eigenschaft in der Eingabedatei festgelegt ist, wird der Wert von `CustomToolNamespace` wird der Wert des Standardnamespace <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate*>\-Parameters, der an die Methode übergeben wird.  Andernfalls ist der `wszDefaultNamespace`\-Parameter, der auf `Generate` übergeben wird, immer dem Stammnamespace.  Weitere Informationen über Namespaces finden Sie unter [Namespaceschlüsselwörter](../Topic/Namespace%20Keywords%20\(C%23%20Reference\).md).  
  
 [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] verwendet Ordner\-basierte Namespaces.  Anders gesagt besteht der Namespace aus dem Stammnamespace plus Namen aller Ordner, die das benutzerdefinierte Tool enthalten.  Jeder Ordnername wird in einen gültigen Bezeichner umgewandelt, und trennen alle Namen.  Wenn z. B. die Eingabedatei FolderA \\ FolderB \\ FolderC \\ MyInput.txt und der Stammnamespace entspricht, würde der berechnete CL9 Standardnamespace **CL9.FolderA.FolderB.FolderC**sein.  
  
 Eine Ausnahme von dieser Regel tritt auf, wenn die Hierarchien Kette einen Ordner Webverweise enthält.  Wenn z. B. Folgendes gegeben ist:  
  
-   FolderC war ein Ordner Webverweise, wäre der Namespace **CL9.FolderC**.  
  
-   FolderB war ein Ordner Webverweise, wäre der Namespace **CL9.FolderB.FolderC**.  
  
 Das heißt, wird der Namespace im folgenden Format:  
  
```  
rootNamespace.webReferenceFolder.containedFolder.containedFolder ...  
```  
  
## Siehe auch  
 [Implementieren von Einzeldatei\-Generatoren](../Topic/Implementing%20Single-File%20Generators.md)   
 [Registrieren von Einzeldatei\-Generatoren](../Topic/Registering%20Single%20File%20Generators.md)   
 [\-Typen für visuelle Designer verfügbar gemacht](../Topic/Exposing%20Types%20to%20Visual%20Designers.md)