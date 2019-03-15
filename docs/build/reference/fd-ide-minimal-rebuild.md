---
title: /FD (Minimale Neuerstellung in der IDE)
ms.date: 11/04/2016
f1_keywords:
- /FD
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: 323a0045ab11f23ab996d5179a135d0eb4184f20
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817438"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (Minimale Neuerstellung in der IDE)

**/ Fd** ist nicht verfügbar für Benutzer mit Ausnahme von in die [Befehlszeile](command-line-property-pages.md) Eigenschaftenseite eines C++-Projekts **Eigenschaftenseiten** Dialogfeld, wenn und nur wenn  [ /GM (minimale Neuerstellung aktivieren)](gm-enable-minimal-rebuild.md) nicht ebenfalls ausgewählt. **/ Fd** wirkt sich nicht nur aus der Entwicklungsumgebung. **/ Fd** ist nicht verfügbar gemacht, in der Ausgabe des **cl /?**.

Wenn Sie nicht aktivieren **/GM** in der Entwicklungsumgebung **/FD** verwendet werden. **/ Fd** wird sichergestellt, dass die .idb-Datei über ausreichende Informationen zu den Abhängigkeiten. **/ Fd** wird nur von der Entwicklungsumgebung verwendet und sollte nicht über die Befehlszeile oder ein Buildskript verwendet werden.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](output-file-f-options.md)<br/>
[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
