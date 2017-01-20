---
title: "_com_ptr_t::Detach"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::Detach"
  - "_com_ptr_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach-Methode"
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.  
  
## Syntax  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## Hinweise  
 Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück und löscht dann den Speicher des gekapselten Zeigers auf **NULL**.  Dadurch wird der Schnittstellenzeiger aus der Kapselung entfernt.  Sie können entscheiden, ob Sie **Release** für den zurückgegebenen Schnittstellenzeiger aufrufen.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)