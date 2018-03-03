---
title: TOOLTIPTEXT-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: becbdcfcc6dbd26ae3095de098d12dbc078530cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT-Struktur
Beim Schreiben der [Benachrichtigung QuickInfo-Handler](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), müssen Sie die `TOOLTIPTEXT` Struktur. Die Mitglieder der `TOOLTIPTEXT` Struktur sind:  
  
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
 Identifiziert das Tool an, das Text benötigt. Das einzige Mitglied dieser Struktur, die Sie möglicherweise ist das Steuerelement-Befehls-ID. Die Befehls-ID des Steuerelements werden in der `idFrom` Mitglied der `NMHDR` -Struktur, mit der Syntax zugegriffen `hdr.idFrom`. Finden Sie unter [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) eine Erläuterung der Mitglieder der `NMHDR` Struktur.  
  
 `lpszText`  
 Die Adresse einer Zeichenfolge in den Text für ein Tool zu erhalten.  
  
 `szText`  
 Der Puffer, der den QuickInfo-Text empfängt. Eine Anwendung kann den Text in diesem Puffer als Alternative zum Angeben einer Zeichenfolge Adresse kopieren.  
  
 `hinst`  
 Handle der Instanz, die eine Zeichenfolge als den QuickInfo-Text zu verwendende enthält. Wenn `lpszText` ist die Adresse von den QuickInfo-Text, dieses Element NULL ist.  
  
 Bei der Behandlung der `TTN_NEEDTEXT` Benachrichtigung angezeigt wird, geben Sie die Zeichenfolge, die in einem der folgenden Methoden angezeigt werden:  
  
-   Kopieren Sie den Text in den Puffer, die gemäß der `szText` Member.  
  
-   Kopieren Sie die Adresse des Puffers, der Text enthält, die `lpszText` Member.  
  
-   Kopieren Sie den Bezeichner der zu einer Zeichenfolgenressource der `lpszText` Element, und kopieren Sie das Handle für die Instanz, die die Ressource enthält die `hinst` Member.  
  
## <a name="see-also"></a>Siehe auch  
 [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

