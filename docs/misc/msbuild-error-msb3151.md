---
title: "MSBuild Error MSB3151"
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
  - "MSBuild.GenerateBootstrapper.IncludedProductIncluded"
helpviewer_keywords: 
  - "MSB3151"
ms.assetid: e4766734-2e90-436e-850b-a8a9da535dee
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3151
**MSB3151: \<Paket\> ist bereits im \<Paket\>\-Element enthalten.**  
  
 Diese Warnung wird ausgegeben, wenn Sie zwei Bootstrapperpakete ausgewählt haben, wobei ein Paket in dem anderen enthalten ist. \(Durch die Auswahl des enthaltenen Pakets geben Sie dieses doppelt an.\)  
  
### So beheben Sie diesen Fehler  
  
-   Deaktivieren Sie das Kontrollkästchen für das überflüssig eingeschlossene Paket.