---
title: MSG-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b2f58af3bcf3eef524b95d25579e5bc233f9108
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334532"
---
# <a name="msg-structure"></a>MSG-Struktur

Die `MSG` Struktur enthält Meldungsinformationen aus der Nachrichtenwarteschlange eines Threads.

## <a name="syntax"></a>Syntax

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

#### <a name="parameters"></a>Parameter

*HWND*<br/>
Gibt das Fenster, dessen Fensterprozedur die Meldung empfängt.

*message*<br/>
Gibt die Nummer der Meldung an.

*wParam-Parameter*<br/>
Gibt zusätzliche Informationen über die Meldung an. Die genaue Bedeutung hängt von den Wert des der `message` Member.

*lParam*<br/>
Gibt zusätzliche Informationen über die Meldung an. Die genaue Bedeutung hängt von den Wert des der `message` Member.

*time*<br/>
Gibt die Uhrzeit, zu der die Nachricht gepostet wurde.

*pt*<br/>
Gibt an der Cursorposition ein, in Bildschirmkoordinaten, wenn die Nachricht gepostet wurde.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

