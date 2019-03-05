---
title: TOOLTIPTEXT-Struktur
ms.date: 11/04/2016
f1_keywords:
- TOOLTIPTEXT
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
ms.openlocfilehash: 7d77ca7dc55273e6084e919323ed71e55fa68a2c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260594"
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

*hdr*<br/>
Identifiziert das Tool, das Text benötigt. Das einzige Mitglied dieser Struktur, die Sie möglicherweise ist das Steuerelement die Befehls-ID Befehls-ID des Steuerelements befinden sich in der *IdFrom* Mitglied der **NMHDR** Struktur, die mit der Syntax zugegriffen `hdr.idFrom`. Finden Sie unter [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) eine Erläuterung der Mitglieder der **NMHDR** Struktur.

*lpszText*<br/>
Die Adresse einer Zeichenfolge in den Text für ein Tool zu erhalten.

*szText*<br/>
Puffer, der den QuickInfo-Text empfängt. Eine Anwendung kann den Text für diesen Puffer als Alternative zur Angabe einer Adresse Zeichenfolge kopieren.

*hinst*<br/>
Handle der Instanz, die eine Zeichenfolge als den QuickInfo-Text verwendet werden soll. Wenn *LpszText* ist die Adresse, der den QuickInfo-Text, dieses Element NULL ist.

Bei der Behandlung der `TTN_NEEDTEXT` Benachrichtigung angezeigt wird, geben Sie die Zeichenfolge, die in einem der folgenden Arten angezeigt werden:

- Kopieren Sie den Text in den Puffer, die gemäß der *SzText* Member.

- Kopieren Sie die Adresse des Puffers, der den Text enthält die *LpszText* Member.

- Kopieren Sie den Bezeichner der Ressource, eine Zeichenfolge, die *LpszText* Member, und kopieren Sie das Handle der Instanz, die die Ressource enthält die *Hinst* Member.

## <a name="see-also"></a>Siehe auch

[QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
