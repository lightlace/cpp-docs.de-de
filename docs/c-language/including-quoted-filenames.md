---
title: Einschließlich Dateinamen in Anführungszeichen
ms.date: 11/04/2016
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
ms.openlocfilehash: 11beaa3a91f476348c57b12ab3febad7cb9c89fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656715"
---
# <a name="including-quoted-filenames"></a>Einschließlich Dateinamen in Anführungszeichen

**ANSI 3.8.2** Die Unterstützung für Namen in Anführungszeichen für Quelldateien, die einbezogen werden können

Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen zwei doppelten Anführungszeichen (" ") angeben, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standardverzeichnisse.

Für die Includedateien, die als [#include](../preprocessor/hash-include-directive-c-cpp.md) „path-spec“ angegeben werden, beginnt die Durchsuchung der Verzeichnisse in den Verzeichnissen der übergeordneten Datei und wird anschließend in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt. Daher beginnt die Suche relativ zum Verzeichnis, das die Quelldatei enthält, die gerade verarbeitet wird. Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.

## <a name="see-also"></a>Siehe auch

[Präprozessoranweisungen](../c-language/preprocessing-directives.md)