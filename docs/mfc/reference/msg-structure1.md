---
title: MSG-Struktur 1 | Microsoft-Dokumentation
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
ms.openlocfilehash: 5fe629c2f279b6b258f4824229490f7b72b4ce4d
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338811"
---
# <a name="msg-structure1"></a>MSG-Struktur 1
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
 *HWND*  
 Gibt das Fenster, dessen Fensterprozedur die Meldung empfängt.  
  
 *message*  
 Gibt die Nummer der Meldung an.  
  
 *wParam-Parameter*  
 Gibt zusätzliche Informationen über die Meldung an. Die genaue Bedeutung hängt von den Wert des der `message` Member.  
  
 *lParam*  
 Gibt zusätzliche Informationen über die Meldung an. Die genaue Bedeutung hängt von den Wert des der `message` Member.  
  
 *time*  
 Gibt die Uhrzeit, zu der die Nachricht gepostet wurde.  
  
 *pt*  
 Gibt an der Cursorposition ein, in Bildschirmkoordinaten, wenn die Nachricht gepostet wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

