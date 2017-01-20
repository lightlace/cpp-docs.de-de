---
title: "Es ist ein Verweis auf die Assembly &#39;&lt;Assemblyname&gt;&#39; erforderlich, die die implementierte Schnittstelle &#39;&lt;Schnittstellenname&gt;&#39; enth&#228;lt."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30009"
  - "bc30009"
helpviewer_keywords: 
  - "BC30009"
ms.assetid: b2dfb89d-7fde-4a8e-ba7f-fe1e59eabaca
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Es ist ein Verweis auf die Assembly &#39;&lt;Assemblyname&gt;&#39; erforderlich, die die implementierte Schnittstelle &#39;&lt;Schnittstellenname&gt;&#39; enth&#228;lt.
Es ist ein Verweis auf die Assembly '\<Assemblyname\>' erforderlich, die die implementierte Schnittstelle '\<Schnittstellenname\>' enthält. Fügen Sie dem Projekt einen Verweis hinzu.  
  
 Die Schnittstelle ist in einer Dynamic Link Library \(DLL\) definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird. Der [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\-Compiler benötigt einen Verweis, um Mehrdeutigkeiten zu vermeiden, falls die Schnittstelle in mehreren DLLs oder Assemblys definiert ist.  
  
 **Fehler\-ID:** BC30009  
  
### So beheben Sie diesen Fehler  
  
-   Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.  
  
## Siehe auch  
 [NIB: Verweisen auf Namespaces und Komponenten](assetId:///568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [Problembehandlung bei fehlerhaften Verweisen](../Topic/Troubleshooting%20Broken%20References.md)