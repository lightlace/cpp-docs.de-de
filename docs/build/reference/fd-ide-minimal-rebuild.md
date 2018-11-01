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
ms.openlocfilehash: a902096bf13105e6a6a66b7bd3ccc56b8f7cf624
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433591"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (Minimale Neuerstellung in der IDE)

**/ Fd** ist nicht verfügbar für Benutzer mit Ausnahme von in die [Befehlszeile](../../ide/command-line-property-pages.md) Eigenschaftenseite eines C++-Projekts **Eigenschaftenseiten** Dialogfeld, wenn und nur wenn  [ /GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) nicht ebenfalls ausgewählt. **/ Fd** wirkt sich nicht nur aus der Entwicklungsumgebung. **/ Fd** ist nicht verfügbar gemacht, in der Ausgabe des **cl /?**.

Wenn Sie nicht aktivieren **/GM** in der Entwicklungsumgebung **/FD** verwendet werden. **/ Fd** wird sichergestellt, dass die .idb-Datei über ausreichende Informationen zu den Abhängigkeiten. **/ Fd** wird nur von der Entwicklungsumgebung verwendet und sollte nicht über die Befehlszeile oder ein Buildskript verwendet werden.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)