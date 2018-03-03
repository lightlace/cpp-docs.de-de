---
title: "TN047: Abschwächen der Anforderungen für die Datenbank-Transaktionen eine | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92631d96e8782a80275695ef4bf2623dc1bff833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Abschwächen der Anforderungen für eine Datenbanktransaktion
Dieser Hinweis an den technischen, die die Anforderungen für Transaktionen in den MFC-ODBC-Datenbankklassen erläutert wird, ist mittlerweile veraltet. Bevor MFC-4.2 Datenbankklassen erforderlich, dass Cursor bei Recordsets nach beibehalten werden eine **CommitTrans** oder **Rollback** Vorgang. Wenn die ODBC-Treiber und DBMS dieses Maß an Beibehaltung der Cursor nicht unterstützt, haben die Datenbankklassen Transaktionen nicht aktiviert.  
  
 Ab MFC 4.2, haben die Beschränkung der Beibehaltung der Cursor erfordern die Datenbankklassen gelockert. Transaktionen werden aktiviert, wenn der Treiber unterstützt. Allerdings müssen Sie jetzt die Auswirkung Überprüfen einer **CommitTrans** oder **Rollback** Vorgang auf geöffneten Recordsets. Die Memberfunktionen [GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) und [Rollback](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

