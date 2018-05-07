---
title: MSG Structure1 | Microsoft Docs
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
ms.openlocfilehash: 41dbbcdd3404705a9ac7c6c7969a9ebeeb0238f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="msg-structure1"></a>MSG Structure1
Die `MSG` Struktur enthält Informationen aus der Nachrichtenwarteschlange eines Threads.  
  
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
 Identifiziert das Fenster, dessen Fensterprozedur die Nachricht empfängt.  
  
 `message`  
 Gibt die Nummer der Meldung an.  
  
 `wParam`  
 Gibt zusätzliche Informationen über die Meldung an. Die genaue Bedeutung hängt vom Wert von der **Nachricht** Member.  
  
 `lParam`  
 Gibt zusätzliche Informationen über die Meldung an. Die genaue Bedeutung hängt vom Wert von der **Nachricht** Member.  
  
 `time`  
 Gibt die Uhrzeit, an der die Nachricht gesendet wurde.  
  
 `pt`  
 Gibt die Cursorposition in Bildschirmkoordinaten an, wenn die Nachricht bereitgestellt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

