---
title: "Verwenden der Schaltfl&#228;che „Anwenden“ | Microsoft Docs"
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
  - "Übernehmen-Schaltfläche in Eigenschaftenblatt"
  - "Eigenschaftenblätter, Schaltfläche „Übernehmen“"
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verwenden der Schaltfl&#228;che „Anwenden“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eigenschaftenblätter haben eine Funktion, die Standarddialogfelder nicht möglich: Sie können dem Benutzer, die Änderungen anzuwenden, die Sie vorgenommen haben, bevor sie das Eigenschaftenblatt haben.  Dies wird mithilfe der übernehmensschaltfläche durchgeführt.  In diesem Artikel werden Möglichkeiten, die Sie verwenden können, um diese Funktion ordnungsgemäß zu implementieren.  
  
 Modale Dialogfelder gelten normalerweise die Einstellungen zu einem externen Objekt wenn der Benutzer auf OK, um das Dialogfeld zu schließen.  Das gilt für ein Eigenschaftenblatt zutrifft: Wenn der Benutzer auf OK, die neuen Einstellungen im Eigenschaftenblatt wirksam werden.  
  
 Sie sollten dem Benutzer zu ermöglichen, Einstellungen zu speichern, ohne zu müssen, das Eigenschaftenblattdialogfeld zu schließen.  Dies ist die übernehmensschaltfläche.  Die übernehmensschaltfläche Wendet die aktuellen Einstellungen in allen Eigenschaftenseiten für das externe Objekt, im Gegensatz zum Anwenden nur der aktuellen Einstellungen der gerade aktiven Seite.  
  
 Standardmäßig wird die übernehmensschaltfläche immer deaktiviert.  Sie müssen Code schreiben, um die übernehmensschaltfläche zu den korrespondierenden Zeitangaben zu aktivieren, und Sie müssen Code schreiben, um den Effekt von ein zu implementieren, wie nachstehend beschrieben.  
  
 Wenn Sie nicht die übernehmensfunktionalität dem Benutzer häufig möchten, ist es nicht erforderlich, die übernehmensschaltfläche zu entfernen.  Sie können es deaktiviert werden, wie unter Anwendungen enthalten sind, die die Standardeigenschaftenblattunterstützung verwenden, die in zukünftigen Windows\-Versionen verfügbar ist.  
  
 So über eine Seite melden, wie Ändern und die übernehmensschaltfläche aktivieren, rufen Sie **CPropertyPage::SetModified\( TRUE \)**.  Wenn eine der Seiten Melden von geändert werden, die übernehmensschaltfläche bleibt aktiviert, unabhängig davon, ob die derzeit aktiven Seite geändert wurde.  
  
 Sie sollten [CPropertyPage::SetModified](../Topic/CPropertyPage::SetModified.md) aufrufen, wenn der Benutzer Einstellungen auf der Seite ändert.  Eine Möglichkeit, zu ermitteln, ob ein Benutzer einer Einstellung auf der Seite geändert wird, ist, Änderungsbenachrichtigungshandler für jede der Steuerelemente in der Eigenschaftenseite, wie **EN\_CHANGE** oder **BN\_CLICKED** zu implementieren.  
  
 Um die Wirkung der übernehmensschaltfläche zu implementieren, muss das Eigenschaftenblatt den Besitzer oder ein anderes externes Objekt in der Anwendung erkennen, die aktuellen Einstellungen auf den Eigenschaftenseiten zu übernehmen.  Gleichzeitig muss das Eigenschaftenblatt die übernehmensschaltfläche deaktivieren, indem es **CPropertyPage::SetModified\( FALSE \)** für alle Seiten aufruft, die die Änderungen für das externe Objekt angewendet haben.  
  
 Ein Beispiel hierfür Prozess, finden Sie das Beispiel [Darüber](../top/visual-cpp-samples.md) allgemeine MFC.  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)