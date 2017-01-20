---
title: "Projektbuildfehler PRJ0050"
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
  - "PRJ0050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0050"
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler beim Registrieren der Ausgabe.Vergewissern Sie sich, dass Sie über die entsprechenden Berechtigungen zum Ändern der Registrierung verfügen.  
  
 Das Visual C\+\+\-Buildsystem war nicht in der Lage, die Ausgabe des Buildvorgangs \(DLL\-Datei oder EXE\-Datei\) zu registrieren.  Sie müssen als Administrator angemeldet sein, um die Registrierung ändern zu können.  
  
 Wenn Sie eine DLL erstellen, können Sie diese manuell mithilfe von regsvr32.exe registrieren. Dadurch können Informationen über die Ursache des Fehlers beim Erstellen angezeigt werden.  
  
 Wenn Sie keine DLL erstellen, überprüfen Sie das Buildprotokoll des Befehls, der einen Fehler verursacht hat.