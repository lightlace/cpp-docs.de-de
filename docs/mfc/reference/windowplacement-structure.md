---
title: "WINDOWPLACEMENT-Struktur"
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
  - "WINDOWPLACEMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPLACEMENT-Struktur"
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# WINDOWPLACEMENT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `WINDOWPLACEMENT`\-Struktur enthält Informationen über die Position eines Fensters auf dem Bildschirm**.**  
  
## Syntax  
  
```  
  
      typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
   UINT length;  
   UINT flags;  
   UINT showCmd;  
   POINT ptMinPosition;  
   POINT ptMaxPosition;  
   RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### Parameter  
 *length*  
 Gibt die Länge, in Bytes, Struktur an**.**  
  
 `flags`  
 Gibt Flags an, die die Position des Fensters minimierten \- Methode steuern, durch die das Fenster wiederhergestellt wird.  Dieser Member kann eine oder beide der folgenden Flags sein:  
  
-   **WPF\_SETMINPOSITION** gibt an, dass die X\- und Y\-Positionen minimierten des Fensters spezifizierter angegeben sein können**.** Dieses Flag muss angegeben werden, wenn die Koordinaten in den **ptMinPosition**\-Member festgelegt werden.  
  
-   **WPF\_RESTORETOMAXIMIZED** gibt, dass das wiederhergestellte Fenster maximiert wird, unabhängig davon, ob es maximiert war, bevor minimiert wurde.  Diese Einstellung ist nur gültig, nächsten wenn das Fenster wiederhergestellt wird.  Sie wird nicht das Standardwiederherstellungsverhalten.  Dieses Flag ist nur gültig, wenn der **SW\_SHOWMINIMIZED**\-Wert **showCmd** für den Member angegeben wird.  
  
 *showCmd*  
 Gibt den aktuellen Anzeigezustand des Fensters an.  Dieser Member kann einer der folgenden Werte sein:  
  
-   **SW\_HIDE** blendet das Fenster aus und führt Aktivierung an einen anderen Fenster.  
  
-   **SW\_MINIMIZE** minimiert das angegebene Fenster und aktiviert das Fenster der obersten Ebene in der Liste des Systems.  
  
-   **SW\_RESTORE** ermöglicht und wird ein Fenster gezeigt.  Wenn das Fenster minimiert oder maximiert ist, stellt Windows es in seine Originalgröße und die Position zurückgesetzt \(gleicher wie **SW\_SHOWNORMAL**\).  
  
-   **SW\_SHOW** kann ein Fenster und wird in der aktuellen Größe und Position in an.  
  
-   **SW\_SHOWMAXIMIZED** kann ein Fenster und wird als maximiertes Fenster an.  
  
-   **SW\_SHOWMINIMIZED** kann ein Fenster und wird als Symbol an.  
  
-   **SW\_SHOWMINNOACTIVE** wird ein Fenster als Symbol an.  Das Fenster, das derzeit aktiv bleibt aktiv.  
  
-   **SW\_SHOWNA** wird ein Fenster in ihrem aktuellen Zustand her.  Das Fenster, das derzeit aktiv bleibt aktiv.  
  
-   **SW\_SHOWNOACTIVATE** wird ein Fenster in der aktuellen Größe und Position in an.  Das Fenster, das derzeit aktiv bleibt aktiv.  
  
-   **SW\_SHOWNORMAL** ermöglicht und wird ein Fenster gezeigt.  Wenn das Fenster minimiert oder maximiert ist, stellt Windows es in seine Originalgröße und die Position zurückgesetzt \(gleicher wie **SW\_RESTORE**\).  
  
 *ptMinPosition*  
 Gibt die Position der oberen linken Ecke des Fensters, wenn das Fenster minimiert wird.  
  
 `ptMaxPosition`  
 Gibt die Position der oberen linken Ecke des Fensters, wenn das Fenster maximiert wird.  
  
 *rcNormalPosition*  
 Gibt die Koordinaten des Fensters, wenn das Fenster in der normalen Position \(wiederhergestellten\) ist.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../Topic/CWnd::SetWindowPlacement.md)