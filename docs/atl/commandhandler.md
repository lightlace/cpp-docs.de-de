---
title: CommandHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CommandHandler
dev_langs: C++
helpviewer_keywords: CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c17d9e731eaee9c6e1a1c584e61db6c9826cf8d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="commandhandler"></a>CommandHandler
`CommandHandler`ist die Funktion, die durch den dritten Parameter von der `COMMAND_HANDLER` Makro in Ihrer nachrichtenzuordnung.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
    LRESULT 
    CommandHandler 
 (
    WORD wNotifyCode,  
    WORD wID,  
    HWND hWndCtl,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Parameter  
 `wNotifyCode`  
 Benachrichtigungscode.  
  
 *wID*  
 Der Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.  
  
 *hWndCtl*  
 Ein Handle für ein Window-Steuerelement.  
  
 `bHandled`  
 Die Nachricht Zuordnung Mengen `bHandled` auf **"true"** vor `CommandHandler` aufgerufen wird. Wenn `CommandHandler` behandelt die Nachricht nicht vollständig sollte `bHandled` auf **"false"** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Nachrichtenverarbeitung. 0, wenn erfolgreich.  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel zur Verwendung dieser Nachrichtenhandler in einer meldungszuordnung, finden Sie unter [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren eines Fensters](../atl/implementing-a-window.md)   
 [Meldungszuordnungen](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

