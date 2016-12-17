---
title: "PAINTSTRUCT-Struktur"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "PAINTSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PAINTSTRUCT-Struktur"
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# PAINTSTRUCT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `PAINTSTRUCT`\-Struktur enthält Informationen, die verwendet werden können, um den Clientbereich eines Fensters zu zeichnen.  
  
## Syntax  
  
```  
  
      typedef struct tagPAINTSTRUCT {  
   HDC hdc;  
   BOOL fErase;  
   RECT rcPaint;  
   BOOL fRestore;  
   BOOL fIncUpdate;  
   BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### Parameter  
 *hdc*  
 Identifiziert den zum Zeichnen verwendet werden Anzeigekontext.  
  
 *fErase*  
 Gibt an, ob der Hintergrund neu gezeichnet werden muss.  Er ist nicht 0, wenn die Anwendung den Hintergrund neu zeichnet.  Die Anwendung ist für das Zeichnen des Hintergrunds zuständig, wenn eine Windows\-Fensterklasse ohne einen Hintergrundpinsel erstellt wird \(siehe die Beschreibung des **hbrBackground**\-Members [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) der Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\).  
  
 *rcPaint*  
 Gibt das obere links und unteren rechten Ecken des Rechtecks angezeigt, in dem das Zeichnen angefordert wird.  
  
 *fRestore*  
 Reservierter Member.  Es wird intern von Windows verwendet.  
  
 *fIncUpdate*  
 Reservierter Member.  Es wird intern von Windows verwendet.  
  
 *rgbReserved \[16\]*  
 Reservierter Member.  Ein reservierter Speicherblock intern verwendet von Windows.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)