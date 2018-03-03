---
title: MSG Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b504f116dcbff7fa45e741ff9715070ee0c74583
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

