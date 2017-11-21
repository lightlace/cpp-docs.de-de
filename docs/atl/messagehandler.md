---
title: Meldungshandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MessageHandler
dev_langs: C++
helpviewer_keywords: MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd6828f5c6b4f89b7d939e4fd909e72e3039b69f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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

