---
title: "Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten | Microsoft Docs"
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
  - "Isolierte Anwendungen [C++]"
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Isolierte Anwendungen sind Anwendungen, die in das Programm integrierte Manifeste aufweisen.  Sie können isolierte Anwendungen erstellen, um COM\-Komponenten zu verwenden.  
  
### So fügen Sie Manifesten isolierter Anwendungen COM\-Verweise hinzu  
  
1.  Öffnen Sie die Projekteigenschaftenseiten für die isolierte Anwendung.  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften** und dann den Knoten **Manifesttool**.  
  
3.  Wählen Sie die Eigenschaftenseite **Isolated COM**, und legen Sie dann die Eigenschaft **Name der Komponentendatei** auf den Namen der COM\-Komponente fest, die von der isolierten Anwendung verwendet werden soll.  
  
4.  Klicken Sie auf **OK**.  
  
### So integrieren Sie Manifeste in isolierte Anwendungen  
  
1.  Öffnen Sie die Projekteigenschaftenseiten für die isolierte Anwendung.  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften** und dann den Knoten **Manifesttool**.  
  
3.  Wählen Sie die Eigenschaftenseite **Eingabe und Ausgabe**, und legen Sie die Eigenschaft **Manifest einbetten** auf **Ja** fest.  
  
4.  Klicken Sie auf **OK**.  
  
5.  Erstellen Sie die Projektmappe.  
  
## Siehe auch  
 [Isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190)   
 [Parallele Assemblys](_win32_side_by_side_assemblies)