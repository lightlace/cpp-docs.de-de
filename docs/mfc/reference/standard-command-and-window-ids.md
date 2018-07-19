---
title: Standardbefehle und Fenster-IDs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 218f0b87edd2ec8c846c08e5cdc72aa01e22c0b1
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886023"
---
# <a name="standard-command-and-window-ids"></a>Standardbefehle und Fenster-IDs
Die Microsoft Foundation Class Library definiert eine Reihe von Standardbefehle und Fenster-IDs in Afxres.h. Diese IDs werden in den Ressourcen-Editoren und das Fenster "Eigenschaften" am häufigsten verwendet, Nachrichten an Ihre Ereignishandler Funktionen zuordnen. Alle standard-Befehle verfügen über eine **ID_** Präfix. Z. B. Wenn Sie im Menü-Editor verwenden, binden Sie normalerweise die Datei öffnen Menüelement an der standardmäßigen ID_FILE_OPEN-Befehls-ID.  
  
 Für die meisten Befehle Anwendungscode muss nicht zum Verweisen auf die Befehls-ID, da das Framework selbst die Befehle über meldungszuordnungen in den primären Frameworkklassen verarbeitet (`CWinThread`, `CWinApp`, `CView`, `CDocument`, und usw.).  
  
 Zusätzlich zum standard-Befehls-IDs werden diverse andere standard-IDs definiert, die ein Präfix haben der **AFX_ID**. Diese IDs sind standard-Fenster-IDs (Präfix **AFX_IDW_**), IDs Zeichenfolge (Präfix **AFX_IDS_**), und verschiedene andere Typen.  
  
 IDs, die mit der **AFX_ID** Präfix werden selten von Programmierern verwendet, jedoch müssen Sie möglicherweise auf diese IDs zu verweisen, wenn Sie Framework-Funktionen zu überschreiben, die auch auf verweisen die **AFX_ID**s.  
  
 IDs werden nicht einzeln in dieser Referenz dokumentiert. Können weitere Informationen finden Sie auf diese in technischen Anmerkungen zu dieser [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), und [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Die Headerdatei Afxres.h ist indirekt in Afxwin.h enthalten. Sie müssen explizit in Ihrer Anwendung Ressourcenskriptdatei (.rc) die folgende Anweisung einschließen:  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
