---
title: "MSBuild Error MSB3155"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.ProductNotFound"
helpviewer_keywords: 
  - "MSB3155"
ms.assetid: 59bf2293-ef13-4bb1-8f29-5d6966bbe313
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3155
**MSBuild\-Fehler MSB3155: Das Element \<Paket\> konnte in \<Pfad\> nicht gefunden werden.**  
  
 Die Warnung wird ausgegeben, wenn ein Paket mit dem angegebenen <xref:Microsoft.Build.Tasks.Deployment.Bootstrapper.Product.ProductCode*> im Bootstrappercache nicht gefunden werden konnte.  
  
> [!NOTE]
>  Microsoft Data Access Components \(MDAC\) sind nicht mehr als Bootstrapperpaket enthalten.  Sie können von der [Microsoft Windows Update](http://go.microsoft.com/fwlink/?LinkId=86676)\-Website heruntergeladen werden.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Paket aus der Liste der zu installirenden Pakete, oder fügen Sie das Paket dem Cache hinzu.  Vergewissern Sie sich auch, dass das Manifest ordnungsgemäß formatiert ist und gültiger XML\-Code verwendet wird.  
  
## Siehe auch  
 [Referenz zum Produkt\- und Paketschema](../Topic/Product%20and%20Package%20Schema%20Reference.md)   
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)   
 [Dialogfeld "Erforderliche Komponenten"](../Topic/Prerequisites%20Dialog%20Box.md)   
 [Erstellen von Bootstrapperpaketen](../Topic/Creating%20Bootstrapper%20Packages.md)