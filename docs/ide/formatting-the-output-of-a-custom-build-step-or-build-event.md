---
title: Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a975951142c028ffcfb8ece870ab3ac2d2b60fc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203248"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses

Wenn die Ausgabe eines benutzerdefinierten Buildschritts oder -ereignisses ordnungsgemäß formatiert wurde, erhalten Benutzer die folgenden Vorteile:

- Warnungen und Fehler werden im **Ausgabefenster** gezählt.

- Die Ausgabe wird im Fenster **Aufgabenliste** angezeigt.

- Wenn Sie im **Ausgabefenster** auf die Ausgabe klicken, wird das entsprechende Thema angezeigt.

- F1-Vorgänge werden im Fenster **Aufgabenliste** oder im **Ausgabefenster** aktiviert.

Das Format der Ausgabe sollte wie folgt sein:

> {<em>Dateiname</em>**(**<em>Zeilennr.</em> \[**,** <em>Spaltennr.</em>]**)** &#124; *Toolname*} **:** \[ <em>beliebiger Text</em> ] {**Fehler** &#124; **Warnung**} <em>Code + Nummer</em>**:**<em>lokalisierbare Zeichenfolge</em> \[ <em>beliebiger Text</em> ]

Ort:

- {*a* &#124; *b*} ist eine Wahl von entweder *a* oder *b*.

- \[<em>item</em>] ist eine optionale Zeichenfolge oder ein Parameter.

- **bold** stellt ein Literal dar.

Zum Beispiel:

> C:\\*sourcefile.cpp*(134) : Fehler C2143: Syntaxfehler: fehlendes „;“ vor „}“

> LINK: Schwerwiegender Fehler LNK1104: Datei „*somelib.lib*“ kann nicht geöffnet werden

## <a name="see-also"></a>Siehe auch

[Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)