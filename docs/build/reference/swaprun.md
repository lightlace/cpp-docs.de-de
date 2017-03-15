---
title: "/SWAPRUN | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/swaprun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN (editbin-Option)"
  - "SWAPRUN (editbin-Option)"
  - "-SWAPRUN (editbin-Option)"
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /SWAPRUN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{[!]NET|[!]CD}  
```  
  
## Hinweise  
 Mit dieser Option wird das Abbild so bearbeitet, dass das Betriebssystem angewiesen wird, das Abbild in eine Auslagerungsdatei zu kopieren und von dort aus auszuführen.  Verwenden Sie diese Option für Abbilder, die in Netzwerken oder auf Wechselmedien gespeichert sind.  
  
 Sie können die **NET**\- oder **CD**\-Qualifizierer hinzufügen oder entfernen:  
  
-   **NET** weist darauf hin, dass sich das Abbild in einem Netzwerk befindet.  
  
-   **CD** weist darauf hin, dass sich das Abbild auf einer CD\-ROM oder einem vergleichbaren Wechselmedium befindet.  
  
-   Verwenden Sie **\!NET** und **\!CD**, um die Auswirkungen von **NET** und **CD** umzukehren.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)