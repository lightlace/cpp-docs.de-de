---
title: "MSG Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSG-Struktur"
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# MSG-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `MSG`\-Struktur enthält Nachrichteninhalt aus der Meldungswarteschlange eines Threads.  
  
## Syntax  
  
```  
  
      typedef struct tagMSG {     // msg    
   HWND hwnd;  
   UINT message;  
   WPARAM wParam;  
   LPARAM lParam;  
   DWORD time;  
   POINT pt;  
} MSG;  
```  
  
#### Parameter  
 *hwnd*  
 Identifiziert das Fenster, dessen Fensterprozedur die Meldung empfängt.  
  
 `message`  
 Gibt die Meldungsnummer an.  
  
 `wParam`  
 Enthält zusätzliche Informationen über die Meldung.  Die genaue Bedeutung hängt vom Wert des **Meldung**\-Members ab.  
  
 `lParam`  
 Enthält zusätzliche Informationen über die Meldung.  Die genaue Bedeutung hängt vom Wert des **Meldung**\-Members ab.  
  
 `time`  
 Angeben der Zeit, zu der die Nachricht gesendet wurde.  
  
 `pt`  
 Gibt der Cursorposition, in Bildschirmkoordinaten an, als die Nachricht gesendet wurde.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)