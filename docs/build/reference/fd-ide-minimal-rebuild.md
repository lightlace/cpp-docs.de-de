---
title: /FD (Minimale Neuerstellung in der IDE)
ms.date: 04/08/2019
f1_keywords:
- /FD
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: ac63b021dc0cb9ee5964af7fa2e168f710653979
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424052"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (Minimale Neuerstellung in der IDE)

**/ Fd** wird nur für Benutzer verfügbar gemacht der [Befehlszeile](command-line-property-pages.md) Eigenschaftenseite ein C++ des Projekts **Eigenschaftenseiten** im Dialogfeld. Es ist verfügbar, wenn und nur, wenn die veraltete und deaktiviert standardmäßig [/GM (minimale Neuerstellung aktivieren)](gm-enable-minimal-rebuild.md) Option nicht aktiviert ist. **/ Fd** wirkt sich nicht nur aus der Entwicklungsumgebung. **/ Fd** ist nicht verfügbar gemacht werden, in der Ausgabe des `cl /?`.

Wenn Sie nicht die veraltete aktivieren **/GM** -Option in der Entwicklungsumgebung **/FD** verwendet wird. **/ Fd** wird sichergestellt, der .idb-Datei verfügt über ausreichende Informationen zu den Abhängigkeiten. **/ Fd** wird nur von der Entwicklungsumgebung verwendet und sollte nicht über die Befehlszeile oder ein Buildskript verwendet werden.

## <a name="see-also"></a>Siehe auch

[/F-Optionen (Ausgabedateioptionen)](output-file-f-options.md)<br/>
[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
