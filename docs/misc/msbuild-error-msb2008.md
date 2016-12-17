---
title: "MSBuild Error MSB2008"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.UnrecognizedChildElement"
helpviewer_keywords: 
  - "MSB2008"
ms.assetid: 3c2afda0-a116-4b2f-af0c-c0f0d1541325
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB2008
**Mit diesem Visual Studio\-Projektsystem können keine "{0}"\-Projekte konvertiert werden.  Mit diesem System können nur C\#\- und VB\-Clientprojekte konvertiert werden.**  
  
 Nur gültige [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\- und [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\-Projekte können mit [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] konvertiert werden.  
  
### So beheben Sie diesen Fehler  
  
-   Wenn das Projekt ein [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\- oder [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\-Projekt ist, überprüfen Sie, ob die Projektdatei geändert wurde oder beschädigt ist.  Wenn sie geändert wurde oder beschädigt ist, öffnen Sie das Projekt in der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Version, in der es erstellt wurde, speichern Sie es, und versuchen Sie dann erneut, es zu konvertieren.  
  
-   Wenn das Projekt kein [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\- oder [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\-Projekt ist, konvertieren Sie es mit dem entsprechenden Tool.  
  
## Siehe auch  
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)