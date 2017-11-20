---
title: Standardbefehle und Fenster-IDs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a7209e3c6e85e5d5855ddac513f95115b02cd1aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="standard-command-and-window-ids"></a>Standardbefehle und Fenster-IDs
Die Microsoft Foundation Class Library definiert eine Reihe von Standardbefehle und Fenster-IDs in Afxres.h. Diese IDs sind innerhalb der Ressourcen-Editoren und des Eigenschaftenfensters am häufigsten verwendet, Meldungen Ihre Handlerfunktionen zuordnen. Alle standard-Befehle verfügen über eine **ID_** Präfix. Z. B. Wenn Sie im Menü-Editor verwenden, Sie normalerweise binden die Datei öffnen Menüelement für den Standard `ID_FILE_OPEN` Befehls-ID.  
  
 Für die meisten Standardbefehle Anwendungscode muss nicht zum Verweisen auf die Befehls-ID, da das Framework selbst die Befehle über meldungszuordnungen in den primären Frameworkklassen verarbeitet ( `CWinThread`, `CWinApp`, < c4 > `CView` , **CDocument**usw.).  
  
 Zusätzlich zu den Standardbefehls-IDs werden diverse andere standard-IDs definiert, wofür ein Präfix des **AFX_ID**. Diese IDs enthalten Standardfenster-IDs (Präfix **AFX_IDW_**), string-IDs (Präfix **AFX_IDS_**), und verschiedene andere Typen.  
  
 IDs, beginnen mit, der **AFX_ID** Präfix selten von Programmierern verwendet werden, jedoch müssen Sie möglicherweise zum Überschreiben Framework-Funktionen, die auch zum Verweisen auf diese IDs finden Sie unter der **AFX_ID**s.  
  
 IDs werden nicht einzeln in dieser Referenz dokumentiert. Weitere Informationen auf diesen finden Sie in der technische Hinweise [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), und [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Die Headerdatei Afxres.h ist indirekt in Afxwin.h enthalten. Sie müssen explizit in die Ressourcenskriptdatei (.rc) für Ihre Anwendung die folgende Anweisung einschließen:  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
