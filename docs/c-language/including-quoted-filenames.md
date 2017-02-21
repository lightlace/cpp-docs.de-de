---
title: "Einschlie&#223;lich Dateinamen in Anf&#252;hrungszeichen | Microsoft Docs"
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
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Einschlie&#223;lich Dateinamen in Anf&#252;hrungszeichen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** Die Unterstützung für Namen in Anführungszeichen für Quelldateien, die einbezogen werden können  
  
 Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen zwei doppelten Anführungszeichen \(" "\) angeben, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standardverzeichnisse.  
  
 Für die Includedateien, die als [\#include](../preprocessor/hash-include-directive-c-cpp.md) "path\-spec" angegeben werden, beginnt die Durchsuchung der Verzeichnisse in den Verzeichnissen der übergeordneten Datei und wird anschließend in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt.  Daher beginnt die Suche relativ zum Verzeichnis, das die Quelldatei enthält, die gerade verarbeitet wird.  Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.  
  
## Siehe auch  
 [Präprozessordirektiven](../c-language/preprocessing-directives.md)