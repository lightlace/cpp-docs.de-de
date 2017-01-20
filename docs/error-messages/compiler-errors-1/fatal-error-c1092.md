---
title: "Schwerwiegender Fehler C1092"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C1092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1092"
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bearbeiten und Fortfahren unterstützt keine Änderungen an Datentypen. Build erforderlich  
  
 Seit dem letzten erfolgreichen Build wurde ein Datentyp geändert oder hinzugefügt.  
  
-   "Bearbeiten und Fortfahren" unterstützt keine Änderungen an vorhandenen Datentypen, einschließlich Klassen\-, Struktur\- oder Enumerationsdefinitionen.  Der Debugvorgang muss beendet und die Anwendung erstellt werden.  
  
-   Das Hinzufügen neuer Datentypen wird von "Bearbeiten und Fortfahren" nicht unterstützt, wenn eine Programm\-Datenbankdatei, z. B. **vcx0.pdb** \(wobei *x* für die höchste Version der verwendeten Visual C\+\+\-Software steht\), schreibgeschützt ist.  Zum Hinzufügen von Datentypen muss die PDB\-Datei vom Compiler im Schreibmodus geöffnet werden.  
  
### So beseitigen Sie diesen Fehler, ohne die aktuelle Debugsitzung zu beenden  
  
1.  Versetzen Sie den Datentyp wieder in den Zustand, der vor Auftreten des Fehlers gültig war.  
  
2.  Wählen Sie im Menü **Debuggen** die Option **Codeänderungen übernehmen**.  
  
### So beseitigen Sie diesen Fehler, ohne den Quellcode zu ändern  
  
1.  Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.  
  
2.  Klicken Sie im Menü **Erstellen** auf **Erstellen**.  
  
 Weitere Informationen finden Sie unter [Unterstützte Codeänderungen](../Topic/Supported%20Code%20Changes%20\(C++\).md).