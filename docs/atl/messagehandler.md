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
ms.workload: cplusplus
ms.openlocfilehash: f5a09439cf47c695af0d3b7d6c7724cffcb9ccb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

