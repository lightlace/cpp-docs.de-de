---
title: Standardbefehle und Fenster-IDs | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: d308f3f9efc5933124460d9839a0e94fffa60b4a
ms.lasthandoff: 02/24/2017

---
# <a name="standard-command-and-window-ids"></a>Standardbefehle und Fenster-IDs
Die Microsoft Foundation Class Library definiert eine Reihe von Standardbefehle und Fenster-IDs, die in Afxres.h. Diese IDs werden am häufigsten in den Ressourcen-Editoren und im Eigenschaftenfenster verwendet, die Handlerfunktionen Nachrichten zuzuordnen. Alle standard-Befehle verfügen über eine **ID_** Präfix. Z. B. Wenn Sie im Menü-Editor verwenden, Sie normalerweise Binden des Menüelements Datei öffnen zum Standard `ID_FILE_OPEN` Befehls-ID.  
  
 Für die meisten Befehle Anwendungscode muss nicht zum Verweisen auf die Befehls-ID, da das Framework selbst die Befehle über meldungszuordnungen in den primären Framework-Klassen behandelt ( `CWinThread`, `CWinApp`, `CView`, **CDocument**usw.).  
  
 Zusätzlich zu Standardbefehls-IDs sind die Anzahl der anderen standard-IDs definiert, die ein Präfix haben von **AFX_ID**. Diese IDs enthalten standard-Fenster-IDs (Präfix **AFX_IDW_**), string-IDs (Präfix **AFX_IDS_**), und verschiedene andere Typen.  
  
 IDs, die mit der **AFX_ID** Präfix selten von Programmierern verwendet werden, aber Sie müssen beim Überschreiben von Framework-Funktionen, die auch zum Verweisen auf diese IDs finden Sie unter der **AFX_ID**s.  
  
 IDs werden nicht einzeln in dieser Referenz dokumentiert. Weitere Informationen für diese finden Sie in den technischen hinweisen [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), und [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Die Headerdatei Afxres.h ist indirekt in Afxwin.h enthalten. Sie müssen explizit in Ihrer Anwendung Ressourcenskriptdatei (.rc) die folgende Anweisung einschließen:  
  
 [!code-cpp[NVC_MFC_Utilities&#47;](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

