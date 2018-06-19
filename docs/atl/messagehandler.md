---
title: Meldungshandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec0fd88def88f7d31fce078fec0c860f4f21f51c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356366"
---
# <a name="messagehandler"></a>Meldungshandler
**Meldungshandler** ist der Name der Funktion identifiziert durch den zweiten Parameter von der `MESSAGE_HANDLER` Makro in Ihrer nachrichtenzuordnung.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
    LRESULT 
    MessageHandler 
 (
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Parameter  
 `uMsg`  
 Gibt die Meldung.  
  
 `wParam`  
 Zusätzliche Meldung-spezifische Informationen.  
  
 `lParam`  
 Zusätzliche Meldung-spezifische Informationen.  
  
 `bHandled`  
 Die Nachricht Zuordnung Mengen `bHandled` auf **"true"** vor `MessageHandler` aufgerufen wird. Wenn `MessageHandler` behandelt die Nachricht nicht vollständig sollte `bHandled` auf **"false"** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Nachrichtenverarbeitung. 0, wenn erfolgreich.  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel zur Verwendung dieser Nachrichtenhandler in einer meldungszuordnung, finden Sie unter [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren eines Fensters](../atl/implementing-a-window.md)   
 [Meldungszuordnungen](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

