---
title: TOOLTIPTEXT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82c06b98acec18e845fd1353875c1453c4bee8b1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097158"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT-Struktur
Schreiben Ihrer [QuickInfo-Benachrichtigungshandler](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), müssen Sie die **TOOLTIPTEXT** Struktur. Die Mitglieder der **TOOLTIPTEXT** -Struktur sind:  
  
```cpp
typedef struct {
    NMHDR     hdr;        // required for all WM_NOTIFY messages
    LPTSTR    lpszText;   // see below
    TCHAR     szText[80]; // buffer for tool tip text
    HINSTANCE hinst;      // see below
    UINT      uflags;     // flag indicating how to interpret the
                          // idFrom member of the NMHDR structure
                          // that is included in the structure
} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;
```
  
 *HDR*  
 Identifiziert das Tool, das Text benötigt. Das einzige Mitglied dieser Struktur, die Sie möglicherweise ist das Steuerelement die Befehls-ID Befehls-ID des Steuerelements befinden sich in der *IdFrom* Mitglied der **NMHDR** Struktur, die mit der Syntax zugegriffen `hdr.idFrom`. Finden Sie unter [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) eine Erläuterung der Mitglieder der **NMHDR** Struktur.  
  
 *lpszText*  
 Die Adresse einer Zeichenfolge in den Text für ein Tool zu erhalten.  
  
 *szText*  
 Puffer, der den QuickInfo-Text empfängt. Eine Anwendung kann den Text für diesen Puffer als Alternative zur Angabe einer Adresse Zeichenfolge kopieren.  
  
 *hinst*  
 Handle der Instanz, die eine Zeichenfolge als den QuickInfo-Text verwendet werden soll. Wenn *LpszText* ist die Adresse, der den QuickInfo-Text, dieses Element NULL ist.  
  
Bei der Behandlung der `TTN_NEEDTEXT` Benachrichtigung angezeigt wird, geben Sie die Zeichenfolge, die in einem der folgenden Arten angezeigt werden:  
  
-   Kopieren Sie den Text in den Puffer, die gemäß der *SzText* Member.  
  
-   Kopieren Sie die Adresse des Puffers, der den Text enthält die *LpszText* Member.  
  
-   Kopieren Sie den Bezeichner der Ressource, eine Zeichenfolge, die *LpszText* Member, und kopieren Sie das Handle der Instanz, die die Ressource enthält die *Hinst* Member.  
  
## <a name="see-also"></a>Siehe auch  
 [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

