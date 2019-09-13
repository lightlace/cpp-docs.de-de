---
title: Standardbefehle und Fenster-IDs
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: 40783bc19e51afb0e9fe9e4a429df0239a8e7f09
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907713"
---
# <a name="standard-command-and-window-ids"></a>Standardbefehle und Fenster-IDs

Der Microsoft Foundation Class-Bibliothek definiert eine Reihe von standardmäßigen Befehls-und Fenster-IDs in AFXRES. h. Diese IDs werden am häufigsten in den Ressourcen-Editoren und im [Klassen-Assistenten](mfc-class-wizard.md) verwendet, um Nachrichten zu ihren Handlerfunktionen zuzuordnen. Alle Standard Befehle verfügen über ein **ID_** -Präfix. Wenn Sie z. b. den Menü-Editor verwenden, binden Sie normalerweise das Menü Element "Datei öffnen" an die standardmäßige ID_FILE_OPEN-Befehls-ID.

Bei den meisten Standard Befehlen muss der Anwendungscode nicht auf die Befehls-ID verweisen, da das Framework selbst die Befehle über Nachrichten Zuordnungen in seinen primären Frameworkklassen`CWinThread`verarbeitet `CWinApp`( `CView`, `CDocument`,, und). so weiter).

Zusätzlich zu den standardmäßigen Befehls-IDs werden einige andere Standard-IDs definiert, die das Präfix **AFX_ID**aufweisen. Zu diesen IDs zählen Standardfenster-IDs (prefix **AFX_IDW_** ), Zeichen folgen-IDs (Präfix **AFX_IDS_** ) und verschiedene andere Typen.

IDs, die mit dem Präfix " **AFX_ID** " beginnen, werden selten von Programmierern verwendet, aber Sie müssen möglicherweise auf diese IDs verweisen, wenn Sie Frameworkfunktionen überschreiben, die auch auf die **AFX_ID**s verweisen.

IDs werden in diesem Verweis nicht einzeln dokumentiert. Weitere Informationen finden Sie in den technischen Hinweisen [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md)und [22](../../mfc/tn022-standard-commands-implementation.md).

> [!NOTE]
>  Die Header Datei "AFXRES. h" ist indirekt in "AFXWIN. h" enthalten. Sie müssen die folgende Anweisung explizit in die Ressourcen Skriptdatei (. RC) Ihrer Anwendung einschließen:

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>Siehe auch

[Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md)
