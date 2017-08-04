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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 70b5e68fc8a3c0c23b291220e4faf387e9aa11c2
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="including-quoted-filenames"></a>Einschließlich Dateinamen in Anführungszeichen
**ANSI 3.8.2** Die Unterstützung für Namen in Anführungszeichen für Quelldateien, die einbezogen werden können  
  
 Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen zwei doppelten Anführungszeichen (" ") angeben, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standardverzeichnisse.  
  
 Für die Includedateien, die als [#include](../preprocessor/hash-include-directive-c-cpp.md) „path-spec“ angegeben werden, beginnt die Durchsuchung der Verzeichnisse in den Verzeichnissen der übergeordneten Datei und wird anschließend in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt. Daher beginnt die Suche relativ zum Verzeichnis, das die Quelldatei enthält, die gerade verarbeitet wird. Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoranweisungen](../c-language/preprocessing-directives.md)
