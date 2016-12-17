---
title: "/TLS"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/TLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TLS-dumpbin-Option"
  - "-TLS-dumpbin-Option"
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# /TLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeigt die IMAGE\_TLS\_DIRECTORY\-Struktur einer ausführbaren Datei an.  
  
## Hinweise  
 Mit \/TLS werden das Feld der TLS\-Struktur sowie die Adressen der TLS\-Rückruffunktionen angezeigt.  
  
 Wenn ein Programm keinen lokalen Threadspeicher verwendet, enthält sein Abbild keine TLS\-Struktur.  Weitere Informationen finden Sie unter [Thread](../../cpp/thread.md).  
  
 IMAGE\_TLS\_DIRECTORY wird in winnt.h definiert.  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)