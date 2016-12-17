---
title: "Benutzeroberfl&#228;chen-Aktualisierung f&#252;r Datensatzansichten (MFC-Datenzugriff)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Menüs, Aktualisieren bei Kontextänderungen"
  - "Datensatzansichten, Benutzeroberfläche"
  - "Benutzeroberflächen, Aktualisieren"
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzeroberfl&#228;chen-Aktualisierung f&#252;r Datensatzansichten (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CRecordView` und `CDaoRecordView` bieten zusätzlich standardmäßige Benutzeroberflächen\-Aktualisierungshandler für die Navigationsbefehle.  Diese Handler automatisieren die Aktivierung und Deaktivierung der Benutzeroberflächenobjekte – Menüelemente und Symbolleisten\-Schaltflächen.  Der Anwendungs\-Assistent stellt Standardmenüs bereit und, wenn Sie die Option **Andockbare Symbolleiste** verwenden, eine Reihe von Symbolleisten\-Schaltflächen für die Befehle.  Wenn Sie eine Datensatzansichtsklasse mithilfe von `CRecordView` erstellen, können Sie der Anwendung vergleichbare Benutzeroberflächenobjekte hinzufügen.  
  
### So erstellen Sie Menüressourcen mit dem Menü\-Editor  
  
1.  Lesen Sie die Informationen über die Verwendung des [Menü\-Editors](../mfc/menu-editor.md), und erstellen Sie ein eigenes Menü mit denselben vier Befehlen.  
  
#### So erstellen Sie Symbolleisten\-Schaltflächen mit dem Grafik\-Editor  
  
1.  Lesen Sie die Informationen über die Verwendung des [Symbolleisten\-Editors](../mfc/toolbar-editor.md), und bearbeiten Sie die Symbolleistenressource, um Symbolleisten\-Schaltflächen für die Navigationsbefehle des Datensatzes hinzuzufügen.  
  
## Siehe auch  
 [Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)