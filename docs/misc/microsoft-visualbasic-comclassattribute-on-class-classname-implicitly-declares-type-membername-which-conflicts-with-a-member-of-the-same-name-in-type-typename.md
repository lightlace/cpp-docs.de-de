---
title: "Durch &quot;Microsoft.VisualBasic.ComClassAttribute&quot; in der Klasse &quot;&lt;Klassenname&gt;&quot; wird implizit der &lt;Typ&gt; &quot;&lt;Membername&gt;&quot; deklariert, wodurch ein Konflikt mit einem Member mit demselben Namen im &lt;Typ&gt; &quot;&lt;Typname&gt;&quot; entsteht."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "BC42101"
ms.assetid: 001c8eaa-19b6-44fa-8056-4186ecffbda8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Durch &quot;Microsoft.VisualBasic.ComClassAttribute&quot; in der Klasse &quot;&lt;Klassenname&gt;&quot; wird implizit der &lt;Typ&gt; &quot;&lt;Membername&gt;&quot; deklariert, wodurch ein Konflikt mit einem Member mit demselben Namen im &lt;Typ&gt; &quot;&lt;Typname&gt;&quot; entsteht.
Durch "Microsoft.VisualBasic.ComClassAttribute" in der Klasse "\<Klassenname\>" wird implizit der \<Typ\> "\<Membername\>" deklariert, wodurch ein Konflikt mit einem Member mit demselben Namen im \<Typ\> "\<Typname\>" entsteht. Verwenden Sie "Microsoft.VisualBasic.ComClassAttribute\(InterfaceShadows:\=True\)", wenn Sie den Namen für den grundlegenden "\<Typname\>" ausblenden möchten.  
  
 Eine Klasse, die einen `COMClassAttribute`\-Attributblock verwendet, definiert implizit eine Schnittstelle mit dem gleichen Namen wie ein Member der Basisklasse. In diesem Fall sollte der Basisklassenmember durch den Schnittstellennamen überschattet werden.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC42101  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn Sie den Basisklassenmember ausblenden möchten, legen Sie im `ComClassAttribute`\-Attributblock `InterfaceShadows:=True` fest.  
  
2.  Wenn Sie den Basisklassenmember nicht ausblenden möchten, ändern Sie den Namen der Klasse.  
  
## Siehe auch  
 [NICHT IM BUILD: In Visual Basic verwendete Attribute](assetId:///22231318-8a40-49af-9245-e0aab723563b)   
 [NICHT IM BUILD: Anwendung von Attributen](assetId:///2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute\-Klasse](assetId:///5c2f0835-9210-47dc-bc59-5c1769953574)   
 [ComClassAttribute.InterfaceShadows\-Eigenschaft](assetId:///0fae25bd-e0ba-4755-a76c-3b526b1ac795)