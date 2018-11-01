---
title: 'TN047: Abschwächen der Anforderungen für eine Datenbanktransaktion'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: d609576c5ffda1a3ba8021e6a459943092c40e98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658834"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Abschwächen der Anforderungen für eine Datenbanktransaktion

Diese technische Hinweise, die die Transaktion an die MFC-ODBC-Datenbankklassen erläutert, ist mittlerweile veraltet. Vor MFC 4.2, die Datenbankklassen erforderlich sind, dass Cursor bei Recordsets nach beibehalten werden eine **CommitTrans** oder **Rollback** Vorgang. Wenn die ODBC-Treiber und das DBMS diese Ebene der Beibehaltung der Cursor nicht unterstützt, die Datenbankklassen nicht Transaktionen aktivieren.

Ab MFC 4.2, haben die Beschränkung der Beibehaltung der Cursor erfordern die Datenbankklassen gelockert. Transaktionen aktiviert werden, wenn der Treiber unterstützt. Allerdings müssen Sie derzeit die Auswirkungen Überprüfen einer **CommitTrans** oder **Rollback** Vorgang auf dem geöffneten Recordsets. Die Memberfunktionen [GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) und [Rollback](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

