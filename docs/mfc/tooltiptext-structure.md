---
title: TOOLTIPTEXT-Struktur
ms.date: 11/04/2016
f1_keywords:
- TOOLTIPTEXT
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
ms.openlocfilehash: 80b95225a277a7985c30e5ea453597b06e501753
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513303"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT-Struktur

Beim Schreiben des QuickInfo- [Benachrichtigungs Handlers](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)müssen Sie die **ToolTipText** -Struktur verwenden. Die Member der **ToolTipText** -Struktur sind:

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
Identifiziert das Tool, das Text benötigt. Der einzige Member dieser Struktur, den Sie möglicherweise benötigen, ist die Befehls-ID des Steuer Elements. Die Befehls-ID des Steuer Elements befindet sich im *idfrom* -Member der **NMHDR** -Struktur, auf die `hdr.idFrom`mit der-Syntax zugegriffen wird. Eine Erörterung der Member der **NMHDR** -Struktur finden Sie unter [NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr) .

*lpszText*<br/>
Die Adresse einer Zeichenfolge, die den Text für ein Tool empfängt.

*szText*<br/>
Puffer, der den QuickInfo-Text empfängt. Eine Anwendung kann den Text als Alternative zum Angeben einer Zeichen folgen Adresse in diesen Puffer kopieren.

*hinst*<br/>
Handle der-Instanz, die eine Zeichenfolge enthält, die als QuickInfo-Text verwendet werden soll. Wenn *lpszText* die Adresse des QuickInfo-Texts ist, ist dieser Member NULL.

Wenn Sie die `TTN_NEEDTEXT` Benachrichtigungs Meldung verarbeiten, geben Sie die anzuzeigende Zeichenfolge auf eine der folgenden Arten an:

- Kopieren Sie den Text in den Puffer, der durch den *szText* -Member angegeben wird.

- Kopieren Sie die Adresse des Puffers, der den Text enthält, in den *lpszText* -Member.

- Kopieren Sie den Bezeichner einer Zeichen folgen Ressource in das *lpszText* -Element, und kopieren Sie das Handle der-Instanz, die die Ressource enthält, in das *hInst* -Member.

## <a name="see-also"></a>Siehe auch

[QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
