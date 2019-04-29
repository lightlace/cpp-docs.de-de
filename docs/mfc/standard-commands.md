---
title: Standardbefehle
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
ms.openlocfilehash: 987023322e38584d10901c1ab1fe20ac46926bd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307158"
---
# <a name="standard-commands"></a>Standardbefehle

Das Framework definiert viele Standardbefehl Nachrichten. Die IDs für diese Befehle haben in der Regel das Format:

**ID_** *Quelle*_*Element*

in denen *Quelle* ist in der Regel ein Menünamen und *Element* ein Menüelement ist. Beispielsweise ist die Befehls-ID für den neuen Befehl im Menü Datei ID_FILE_NEW. Standardbefehle-IDs werden in der Dokumentation fett angezeigt. Programmiererdefinierte IDs werden in einer Schriftart angezeigt, die sich aus dem umgebenden Text unterscheidet.

Im folgenden finden eine Liste mit einigen der wichtigsten Befehle unterstützt:

*Befehle im Menü Datei*<br/>
Neu, öffnen Sie, und schließen Sie, zu speichern, speichern unter, Seite einrichten, einrichten, Druck, Druckvorschau, beenden und zuletzt verwendeten Dateien.

*Befehle im Menü Bearbeiten*<br/>
Löschen, löschen Wiederholen alle "," Kopieren "," Ausschneiden "," Suchen "," einfügen, ersetzen, Alles markieren, Rückgängig / Wiederholen.

*Befehle im Menü "Ansicht"*<br/>
Die Symbolleiste und Statusleiste.

*Befehle im Menü "Fenster"*<br/>
Neue, anordnen, kaskadiert werden, Kachel Horizontal, vertikal Kachel und teilen.

*Befehle im Menü "Hilfe"*<br/>
Index mit der Hilfe und zum.

*OLE-Befehle (Menü "Bearbeiten")*<br/>
Fügen Sie neue Objekt, Verknüpfungen bearbeiten, Verknüpfung einfügen, Inhalte einfügen und *Typename* Objekt (Verbbefehle).

Das Framework bietet verschiedene Ebenen der Unterstützung für diese Befehle. Einige Befehle sind nur als definierten Befehls-IDs unterstützt, während andere umfassende Implementierungen unterstützt werden. Beispielsweise implementiert das Framework der Befehl zum Öffnen auf das Menü "Datei" ein neues Dokumentobjekt erstellt, indem ein geöffnetes Dialogfenster, anzeigen und öffnen und Lesen der Datei. Im Gegensatz dazu müssen Sie implementieren Befehle im Menü Bearbeiten selbst, da Befehle wie ID_EDIT_COPY von der Art der Daten abhängig sind, die Sie kopieren.

Weitere Informationen zu unterstützten Befehle und die Ebene der Implementierung finden Sie [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md). Die standard-Befehle werden in der Datei AFXRES definiert. H.

## <a name="see-also"></a>Siehe auch

[Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md)
