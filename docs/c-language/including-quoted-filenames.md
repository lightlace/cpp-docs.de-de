---
title: "Einschließlich Dateinamen in Anführungszeichen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75b9e308fec394825b3113a716ead2c93e9bb290
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="including-quoted-filenames"></a>Einschließlich Dateinamen in Anführungszeichen
**ANSI 3.8.2** Die Unterstützung für Namen in Anführungszeichen für Quelldateien, die einbezogen werden können  
  
 Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen zwei doppelten Anführungszeichen (" ") angeben, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standardverzeichnisse.  
  
 Für die Includedateien, die als [#include](../preprocessor/hash-include-directive-c-cpp.md) „path-spec“ angegeben werden, beginnt die Durchsuchung der Verzeichnisse in den Verzeichnissen der übergeordneten Datei und wird anschließend in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt. Daher beginnt die Suche relativ zum Verzeichnis, das die Quelldatei enthält, die gerade verarbeitet wird. Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoranweisungen](../c-language/preprocessing-directives.md)