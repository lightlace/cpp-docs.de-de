---
title: "COM Interop Wrapper Error"
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
  - "vs.tasklisterror.cannotcopyassembly"
  - "Vs.refruntlbimp"
helpviewer_keywords: 
  - "COM Interop Wrapper dialog box"
ms.assetid: 9a9d6374-ee26-4dbc-9e34-e1d90f6254b4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# COM Interop Wrapper Error
Dieses Meldungsfeld wird angezeigt, wenn das Projektsystem einen COM\-Interop\-Wrapper für eine bestimmte Komponente nicht erstellen konnte.  COM\-Interop\-Wrapper werden von der Common Language Runtime \(CLR\) angefordert, um COM\-Komponenten zu verwalten und mit diesen zu kommunizieren.  Weitere Informationen finden Sie unter [COM\-Interoperabilität in Visual Basic und Visual C\#](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md).  
  
 Häufige Ursachen für diesen Fehler sind:  
  
-   Die Typbibliothek für die Komponente ist nicht ordnungsgemäß registriert.  
  
-   Eine Komponente, von der die umschlossene Komponente abhängig ist, konnte nicht auf Ihrem Computer gefunden werden.  
  
 In beiden Fällen müssen Sie sicherstellen, dass die COM\-Komponente auf dem Computer ordnungsgemäß installiert und registriert ist und den Vorgang wiederholen.  
  
> [!TIP]
>  Einen für Ihre spezifische COM\-Komponente veröffentlichten COM\-Interop\-Wrapper finden Sie auch auf der [MSDN\-Website](http://go.microsoft.com/fwlink/?LinkId=3355).  
  
> [!NOTE]
>  COM\-Interop\-Wrapper werden manchmal als „primäre Interop\-Assemblys“ bezeichnet. Diese Begriffe stellen Synonyme dar.  
  
## Siehe auch  
 [Komponentenmodell\-Namespaces in Visual Studio](assetId:///705d0add-0707-44ba-a6de-637381d9c937)   
 [Component Authoring](../Topic/Component%20Authoring.md)   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)   
 [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md)   
 [COM Interoperability in .NET Framework Applications](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md)