---
title: "Eigenschaftenbl&#228;tter als Assistenten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Eigenschaftenblätter, als Assistenten"
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Eigenschaftenbl&#228;tter als Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Hauptmerkmal eines Assistenteneigenschaftenblattes ist, dass die Navigation mit nächsten oder End\-, Rückseiten\- und Abbrechen anstelle der Registerkarten bereitgestellt wird.  Sie müssen [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) aufrufen, bevor Sie [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) für das Eigenschaftenblattobjekt aufrufen, um diese Funktion nutzen.  
  
 Der Benutzer werden dieselbe [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md) und [CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md) Benachrichtigungen beim Wechseln von einer Seite zu einer anderen Seite.  Anschließend Endschaltflächen und sind sich gegenseitig ausschließende Alleinherrschaften; das heißt, es wird nur eine von ihnen jeweils angezeigt.  Auf der ersten Seite sollte die nächste Schaltfläche aktiviert werden.  Wenn der Benutzer auf der letzten Seite ist, sollte die Endschaltfläche aktiviert werden.  Dies wird nicht automatisch vom Framework durchgeführt.  Sie müssen [CPropertySheet::SetWizardButton](../Topic/CPropertySheet::SetWizardButtons.md) auf der letzten Seite aufrufen, um dies zu erreichen.  
  
 Um alle Standardschaltflächen, Sie anzeigen Breishow die Endschaltfläche und die nächste Schaltfläche bewegen.  Verschieben Sie dann die Schaltfläche Zurück, dass die relative Position der nächsten Schaltfläche verwaltet wird.  Weitere Erklärung finden Sie im KB\-Artikel für Q143210.  Knowledge Base\-Artikel sind in der MSDN Library verfügbar.  
  
## Beispiel  
 [!CODE [NVC_MFCDocView#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#5)]  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)