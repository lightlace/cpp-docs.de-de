---
title: "TOOLTIPTEXT-Struktur"
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
  - "TOOLTIPTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QuickInfos [C++], Benachrichtigungen"
  - "TOOLTIPTEXT-Struktur"
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# TOOLTIPTEXT-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie das [QuickInfobenachrichtigungshandler](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) schreiben, müssen Sie die `TOOLTIPTEXT`\-Struktur verwenden.  Die Member `TOOLTIPTEXT` der Struktur sind:  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 Identifiziert das Tool, das Text erforderlich.  Der einzige Member dieser Struktur, die Sie unter Umständen, lautet die ID der Steuerbefehl  Die Befehls\-ID des Steuerelements ist im `idFrom` müssen Member der Struktur `NMHDR`, zugegriffen mit der Syntax `hdr.idFrom`.  Siehe [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) Erläuterungen zur Member `NMHDR` der Struktur.  
  
 `lpszText`  
 Adresse einer Zeichenfolge, um den Text für ein Tool zu empfangen.  
  
 `szText`  
 Puffern Sie, das den QuickInfo\-Text empfängt.  Eine Anwendung kann den Text in diesem Puffer als Alternative zur Angabe einer Zeichenfolgenadresse kopieren.  
  
 `hinst`  
 Handle die Instanz, die eine als enthält der QuickInfo\-Text verwendet werden, Zeichenfolge.  Wenn `lpszText` die Adresse des QuickInfotexts ist, wird dieser Member NULL.  
  
 Wenn Sie die `TTN_NEEDTEXT` \- Benachrichtigung bearbeiten, die in einer der folgenden Methoden angezeigt werden, Zeichenfolge:  
  
-   Kopieren Sie den Text in den Puffer, der vom `szText`\-Member angegeben wird.  
  
-   Kopieren Sie die Adresse des Puffers, der den Text zum `lpszText`\-Member enthält.  
  
-   Kopieren Sie den Bezeichner einer Zeichenfolgenressource zum `lpszText`\-Member, und kopieren Sie das Handle die Instanz, die die Ressource für den Member `hinst` enthält.  
  
## Siehe auch  
 [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)