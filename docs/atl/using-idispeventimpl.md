---
title: Verwendung von IDispEventImpl (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f787fac05e95fff8a974692c3e6fca24561ed222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-idispeventimpl"></a>Verwendung von IDispEventImpl
Bei Verwendung `IDispEventImpl` um Ereignisse zu behandeln, müssen Sie:  
  
-   Leiten Sie eine Klasse von [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Fügen Sie ein Ereignis Sink-Zuordnung der Klasse hinzu.  
  
-   Fügen Sie Einträge mit dem Ereignissenke Zuordnung der [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) oder [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) Makro.  
  
-   Implementieren Sie die Methoden, die Sie behandeln interessiert sind.  
  
-   Melden Sie an und die Ereignisquelle.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie behandelt die **DocumentChange** Ereignis ausgelöst wird, von Word **Anwendung** Objekt. Dieses Ereignis wird als eine Methode definiert, auf die **ApplicationEvents** Disp-Schnittstelle.  
  
 Das Beispiel stammt aus dem [ATLEventHandling-Beispiel](../visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 Im Beispiel wird `#import` zum Generieren der erforderlichen Headerdateien aus der Typbibliothek für Word. Wenn Sie dieses Beispiel mit anderen Versionen von Word verwenden möchten, müssen Sie die korrekte Mso-Dll-Datei angeben. Z. B. Office 2000 bietet mso9.dll und OfficeXP mso.dll bereit. Dieser Code wird von "stdafx.h" vereinfacht:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]  
  
 Im folgende Code wird im NotSoSimple.h angezeigt. Der relevante Code wird durch Kommentare aufgeführt:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)   
 [ATLEventHandling-Beispiel](../visual-cpp-samples.md)

