---
title: "Gewusst wie: Erstellen von COM-Komponenten ohne Registrierung"
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
  - "COM-Komponenten, Ohne Registrierung"
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Gewusst wie: Erstellen von COM-Komponenten ohne Registrierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM\-Komponenten ohne Registrierung sind COM\-Komponenten, die in DLLs integrierte Manifeste aufweisen.  
  
### So integrieren Sie Manifeste in COM\-Komponenten  
  
1.  Öffnen Sie die Projekteigenschaftenseiten für die COM\-Komponente.  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften** und dann den Knoten **Manifesttool**.  
  
3.  Wählen Sie die Eigenschaftenseite **Eingabe und Ausgabe**, und legen Sie die Eigenschaft **Manifest einbetten** auf **Ja** fest.  
  
4.  Klicken Sie auf **OK**.  
  
5.  Erstellen Sie die Projektmappe.  
  
## Siehe auch  
 [Isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190)   
 [Parallele Assemblys](_win32_side_by_side_assemblies)   
 [Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM\-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)