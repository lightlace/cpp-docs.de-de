---
title: Verwendung von IDispEventImpl (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 520d1129234a26ff6eb4c402154969ad7e166211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361150"
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

