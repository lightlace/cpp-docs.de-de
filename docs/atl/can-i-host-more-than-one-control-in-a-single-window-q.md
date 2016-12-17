---
title: "Can I Host More Than One Control in a Single Window?"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [ATL], hosting multiple"
  - "windows [C++], hosting multiple controls"
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Can I Host More Than One Control in a Single Window?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es ist nicht möglich, mehr als ein Steuerelement in einem einzelnen ATL\-Hostfenster zu hosten.  Jedes Hostfenster wurde entwickelt, um ein Steuerelement auf genau einmal anzuhalten \(dies kann ein einfaches Verfahren zum Behandeln von Meldung Reflektions\- und ProSteuerelementambient\-eigenschaften zu\).  Wenn Sie jedoch den Benutzer benötigen, um mehrere Steuerelemente in einem einzelnen Fenster anzuzeigen, ist es eine einfache Aufgabe, mehrere Hostfenster als untergeordnete Elemente dieses Fensters zu erstellen.  
  
## Siehe auch  
 [Fragen und Antworten zur Steuerelementkapselung](../atl/atl-control-containment-faq.md)