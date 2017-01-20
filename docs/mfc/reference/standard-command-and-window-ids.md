---
title: "Standardbefehle und Fenster-IDs"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Standardbefehl und Windows-IDs"
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 13
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Standardbefehle und Fenster-IDs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Microsoft Foundation Class\-Bibliothek definiert einige Standardbefehl und Fenster IDs in Afxres.h.  Diese IDs sind innerhalb der Ressourcen\-Editoren und des Eigenschaftenfensters am häufigsten verwendet, Meldungen an die Handlerfunktionen zuzuordnen.  Alle Standardbefehle haben ein Präfix **ID\_**.  Wenn Sie im Menü\-Editor, binden Sie normalerweise das geöffnete Menüelement für die Standard\- `ID_FILE_OPEN` Befehl ID  
  
 Für die meisten Standardbefehle Anwendungscode muss nicht, um die Befehls\-ID zuzugreifen, da das Framework auch die Befehle von Meldungszuordnungen in den primären Frameworkklassen behandelt \(`CWinThread`, `CWinApp`, `CView`, **CDocument**, z.\).  
  
 Neben den Standardbefehls\-IDs werden mehrere andere Standard\-IDs definiert, die ein Präfix von **AFX\_ID** verfügen.  Diese ID\-Einschließungsstandardfenster IDs \(Präfix **AFX\_IDW\_**\), Zeichenfolgen\-IDs Präfix \( **AFX\_IDS\_**\) und verschiedene andere Typen.  
  
 IDs, die dem **AFX\_ID** Präfix anfangen, werden selten von Programmierern, aber Sie müssen möglicherweise diese IDs verweisen, wenn das Framework arbeiten, die auch das **AFX\_ID**. S verweisen.  
  
 IDs werden nicht einzeln in dieser Referenz dokumentiert.  Sie können weitere Informationen über sie in den Hinweisen technischen [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md) und [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Die Headerdatei Afxres.h wird indirekt in Afxwin.h enthalten.  Sie müssen die folgende Anweisung des Ressourcen\-Skripts der Anwendung explizit einschließen in der Datei \(.rc\):  
  
 [!CODE [NVC_MFC_Utilities#47](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#47)]  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)